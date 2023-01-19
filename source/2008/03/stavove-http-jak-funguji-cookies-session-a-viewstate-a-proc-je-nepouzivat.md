<!-- dcterms:identifier = aspnetcz#190 -->
<!-- dcterms:title = Stavové HTTP: jak fungují Cookies, Session a ViewState a proč je nepoužívat -->
<!-- dcterms:abstract = Web byl stvořen jako bezstavový a struktura HTTP a HTML tomu odpovídá. Často ale potřebujeme simulovat stavovou logiku a existuje několik technik, které dokážou toto omezení v větším či menším úspěchem obcházet. A za větší či menší cenu. -->
<!-- np9:categoryId = 1 -->
<!-- x4w:category = IT -->
<!-- np9:authorId = 1 -->
<!-- np9:authorEmail = michal.valasek@altairis.cz -->
<!-- dcterms:creator = Michal Altair Valášek -->
<!-- np9:serialId = 4 -->
<!-- x4w:serial = Stavové HTTP -->
<!-- dcterms:created = 2008-03-20T08:00:42+01:00 -->
<!-- dcterms:date = 2008-03-20T08:00:42+01:00 -->

Web byl stvořen jako bezstavový. Přesněji řečeno, standardy HTTP a HTML jsou navržené jako bezstavové. Co to znamená? Že jednotlivé požadavky na server položené (HTTP requesty) spolu nejsou nijak svázány. Server neví, zda jsou od téhož uživatele, zda spolu nějak souvisejí atd. 

## Stavový vs. bezstavový protokol

Například protokol SMTP, který se používá pro přenos e-mailových zpráv, je stavový. Komunikace probíhá tak, že klient otevře TCP spojení na server a po celou dobu transakce ho drží otevřené. Tímto kanálem klient pošle sérii příkazů a obdrží odpovědi na ně. Typicky pošle příkazy HELO (představí se), MAIL FROM (adresa odesílatele), RCPT TO (adresa příjemce) a DATA (vlastní zpráva).

Důležité je, že tyto příkazy jsou spolu svázané, server udržuje s klientem stálé spojení a ví, že v rámci této konkrétní relace k sobě patří tento odesílatel, tento příjemce a tento text zprávy.

V případě komunikace pomocí HTTP je situace úplně odlišná. Klient (webový prohlížeč) otevře spojení se serverem, a pošle nějaký příkaz (typicky něco jako *GET /stranka.aspx HTTP/1.1*). Server mu na něj odpoví tím, že pošle stránku, kterou klient chtěl. Pak ukončí spojení a na celou transakci zapomene. 

Pokud uživatel vznese další požadavek, třeba si dotahuje nějaké skripty, obrázky, a nebo uživatel klepne na odkaz či odešle formulář, celá historie se opakuje - ale server neví, že spolu tyto dva požadavky jakkoliv souvisejí a nemá možnost si je mezi sebou propojit. 

Tato architektura má ještě jeden zásadní efekt: aktivita musí vždycky vycházet z klienta, nikdy ne ze serveru - ten je odkázán do role odpovídače. Neexistuje způsob, jakým by se server mohl připojit ze své vůle na klienta a jakkoliv s ním komunikovat - poslat mu aktualizovaná data, zeptat se, zda je ještě naživu a podobně. 

Proč tomu tak je? Bezstavovost znamená, že daný protokol je mnohem jednodušší implementovat a představuje mnohem menší zátěž pro server. Lépe se také vyrovná se ztrátou spojení: stačí opakovat jeden požadavek. Je také mnohem snáze škálovatelný, protože můžete jednoduše postavit webovou farmu, kde bude každý požadavek vyřizovat jiný server.

Bezstavovost představuje výhodu i pro klienta. I pro něj je výhodné, že musí udržovat otevřené spojení jenom po krátkou dobu a že se snadno vyrovná se změnami a výpadky spojení.

## Jak to obejít

Ve většině případů nám toto chování vyhovuje a dokážeme se s ním - při správném návrhu aplikace - smířit. Ba dokonce, využít ho. Správně napsaná bezstavová aplikace je s minimálním nebo vůbec žádným dodatečným úsilím schopná běžet na webové farmě, snáze si poradí s cacheováním (ať už na straně serveru, klienta nebo mezilehlé proxy) a obvykle si dobře poradí i s restriktivním nastavením prohlížeče - s vypnutými skripty, cookies a podobně.

Nejsnazší přístup tedy je, nesnažit se bezstavovost HTTP obejít, ale naopak ji využít. Pokud to není možné, máte v zásadě tři možnosti, jak se z toho vykecat: Cookies, Sessions a ViewState/ControlState.

*   V případě **cookies** se ukládá malé množství dat na klienta a tato data se přenášejí s každým požadavkem. 
*   **Sessions** fungují tak, že se přenáší (v cookie nebo jako součást URL) pouze identifikátor session a vlastní data se udržují na straně serveru. 
*   **ViewState/ControlState** veškerá data ukládá v zašifrované a komprimované podobě do skrytého pole formuláře.

*V následujících dílech tohoto seriálu (budou vycházet s denním odstupem) se na tyto možnosti podíváme postupně, probereme jejich výhody a nevýhody.*
<!-- dcterms:identifier = aspnetcz#86 -->
<!-- dcterms:title = Představení uživatelských instancí SQL Serveru 2005 -->
<!-- dcterms:abstract = Uživatelské instance (user instances) jsou užitečnou novinkou v Microsoft SQL Serveru Express 2005 . Jako každá novinka však přinášejí též různé potíže a nedorozumění, především z důvodu nepochopení. Pojďme se tedy podrobněji podívat na to, co to vlastně "uživatelské instance" jsou a jak fungují. -->
<!-- np9:categoryId = 1 -->
<!-- x4w:category = IT -->
<!-- np9:authorId = 1 -->
<!-- np9:authorEmail = michal.valasek@altairis.cz -->
<!-- dcterms:creator = Michal Altair Valášek -->
<!-- dcterms:created = 2006-04-12T01:18:58.34+02:00 -->
<!-- dcterms:date = 2006-04-12T01:18:58.34+02:00 -->

Uživatelské instance (user instances) jsou užitečnou novinkou v Microsoft SQL Serveru Express 2005 . Jako každá novinka však přinášejí též různé potíže a nedorozumění, především z důvodu nepochopení. Pojďme se tedy podrobněji podívat na to, co to vlastně "uživatelské instance" jsou a jak fungují.

Pokročilejším programátorům a databázovým specialistům se omlouvám za jisté nepřesnosti a zjednodušení v tomto článku. Vznikl proto, že jsem se poslední dobou setkal s řadou zásadních nepochopení funkce databázového serveru a proto se snažím problematiku vysvětlit maximálně jednoduše.

## Access v. SQL Server

Vzhledem k obvyklým principům práce s počítačem jsou pro většinu lidí nejsnáze pochopitelné souborové databáze jako *Microsoft Access* nebo *Microsoft Visual FoxPro*: ty pracují s datovými soubory obdobně jako většina běžných klientských programů. Co databáze, to jeden MDB soubor. Pokud chcete zkopírovat nebo zazálohovat databázi, vypálíte ji na cédéčko... Databáze tohoto typu jsou obvykle jednoduché a určené především pro lokální a jednouživatelské prostředí.

Tento přístup ale neplatí pro větší databázové systémy, jako například *Microsoft SQL Server* nebo *Oracle*. Ty samozřejmě také používají k ukládání dat soubory, ale ne tak přímým, "dokumentovým" způsobem. Databáze je v nich chápána spíše jako služba. Proto také tyto programy nemají žádné obvyklé uživatelské rozhraní, v nichž byste mohli datový soubor "otevřít". Běží jako služba, na pozadí, a připojuje se k nim prostřednictvím specifického aplikačního protokolu. Pomocí toho se též spravují, ačkoliv se s nimi typicky dodávají i vizuální nástroje na správu (Enterprise Manager, SQL Management Studio). 

Zatímco v případě Accessu obvykle platí, že veškeré údaje jsou uloženy v jediném MDB souboru, v případě Microsoft SQL Serveru jsou takové soubory vždy nejméně dva: hlavní datový soubor (`něco.mdf`) a soubor s transakčním logem (`něco_log.ldf`). Může jich být i podstatně víc, pro zvýšení výkonu se často různé části databáze ukládají do různých souborů na různých discích. 

Práce s databázemi probíhá tak, že se datové soubory speciálním postupem připojí k serveru (anglicky *attach* [eteč], v českém techspeaku se často používá *attachnout* [etečnout]) a databáze je identifikována nikoliv názvem souboru, ale svým logickým názvem. Databáze je obvykle připojena trvale, s jejími soubory se nedá přímo pracovat a veškeré operace se provádějí pomocí aplikačního rozhraní databázového serveru. V odůvodněných případech je možno ji odpojit (anglicky *detach* [deteč], techspeak *detachnout* [detečnout]), čímž se databáze na serveru znepřístupní.

Celý tento složitý postup je zde ze dvou hlavních důvodů. Prvním důvodem je, že moderní databázové systémy jsou mnohem více, než jenom skladiště dat. Obsahují funkce na monitorování, optimalizaci a zálohování databází a podobně. Tyto činnosti probíhají nezávisle na aplikaci, která databázi využívá.

Druhý hlavní důvod je umožnit efektivní využítvání databáze více uživateli současně. To je velmi důležité u webových aplikací, kde nemůžete obvykle nijak ovlivnit, kolik současných uživatelů budete mít. Pokud má více uživatelů současně přistupovat k jedné souborové databázi (typicky MDB - Microsoft Access), je nutno tuto databázi uložit na sdílený síťový disk. Databázový stroj (program Microsoft Access) je pak nainstalován na každém klientském počítači a jednotlvá jeho vtělení se "přetahují" o společný datový soubor. 

V případě SQL Serveru je tomu jinak: databázový stroj je nainstalován pouze na jediném počítači a tam jsou také uloženy datové soubory. Klientské aplikace se pak připojují na něj a jemu zadávají příkazy. Je to také databázový server, který se stará o aplikaci uživatelských práv, je tedy možno dát různým uživatelům různá oprávnění k různým databázovým objektům.

Databázi pak identifikujete v connection stringu názvem serveru a logickým názvem databáze (a obvykle zadáváte i uživatelské jméno a heslo). Connection string pak vypadá nějak takto: `SERVER=friesian.altairis.cz; DATABASE=MojeDatabaze; UID=uživatel; PWD=heslo`.

## User instance v SQL Serveru Express 2005

Shora uvedený přístup má samozřejmě i své nevýhody. Při vývoji a testování si zaplevelujete server různými testovacími databázemi, pro jednouživatelské desktopové aplikace zase klasické použití SQL Serveru znamená složitější nasazení a správu.

Proto Microsoft SQL Server Express 2005 obsahuje novinku zvanou "uživatelské instance" (user instances). Zdůrazňuji, že vše níže napsané se týká jenom edice Express, v tomto případě neplatí, že vyšší edice mají veškerou funkcionalitu edic nižších. User instances zdánlivě boří shora uvedené paradigma, protože místo databáze zadáváte fyzickou cestu k MDF souboru. 

Postup je zhruba následující: Při otevření spojení se vytvoří a nastartuje nová instance SQL Serveru. Jedná se o dočasnou instanci drženou v paměti, která je dostupná jenom pro oho uživatele, který ji vytvořil. Specifikovaný databázový soubor a jeho log se připojí jako jediná databáze a uživatel je do ní odkázán. Po uzavření spojení se databáze zase odpojí a instance se zruší.

Connection string vypadá v uvedeném případě takto: `Data Source=.\SQLExpress; Integrated Security=True; User Instance=True; AttachDBFilename=X:\cesta\k\souboru.mdf`.

Možnosti SQL Serveru jsou v tomto režimu práce omezené, nefunguje údržba, je omezen systém uživatelských práv atd. Proto je použitelnost uživatelských instancí omezená. Jsou však výhodné ve dvou základních případech.

Prvním případem je vývoj aplikací (i webových). Databáze je součástí struktury projektu a je dynamicky připojena v případě, když je to zapotřebí. Je fakticky součástí zdrojového kódu. Pro nasazení na ostrém produkčním serveru se pak databáze vytvoří nebo připojí běžným způsobem.

Druhým případem je tvorba jednouživatelské desktopové aplikace, která chce využívat SQL Server pro ukládání dat. S datovými soubory je možno (pokud není aplikace spuštěna) zacházet běžným způsobem, aniž by bylo nutno se vzdát většiny výhod SQL Serveru. Rovněž není nutno SQL Server Express nijak zvlášť konfigurovat, např. v rámci setupu aplikace a podobně.

## Na server user instances nepatří

User instance jsou ovšem *naprosto nevhodné* pro ostrý běh webových aplikací na serveru. Důvodů pro to je několik.

Vytvoření nové instance, její nastartování a připojení databáze znamená poměrně velkou režii. První požadavek na aplikaci po delší době nečinnosti pak trvá velmi dlouho, protože tohle všechno musí provést.

Použití více instancí SQL Serveru znamená pro server větší zátěž, je mnohem efektivnější mít jednu instanci a v ní různé databáze.

Takovýmto způsobem používaná databáze se prakticky nedá zálohovat. Souborově ji nezkopírujete (protože soubor je zpravidla otevřen instancí a používá se), plánované zálohování SQL Serveru ale nelze použít. Totéž se týká jakýchkoliv změn v databázi. Uživatelská instance je viditelná jenom pro toho, kdo ji vytvořil, nedá se na ni nijak zvlášť připojit a například modifikovat strukturu tabulek. 

Jediný způsob jak zazálohovat databázi nebo provést změny v její struktuře (pokud tak samozřejmě neučiní aplikace sama z kódu) je shodit aplikaci, například pomocí triku se souborem [app_offline.htm](https://www.aspnet.cz/Articles/77-tajemstvi-souboru-app-offline-htm-snadny-upgrade-aplikaci-v-asp-net-2-0.aspx) a zkopírovat přímo datové soubory.

Právě z tohoto důvodu je možno user instance používat pouze u Express edice SQL Serveru, nikoliv u edic vyšších.

## Závěr a užitečné odkazy

Jako vždy, i v případě uživatelských instancí platí, že mohou být velmi užitečné, pokud jim porozumíte, ale velmi matoucí pokud ne. Pro jednodušší schémata práce s databází a při vývoji mohou výrazně zjednodušit práci a nasazení. Pro složitější schémata (například síťový přístup) nebo ostré nasazení na web serveru ovšem použijte běžný způsob práce s databází.

Více:

*   [Download Microsoft SQL Server 2005 - Express Edition](http://msdn.microsoft.com/vstudio/express/sql/)

*   [Popis user instances na MSDN](http://msdn.microsoft.com/sql/express/default.aspx?pull=/library/en-us/dnsse/html/sqlexpuserinst.asp)

*   [Blog SQL Express teamu](http://blogs.msdn.com/sqlexpress/) s množstvím užitečných tipů a downloadů
*   [Popis omezení Express edice](http://www.teratrax.com/articles/sql_server_2005_express.html)
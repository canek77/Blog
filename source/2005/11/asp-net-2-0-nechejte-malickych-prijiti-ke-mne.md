<!-- dcterms:identifier = riderweblog#218 -->
<!-- dcterms:title = ASP.NET 2.0: Nechejte maličkých přijíti ke mně… -->
<!-- dcterms:abstract = Microsoft nikdy neuměl moc prodávat malým. A právě tato neschopnost je klíčem k jednomu z největších jeho historických neúspěchů, tedy pozici na trhu webových aplikací, kde je kombinace IIS + ASP/ASP.NET zcela převálcována duem Apache + PHP. Změní se na tom něco s ASP.NET 2.0? Mohlo by... -->
<!-- np9:categoryId = 1 -->
<!-- x4w:category = Koně -->
<!-- np9:authorId = 1 -->
<!-- np9:authorEmail = michal.valasek@altairis.cz -->
<!-- dcterms:creator = Michal Altair Valášek -->
<!-- dcterms:created = 2005-11-09T21:22:13.087+01:00 -->
<!-- dcterms:date = 2005-11-09T21:22:13.087+01:00 -->

## Komu Microsoft neumí prodávat

Microsoft nikdy neuměl moc prodávat malým. A právě tato neschopnost je klíčem k jednomu z největších jeho historických neúspěchů, tedy pozici na trhu webových aplikací, kde je kombinace IIS + ASP/ASP.NET zcela převálcována duem Apache + PHP.

### Velcí nemají na výběr

Microsoft má velmi silnou pozici ve velkých firmách. Zde je jeho silnou stránkou integrace. Pokud máte stovky, tisíce či desetitisíce zaměstnanců, potřebujete o nich uchovávat informace, zařizovat pro ně groupware, tvorbu a správu dokumentů… A to všechno provázané tak, abyste se z toho nezbláznili. V takovém případě je Active Directory + Exchange + MS Office + Sharepoint atd. prakticky jediné řešení.

V takové situaci je klíčovým parametrem snadnost a automatizovatelnost správy a nasazení – ono magické TCO, neboli total cost of ownership. Kromě Microsoftu neexistuje na světě firma, která by dokázala svými produkty pokrýt celou škálu shora uvedených potřeb. A ačkoliv ani spolupráce mezi MS produkty není vždy zcela spolehlivá, jedná se o procházku růžovou zahradou proti snahám rozchodit v reálném prostředí spolupráci produktů různých výrobců.

To je ostatně dobře vidět na příkladu řady honosně oznamovaných „přechodů na Linux“, které obvykle co do praktického efektu končí právě tím oznámením (asi tak za rok se objeví druhé, podstatně nenápadnější, o posunutí předpokládaného termínu).

### Úplně malé výběr nezajímá

Koncové uživatelé, tedy ta masa lidí, kteří sedí u počítače, výběr vcelku nezajímá. Takový uživatel potřebuje psát dokumenty, e-maily, prohlížet web a chce si pouštět na počítači písničky a prohlížet fotky z dovolené… S jemnými nuancemi mu stejně dobře vyhoví Windows, Linux i Mac, nevidí rozdíl mezi Internet Explorerem a Mozillou, dokumenty napíše stejně dobře v MS Office jako ve WinTextu nebo OpenOffice.

Bude používat to, co v práci (a tam dostane ze shora uvedených důvodů Windows a Office), případně co bude mít na počítači předinstalováno (a na těchto pozicích je Microsoft velice pevně zakopán).

### Mít tak jeden krk…

Mezi shora uvedenými extrémy se nachází sféra malých a středních firem – dle českého pojetí toho co je „malé“ a „střední“. To je přesně ta skupina zákazníků, které Microsoft nikdy nedokázal účinným způsobem oslovit.

Tito zákazníci neocení propracované nástroje na správu velkých sítí (pokud máte deset počítačů a deset uživatelů, nepotřebujete je) a spíše než TCO je zajímají okamžité pořizovací náklady a absolutní čísla.

Kromě toho jim Microsoft často nemá co nabídnout. Typickým příkladem jsou poštovní (e-mailové) servery. Jediným produktem Microsoftu v tomto směru je Exchange, což je ale pro prostý e-mail řešení stylem „kanón na vrabce“. Jako součást Windows Serveru 2003 se konečně objevil i POP3 server, ovšem jeho možnosti jsou tak primitivní, že se jedná o řešení spíše teoretické.

Malé firmy dokáže Microsoft sice vyděsit (kampaněmi stylu „černý pytel od BSA“), ale nikoliv pořádně oslovit. Je jich příliš mnoho, mají příliš různé potřeby a nemají ten příslovečný „jeden krk“, za který by se daly chytit.

## Proč Microsoft na webu prohrává

Podívejme se na studie americké společnosti [Netcraft](http://www.netcraft.com/), jmenovitě na [graf zastoupení jednotlivých webových serverů](http://news.netcraft.com/archives/2005/11/07/november_2005_web_server_survey.html) na trhu za posledních deset let:

![Zastoupení jednotlivých webových serverů na trhu za posledních deset let. Zdroj: Netcraft.com](https://www.cdn.altairis.cz/Blog/2005/20051109-netcraft-graf.gif)

V současné době jsou na trhu jenom dva hráči: Apache s podílem okolo 70% (a stále rostoucím) a Microsoft IIS s víceméně konstantním podílem okolo 20%. Zajímavý je ovšem historický vývoj, kdy podíl Microsoftu zůstává vcelku konstantní od konce roku 1997, zatímco podíl Apache stoupá.

Řekl bych, že je to tím, že Microsoftu jeho zákazníci zůstali víceméně věrní, ale na druhou stranu nezískal mnoho z těch, nových, kteří se objevili s překotným rozvojem Internetu v posledních letech.

Podle mého názoru je tato situace způsobena několika vzájemně se doplňujícími faktory.

Jak jsem již byl pravil, Microsoft neoslovuje malé a menší zákazníky. Jednak je to složité (moc hlav, ke kterým musíme mluvit) a druhak obtížné, anžto na ně nepůsobí obvyklé triky o TCO, týmové spolupráci, vysoké výkonnosti a dostupnosti na serverových clusterech a podobně. Microsoft dílem neumí oslovit a dílem podcenil početnou skupinu nadšenců, kteří weby tvoří (alespoň zpočátku) pro zábavu a ne pro peníze. Ovšem z těchto nadšenců se rekrutují profesionální programátoři, kteří užírají po malých soustech velký díl koláče tržního podílu Microsoftu.

Základní příčiny tohoto stavu (kromě nedostatečné propagace) jsou podle mého názoru tři a mají společného jmenovatele: vysoké vstupní náklady, které si začátečník nemůže dovolit, a později již obvykle nemá potřebu vydávat.

### Nedostupné vývojové nástroje

O tomto problému můžeme už několik hodin mluvit v minulém čase, protože už několik hodin jsou k dispozici Express verze vývojových nástrojů. Povíme si o nich více později.

Až do doby velmi nedávné fakticky neexistoval způsob, jak vyvíjet aplikace pro ASP.NET, aniž byste museli zaplatit nekřesťanské peníze za vývojové prostředí. Jediným reálně existujícím nástrojem bylo Microsoft Visual Studio .NET v ceně mnoha desítek tisíc korun. Teoreticky alternativy existují. Například open-source klon VS.NET jménem SharpDevelop nebo přímo Microsoftem poskytnutý ASP.NET Web Matrix.

Posledně jmenovaný kousek software představuje přímo pomníček neobratnosti Microsoftu v této věci. Ač byl poměrně halasně propagován, nedočkal se Web Matrix prakticky žádného rozšíření. Microsoft jej, pravděpodobně ve snaze zabránit mu v možnosti konkurovat VS.NET, zohavil způsobem, že je téměř nepoužitelný. Rozhodně se nemůže svým komfortem rovnat zdarma dostupným nástrojům pro vývoj v PHP. Kromě toho veškeré příklady a ukázkové aplikace, kromě několika smutných snah Microsoftu, jsou dostupné pouze pro VS.NET a s Web Matrixem nikdo nepočítá.

SharpDevelop je sice schopnější, ale jako nezávislý nekomerční produkt nemá prakticky žádnou propagaci a s podporou v příkladech je to zcela stejné.

Nedostupnost vývojových nástrojů je ostatně u Microsoftu tradicí. Vždy mířil pouze na profesionální vývojáře z větších firem, kterým je možno schopné nástroje draze prodat.

Má paměť zahrnuje toliko jeden případ opaku, a tím byl produkt jménem „Microsoft Visual Basic 5.0 Control Creation Edition“. Ve snaze podpořit svou technologii ActiveX uvolnil Microsoft speciální edici Visual Basicu, která umožňovala vytváření ActiveX ovládacích prvků. Nedočkala se příliš velkého přijetí, protože vytváření a distribuce ActiveX prvků je docela složité. A smrtelnou ránu mu zasadila plejáda bezpečnostních problémů Internet Exploreru, která (právem) zapsala ActiveX prvky na webových stránkách (spolu s Java Applety) na listinu ohrožených druhů.

Klasické ASP stránky (Active Server Pages) se daly docela dobře psát bez specifického vývojového prostředí v běžném editoru, a hodně lidí tak činilo. Želbohu prostým výčtem schopností ASP v souboji s PHP reálně prohrávaly. Původní idea u ASP byla taková, že veškerá reálná funkčnost bude ležet v COM komponentách (psaných nejlépe v C++) a ASP skripty budou jenom jednoduše ovládat tyto komponenty. Tomu odpovídal i jejich výkon a celkové schopnosti.

Tato myšlenka se ovšem nikdy ve velkém měřítku neuchytila, protože vývoj a správa COM komponent byla příliš složitá a ve světě hostingových služeb téměř nerealizovatelná. Lidé psali celé aplikace ve VBScriptu a skriptovací engine se hroutil pod náporem, na který nebyl stavěn.

Platforma ASP.NET, ač svými schopnostmi PHP výrazně předčila, měla tedy velmi ztíženou nástupní pozici.

### Nedostupný web hosting

Drtivá většina webů je umístěna nikoliv na serverech vlastníků prezentací, ale na serverech poskytovatelů web hostingových služeb. Autor aplikace nemá kontrolu nad serverem, na němž tato běží, pouze si za jistý poplatek pronajímá část jeho služeb.

Ani v tomto směru Microsoft dlouho netrefil do černého. Začít poskytovat hosting na platformě Microsoft (Windows + IIS + ASP/ASP.NET) bylo, a želbohu nadále je, úkolem podstatně náročnějším, než činiti totéž na Linuxu (Apache + PHP). A to z hlediska finančního i technologického.

Finanční náročnost spočívá v ceně licencí. Web server sám je součástí operačního systému a není třeba platit víc, než cenu OS. Cena Windows 2000 Serveru se pohybovala okolo dvaceti tisíc a jisté ulehčení přinesl až celkem nedávno Windows 2003 Web Server. Háček se ale skrývá nikoliv v platformě pro web, ale v databázovém serveru.

Provozovat webovou aplikace bez databáze jest téměř nemožno a jedinou reálně v úvahu připadající databází je Microsoft SQL Server. Na ten potřebujete druhý stroj, s druhou licencí Windows Serveru (a to Standard Edition a vyšší) a zejména licenci SQL Serveru samotnou. Vzhledem k licenčním podmínkám potřebujete procesorovou licenci, která stojí bratru 80 000 za jeden procesor (a potřebujete dvě, protože na single proc server nemá snad ani cenu to SQLko instalovat).

Chcete-li tedy začít poskytovat hostingové služby na MS platformě, musíte z kapsy vytáhnout bezmála dvě sta tisíc jenom na licencích. Nepočítaje v to cenu mailového serveru (který potřebujete, protože provozovat hosting bez mailu nelze) a pro který vám Microsoft nic nenabídne.

Cena licencí pro hosting na Apache + PHP je pěkná kulaťoučká nula.

Pokud pro vás snad finance nejsou problém, užijete si problémů s technologií. Základem úspěchu u hostingové společnosti je kvalitní izolace jednotlivých zákaznických aplikací. Musíte zajistit, aby jeden neumětel svojí nekonečnou smyčkou neshodil všechny zákazníky, které na serveru hostujete. Musíte nastavit práva tak, aby se uživatelé nedostali, kam nemají. Nic takového IIS velmi dlouho neumělo. Nesmělé náznaky se objevily až ve verzi 5.0 a k reálné použitelnosti je dovedla až zatím poslední verze 6.0.

Provozovatelé hostingu tedy sahali k zoufalým řešením jako odstranění komponenty FileSystemObject (a tím možnosti práce se soubory vůbec) či jejímu nahrazení nějakým vlastním řešením pochybné dostupnosti, známosti, funkčnosti a kvality. Pro PHP je k dispozici speciálně navržený „safe mode“, pro ASP nic.

V tomto případě Microsoft poněkud zaspal, i pokud se týče automatizovatelné administrace, což je základem úspěchu pro jakýkoliv větší hosting. Skriptování pomocí ADSI a zápisů do díla Ďáblova jménem Metabáze představuje zábavu na dlouhé zimní večery. Zejména pak s ohledem na dokumentaci, o jejíchž kvalitách těžko hovořiti, aniž bychom se museli uchýlit k výrazům ve slušné společnosti obvykle neužívaným. Microsoft sice přišel s iniciativou jménem Microsoft Web Hoster Program, leč až v polovině letošního roku, což nelze nazvat právě včasností.

Důsledkem shora uvedené licenční politiky a technologických problémů je pro hostera poskytování služeb na platformě MS mnohem dražší, než v případě Linux + Apache + PHP. To se samozřejmě projevuje i na cenách pro koncové zákazníky. Hosting ASP/ASP.NET aplikací stojí měsíčně částky, za které je možno zaplatit PHP hosting na celý rok. Pro PHP existuje celá řada kvalitních a reálně použitelných free hostingů, pro ASP/ASP.NET nevím o jediném takovém.

To samozřejmě hraje roli i při rozhodování jakou technologii použít pro vývoj aplikací a jaké se profesně věnovat.

### Na výkonnosti nezáleží, aneb křivka naučení

Poslední zásadní nevýhodou technologie ASP.NET je velmi nepříznivá křivka učení. ASP.NET je velice mocný a výkonný nástroj, ale jeho zvládnutí si žádá čas a energii. Kromě shora zmiňované počáteční investice finanční je tedy třeba investovat i poměrně dost času, a to i na vytváření jednoduchých aplikací.

Napsat jednoduchou aplikaci v ASP nebo PHP je triviální. Jednoduchý chat, fotogalerii či publikační systém lze splácat snadno a s minimálními znalostmi. Pro PHP jsou shora uvedených aplikací zdarma k dispozici stovky, ba tisíce.

Napsat totéž v ASP.NET vyžaduje povědomost o objektově orientovaném programování a základech používané technologie obecně.

V počátečních fázích rozhodování, ke které technologii se přiklonit, hraje IMHO toto zásadní roli. Napsat jednoduchou aplikaci v PHP (byť z hlediska programátorských zásad špatnou a zbastlenou) je mnohem jednodušší, než udělat totéž v ASP.NET. Výhody platformy .NET se projeví až při tvorbě větších aplikací. To ale začátečníky nezajímá a pro pokročilé je už pozdě, když znají konkurenční technologii.

### Shrnutí současné situace

Současná situace (.NET 1.x) je pro Microsoft dosti neradostná. Jako začátečník jsem všemi prostředky odrazován od toho, abych se orientoval na .NET platformu. .NET je pro mne méně dostupný, dražší a hůře se k němu hledají začátečnické zdroje.

V tomto článku se orientuji pouze na racionální stránku uvažování. Tématem pro obsáhlou samostatnou studii jsou vlivy takříkajíc citové a společenské. Mezi (zejména začínajícími) webovými vývojáři patří fakticky k „dobrému tónu“ nemít rád Microsoft.

Ačkoliv Microsoft v posledních letech svou politiku výrazně změnil, názory mají velkou setrvačnost. V řadě dalších oborů se kromě toho Microsoft pohybuje stylem hrocha či spíše slona v porcelánu. Sice velmi efektivně dosahuje svého (a má zisky), páchá nicméně velké škody na své pověsti.

Je velmi těžké hájit barvy Microsoftu tváří v tvář čiročiré demagogii, kterou lze z úst zástupců Microsoftu slyšet na adresu open source projektů. Možná na ně mohou slyšet tradiční zákazníci společnosti, ale ve zde diskutované skupině působí kontraproduktivně. Když se mnohdy vaří krev i mně, dovedu si poměrně živě představit pocity těch, kdož již stojí na straně konkurence. Že stejně demagogické argumenty vycházejí i ze strany zástupců open source je sice okolnost polehčující, nikoliv však zprošťující.

## Přicházejí změny… Možná

Můžeme se zamýšlet nad tím, co Microsoft dělá (nebo by dělat měl) aby shora uvedené problémy minimalizoval či odstranil. Klíčovou otázkou ovšem je, má-li to smysl. Pozice Microsoftu na jeho tradičních trzích je vcelku pevná. Kroky vstřícnosti k „šedé zóně“ mezi nimi by mohly tuto pozici ohrozit a jest otázkou, zda to Microsoftu stojí za to.

Z té „šedé zóny“ ovšem vychází pro Microsoft velké nebezpečí. Konkurence se vylepšuje a postupně se začne rozšiřovat a ukusovat z dosud výsostných území Microsoftu. Velkou hrozbu dle mého názoru představuje firma Novell, která má pohlcením SuSe docela dobrou pozici k tomu, aby mohla poskytovat komplexní alternativu k MS produktům na bází Linuxu a dalších vlastních řešení.

Stejně tak firmy, které Microsoft nedávno veřejně označil za své konkurenty, pocházejí ze shora uvedené „šedé zóny“ a jsou s ní silně spjaty – zejména Google.

Dle mého názoru by tedy bylo od Microsoftu velmi nemoudré, kdyby tuto hrozbu podcenil a nereagoval na ni. Je však otázkou, zda na ni vůbec reagovat dokáže.

S více než šedesáti tisíci zaměstnanci a tržbami ve výši bezmála čtyřicet miliard dolarů se jedná o entitu, která se podobá spíše státu, než firmě. Kdyby byl Microsoft státem a porovnával své tržby s hrubým domácím produktem jednotlivých zemí, soupeřil by o šedesáté místo se zeměmi jako Kuvajt, Slovensko a Kazachstán (podle údajů Světové banky z 15. 07. 2005).

Tomu odpovídá též pružnost jednání a schopnost rychle reagovat a měnit své pozice a postoje – a také převádět proklamace svých představitelů na reálné činy.

V souvislosti s tím je také třeba si uvědomit, že možnosti české pobočky MS jsou dosti omezené. Nemohou měnit globální licenční a cenovou politiku a mají omezené lidské i finanční zdroje.

Nicméně necháme-li politiku stranou a budeme-li předpokládat, že Microsoft chce svou pozici mezi webovými ISV a začátečníky opravdu zlepšit, měl by se podle mého názoru zaměřit na odstranění třech výše zmiňovaných příčin, a to následujícími prostředky.

### Vývojové nástroje zdarma

Před několika hodinami uvolnil Microsoft ke stažení zdarma pro každého finální verzi „[Express](http://msdn.microsoft.com/vstudio/express/)“ edice svých vývojových nástrojů. To je samo o sobě výtečná zpráva: v betách jsem používal jak plnokrevné VS.NET, tak Express nástroje a z hlediska malého až středního vývojáře mezi nimi není rozdílu.

Uvolnění Express verzí byl od Microsoftu velmi odvážný – a řekl bych, že též velice moudrý – tah. Odvaha spočívá v tom, že Express edice jsou tak dobré, že dle mého názoru mohou výrazně ohrozit prodeje Visual Studia 2005. Ač jsou cíleny na začátečníky a „koníčkáře“, bohatě postačují i pro profesionální vývoj jednotlivců.

Ale ani zde Microsoft nemá vyhráno. V první řadě bude muset překonat stigma nepodařeného Web Matrixu a přesvědčit lidi, že Visual Web Developer Express není ořezaná demoverze, ale velmi silný a schopný vývojový nástroj. A kromě toho bude muset zůstat zdarma.

Předpokládám, že se ohledně bezplatné distribuce Express edic v Microsoftu odehrál tuhý vnitřní boj. Soudím tak dle toho, že téměř do poslední chvíle nebyla zcela jasná a oficiálně prohlášená licenční a cenová politika. Sice se „obecně mělo za to“, že Express bude ke stažení zdarma, ale prakticky až do poslední chvíle to nikdo neřekl závazně, veřejně a napevno, vždy s ústupovými cestičkami a důsledně „off-record“.

Výsledek je šalamounský: Express edice oficiálně není zdarma, stojí 59 amerických dolarů (na CD), ale jako časově omezenou promo akci si ho bude možno rok stáhnout bezplatně. Osobně jsem přesvědčen tomu, že se jedná o prostý záchvěv křečí v duchu „přece jim to fakt nedáme na věky zadarmo“ a že prakticky budou Express verze zdarma na věky věkův.

Jsem přesvědčen, že se bude opakovat historie s MSDE 2000: data engine SQL Serveru byl také nejprve k dispozici stylem chytré horákyně pouze s VS.NET, poté se seznam produktů postupně rozšiřoval a nakonec zábrany padly a MSDE je k dispozici volně pro každého. Jakmile jednou vypustíte kočku z pytle ven, jenom težko ji nacpete zase zpátky.

Ačkoliv jsem přesvědčen, že tato ústupová cestička nebude nikdy využita, může dle mého soudu hodně uškodit. Vývojáři budou nad sebou stále cítit ocelové čelisti myší pasti připravené zaklapnout, pokud nebudou mít jistotu, že základní vývojové nástroje budou pro .NET platformu zdarma dostupné obecně a do skonání světa.

V každém případě je dostupnost Express nástrojů velkým krokem kupředu.

### Dostupnější hosting

V oblasti dostupnosti hostingu se toho zatím moc nezměnilo. Alespoň v českých luzích a hájích ne. Jsou sice dostupné free hostingové firmy, ale pouze v rozsahu umožňujícím vyzkoušení technologie, nikoliv praktické použití.

V daném okamžiku ještě neznám detailně schopnosti SQL Serveru 2005 Express a nevím, zda bude (na rozdíl od MSDE 2000) použitelný i pro poskytovatele hostingových služeb a zda z jejich ramen sejme břemeno statisíců počáteční investice.

V každém případě, chce-li Microsoft uspět, musí kampaň zaměřenou na programátory doplnit i nabídkou pro hostery, aby bylo nové .NET aplikace kam dát. Je životně důležité, aby se zaměřil nejenom na „velkou trojku“, ale i na menší hostingové společnosti s pár servery a desítkami zákazníků. Zabírají v součtu významnou část trhu a často je používají komunitní „decision makeři“, protože nabízejí individuální přístup a pružnější spolupráci, než hostingoví giganti.

### Učit je, učit je, učit je

A konečně třetí oblastí, která bude pro úspěch Microsoftu kritická, je vzdělávání začátečníků. Je nutno jim jednoduchými slovy vysvětlit, že programování na platformě .NET 2.0 je dostupné, a hlavně že je to *zábavné*. Že budou moci jednoduché aplikace vytvářet snadno a rychle, a to v souladu s moderními trendy web designu.

Pokud se týče schopností technologie samé, má Microsoft velmi dobrou pozici. Technologická úroveň ASP.NET 2.0 je neporovnatelná s jakoukoliv konkurenční technologií a zejména s PHP. I zatvrzelí a letití programátoři v PHP byli zaujati, když jsem jim o nové technologii vyprávěl a byli odhodláni ji alespoň letmo vyzkoušet.

Jde o to, zda Microsoft dokáže tyto lidi oslovit, a zda tak dokáže učinit jejich jazykem. Velmi snadno se dá sklouznout do prázdných klišé a marketingových frází – a ty zase naopak sklouznou po cílové skupině, aniž by zanechaly jakýkoliv pozitivní dojem.

Jenom pozvolna u nás Microsoft proniká do akademických kruhů. Vysokoškolské studenty oslovuje velmi namáhavě, a obávám se, že svým způsobem i zbytečně. Ona namáhavost spočívá v tom, že akademické prostředí obecně a u nás zejména je tradičně vůči Microsoftu naladěno dosti nepřátelsky a na jakoukoliv jeho aktivitu hledí s jistým podezřením. Důležitější je ovšem ona zbytečnost. Podle mého názoru je totiž pozdě oslovovat programátory až na vysoké škole.

Podle mých zkušeností velká část webových vývojářů začíná psát weby a aplikace už ve věku spíše středoškolském, řekněme 15–18 let a chce-li Microsoft mít se svou technologií úspěch, musí je oslovit právě v této fázi a v tomto věku. To s sebou ovšem nese řadu problémů, které Microsoft není zvyklý řešit.

Ono úvodní seznámení je – dle mého názoru – vhodné uskutečnit osobně a nebo alespoň video záznamem, psaným textem nelze dynamické schopnosti nové technologie dostatečně předvést. V případě že bude chtít Microsoft uspořádat semináře pro tuto cílovou skupinu, musí změnit styl, jakým podobné věci vede.

Klíčový je termín a místo. Pro středoškoláka je téměř nemožné navštívit celodenní seminář v pracovní den. Je tedy nutné akce pořádat buďto o víkendu a nebo mimo dobu školního vyučování. Rovněž místo hraje svou roli, protože cestovat přes půl republiky do Prahy nebo Brna není problém pro profesionála, ale pro šestnáctiletého kluka, který musí žádat rodiče o souhlas a jízdenku si zaplatit z kapesného, ano.

Stejně tak obvyklé Microsoftí symbolické vstupné 500 Kč, z hlediska profesionálního vývojáře (potažmo jeho zaměstnavatele) zanedbatelné, představuje pro našeho modelového studenta-začátečníka-koníčkáře podstatný výdaj.

Ze strany českého Microsoftu jsem zatím příliš významnou relevantní aktivitu nezaznamenal. Existují sice české starter kity, provozované ve spolupráci s mým webem ASPNET.CZ ([http://starterkit.aspnet.cz](http://starterkit.aspnet.cz/)) a soutěž [LCD za web](http://www.lcdzaweb.cz/), ale podle mého soudu se jedná o projekty až druhého sledu: nejprve je nutno lidi přesvědčit, že věc stojí za pozornost a pak teprve jim dávat ukázky.

Velice záslužným počinem z globálního hlediska je projekt [MSDN Coding 4 Fun](http://msdn.microsoft.com/coding4fun/), kde jsou nabízeny jednoduché a zábavné aplikace realizované prostřednictvím .NET 2.0 a Express nástrojů.

## Závěrem

Článek, který jste právě dočetli, představuje souhrn mých osobních názorů na současnou situaci ohledně šancí technologie ASP.NET 2.0 uspět na trhu malých a středních zákazníků. Tyto názory vycházejí ze zkušeností, které jsem získal během osmi let, po které se živím vývojem a hostingem webových aplikací, a zejména během cca. tří let, po které provozuji weby ASP.CZ resp. ASPNET.CZ, které jsou určeny právě cílové skupině začátečníků.

Chce-li Microsoft na tomto poli uspět, čeká ho velice těžká práce, jejíž efekt se navíc projeví pouze pomalu. Bude muset bojovat nejenom proti pevně zakořeněným předsudkům z minulosti, ale též na dosud neznámém poli, bude muset komunikovat se zákazníky, jejichž existenci dosud téměř nevnímal.

Nejzásadnější ale bude, že Microsoft bude muset bojovat sám se sebou, protože úspěch ve shora uvedených oblastech bude znamenat jisté popření dosavadních zásad a ohrožení dosud pevně zastávaných pozic. S trochou nadsázky a smyslu pro romantiku lze říci, že úspěch největší softwarové společnosti na světě v tomto oboru závisí na tom, zda dokáže překročit svůj stín.
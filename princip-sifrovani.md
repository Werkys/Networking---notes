Text "Princip šifrování -- MiS" se zaměřuje na objasnění a porovnání různých metod šifrování, přičemž zdůrazňuje rozdíl mezi kódováním a šifrováním1.

Rozdělení šifrovacích metod2:

Symetrické šifrovací metody: Odesilatel i příjemce používají společný šifrovací klíč pro zašifrování i dešifrování zprávy23.

Asymetrické šifrovací metody: Každý účastník je identifikován dvojicí klíčů -- soukromým a veřejným23.

◦

Soukromý klíč zná pouze vlastník23.

◦

Veřejný klíč smí znát kdokoli23.

◦

Zpráva zašifrovaná veřejným klíčem lze dešifrovat pouze soukromým klíčem a naopak23.

Porovnání vlastností23:

Symetrické metody:

◦

Jsou výpočetně méně náročné3.

◦

Při komunikaci na dálku vzniká problém s bezpečným předáním klíče, pokud se účastníci nemohou setkat osobně3. Klíč by měl být dostatečně dlouhý, náhodný a použit pouze jednou3.

Asymetrické metody:

◦

Dokáží zajistit nepopiratelnost odeslání zprávy (autor zprávy nemůže popřít její odeslání)2.

◦

Ulehčují problém s bezpečným předáním klíče potenciálně nebezpečnou sítí, protože nevadí odposlechnutí veřejného klíče třetí osobou, je jen třeba zabránit podvržení falešného klíče24.

◦

Jedna kombinace veřejného a soukromého klíče stačí pro komunikaci s libovolným počtem partnerů2.

◦

Každý účastník zodpovídá za svůj soukromý klíč, není zde sdílená zodpovědnost za jeho vyzrazení2.

Zabezpečení asymetrickými metodami56:

Proti přečtení zprávy: Odesilatel šifruje zprávu příjemcovým veřejným klíčem. Taková zpráva lze rozšifrovat pouze příjemcovým soukromým klíčem5.

Proti přečtení zprávy a zároveň proti podvržení falešné zprávy: Odesilatel může zprávu zašifrovat příjemcovým veřejným klíčem a navíc i svým soukromým klíčem. Příjemce pak zprávu dešifruje odesilatelovým veřejným klíčem a svým soukromým klíčem5. Útočník nemůže zprávu zfalšovat, protože by musel znát odesilatelův soukromý klíč5.

Možné útoky:

◦

Pokud jsou veřejné klíče vyměněny spolehlivou cestou (např. osobně), je útok velmi obtížný. Zbývá hledat chyby v šifrovacích programech nebo útok hrubou silou6.

◦

Problematická je výměna veřejných klíčů přes nezabezpečenou síť, kde může útočník provést útok man-in-the-middle podsunutím vlastního veřejného klíče6.

◦

V praxi se k předávání klíčů používají certifikační autority6.

Běžné využití4:

Asymetrické metody se obvykle využívají pro bezpečné předání symetrického šifrovacího klíče nebo otisku zprávy4.

Šifrování většího objemu dat se následně provádí symetrickými šifrovacími metodami, protože jsou výpočetně efektivnější4.

TLS (dříve SSL) je vrstva pro šifrovanou komunikaci, typicky používaná pro šifrovaný přenos dat protokolu HTTP (https://...)4.

Příklady šifrovacích algoritmů78:

Symetrické:

◦

DES (Data Encryption Standard) -- dnes již nedostatečné kvůli krátkému klíči (56 bitů)7.

◦

AES (Advanced Encryption Standard, též Rijndael) -- přijatý americkým NIST jako standard, délky klíče 128, 192 nebo 256 bitů7. Zmiňovány jsou také Serpent a Twofish8.

Asymetrické:

◦

RSA (Rivest, Shamir, Adleman) -- základ protokolu SSL, matematický princip je založen na násobení velkých prvočísel8.

Historické šifry910:

Césarova šifra: Posun každého písmena zprávy o zadaný počet v abecedě9.

Vigenèrova šifra (1556) a Šifra Playfair (1854)9.

Vernamova šifra (1917): Podobný princip jako Césarova šifra, ale každé písmeno se posune o jiný počet znaků (klíč je stejně dlouhý jako zpráva a dokonale náhodný). Je neprolomitelná, pokud jsou dodržena pravidla, což dokázal Shannon v roce 1949. Problémem je však předání klíče9.

Enigma (1918): Originální verze prolomena ve 30. letech 20. století. Prolomení pokročilejší verze pomohlo vítězství ve 2. světové válce a na vývoji výpočetních strojů pro prolomení se podílel Alan Turing10.

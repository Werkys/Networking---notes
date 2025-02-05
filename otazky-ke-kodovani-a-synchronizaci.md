# Kontrolní otázky ke kódování a synchronizaci
## 1. Vysvětlete pojmy: <br>
**bitová synchronizace** je proces, při kterém přijímač v komunikačním systému správně rozpoznává jednotlivé bity přenášeného digitálního signálu. Zajišťuje, že přijímač správně určuje začátky a konce bitů, což je klíčové pro správné dekódování přenášených dat. <br>

**kódování** je proces převodu informace do specifické formy, která je vhodná pro přenos, ukládání nebo zpracování. Používá se v telekomunikacích, počítačových vědách i datové kompresi. <br>

**signalizace** je proces přenosu řídicích a stavových informací mezi zařízeními v telekomunikačních a počítačových sítích. Umožňuje navázání, řízení a ukončení komunikace. <br>

### podrobnější vysvětlení: 

### a) Jak funguje bitová synchronizace?

- **Nutnost přesného časování** – Přijímač musí přesně vědět, kdy začíná a končí každý bit.  
- **Metody synchronizace**:  
  - **Externí hodinový signál (synchronní přenos)** – Používá se společný hodinový signál mezi vysílačem a přijímačem.  
  - **Obnova hodinového signálu (asynchronní přenos)** – Přijímač rekonstruuje časování z přijatého signálu pomocí:  
    - **Fázového závěsu (PLL - Phase-Locked Loop)**  
    - **Synchronizačních bitů** (např. start a stop bity v sériové komunikaci)  
    - **Speciálního kódování** (např. Manchester kódování)  

Bez správné bitové synchronizace by docházelo k chybné interpretaci přenášených dat, což by vedlo k nesprávné komunikaci mezi zařízeními.

### b) Typy kódování  

1. **Zdrojové kódování** – Redukuje nadbytečnost v datech (např. komprese ZIP, MP3).  
2. **Řádkové kódování** – Převádí digitální data na signál vhodný pro přenos (např. Manchester kód).  
3. **Kanalové kódování** – Přidává redundantní bity pro detekci a opravu chyb (např. Hammingův kód, Reed-Solomon).  
4. **Šifrování** – Převádí data do zabezpečené podoby (např. AES, RSA).  

Správné kódování zajišťuje efektivní a spolehlivou komunikaci mezi zařízeními.

### c) Typy signalizace  

1. **Linková signalizace** – Řídí fyzické spojení mezi dvěma zařízeními (např. přenos start/stop bitů v sériové komunikaci).  
2. **Kanalová signalizace** – Používá samostatné kanály pro řídicí informace (např. SS7 v telefonních sítích).  
3. **Signálová signalizace** – Přenáší informace v rámci stejného kanálu jako data (např. DTMF tóny v telefonii).  
4. **Optická nebo vizuální signalizace** – Světelné nebo vizuální signály (např. semafory, LED indikátory).  

Signalizace je klíčová pro správné fungování komunikačních systémů, umožňuje efektivní přenos dat i řízení sítě. <br>
<br>

## 2. Co jsou „fyzikální parametry rozhraní a médií“?  

**Fyzikální parametry rozhraní a médií** určují vlastnosti přenosového prostředí a hardwarových rozhraní používaných pro komunikaci v počítačových a telekomunikačních sítích. Tyto parametry ovlivňují rychlost, kvalitu a spolehlivost přenosu dat.  

## Příklady fyzikálních parametrů  

1. **Typ přenosového média**  
   - Metalické kabely (např. kroucená dvojlinka, koaxiální kabel)  
   - Optická vlákna (single-mode, multi-mode)  
   - Bezdrátové přenosy (rádiové vlny, infračervené, mikrovlnné spoje)  

2. **Elektrické vlastnosti** (pro metalická média)  
   - Impedance kabelu (např. 50 Ω u koaxiálního kabelu)  
   - Útlum signálu (měřený v dB na jednotku délky)  
   - Maximální přenosová vzdálenost  

3. **Optické vlastnosti** (pro optická vlákna)  
   - Vlnová délka světla (850 nm, 1310 nm, 1550 nm)  
   - Tlumení signálu v dB/km  
   - Číselná apertura vlákna  

4. **Frekvenční pásmo a šířka pásma**  
   - Ethernetové standardy (např. 100BASE-TX využívá 100 MHz, 10GBASE-T až 500 MHz)  
   - Wi-Fi pásma (2,4 GHz, 5 GHz, 6 GHz)  

5. **Konektory a fyzická rozhraní**  
   - RJ-45 pro ethernet  
   - SC, LC, ST pro optické kabely  
   - SMA, BNC pro koaxiální spoje  

Správná volba fyzikálních parametrů je klíčová pro optimalizaci výkonu a spolehlivosti komunikačních systémů.  


## 3. Vysvětli, jak se kóduje 0 a 1 v uvedených kódováních.

V různých přenosových technologiích se bity **0** a **1** kódují odlišným způsobem, aby byl zajištěn spolehlivý přenos dat.  

#### a) NRZ (Non-Return to Zero)  
- **0** – Nízká úroveň napětí (např. 0 V)  
- **1** – Vysoká úroveň napětí (např. 5 V)  
- Nevýhoda: Dlouhá sekvence stejných bitů může vést ke ztrátě synchronizace.  

#### b) NRZI (Non-Return to Zero Inverted)  
- **0** – Žádná změna signálu  
- **1** – Změna úrovně (z nízké na vysokou nebo naopak)  
- Používá se např. v USB komunikaci.  

#### c) Manchester kódování  
- **0** – Přechod z vysoké úrovně na nízkou (1 → 0) uprostřed bitového intervalu  
- **1** – Přechod z nízké úrovně na vysokou (0 → 1) uprostřed bitového intervalu  
- Výhoda: Zajišťuje zabudovanou synchronizaci hodin.  

#### d) Diferenciální Manchester  
- **0** – Změna signálu na začátku bitového intervalu  
- **1** – Žádná změna na začátku, ale vždy změna uprostřed bitového intervalu  
- Používá se v protokolu Token Ring.  

#### e) 4B/5B kódování  
- Každé 4 datové bity jsou nahrazeny 5bitovým kódem, který nemá dlouhé sekvence nul  
- **Příklad kódování:**  
  - `0000` → `11110`  
  - `0001` → `01001`  
- Používá se v Fast Ethernetu (100BASE-TX).  

#### e) Bipolární kódování (AMI – Alternate Mark Inversion)  
- **0** – Žádný signál (neutrální)  
- **1** – Střídavě kladná a záporná úroveň napětí (+V, -V, +V, -V…)  
- Výhoda: Zajišťuje rovnováhu signálu a umožňuje detekci chyb.  

Každé z těchto kódování má své výhody a je vhodné pro různé komunikační technologie a aplikace. 


## 4. Zakresli graf průběhu signálu při vysílání posloupnosti: 10011010 při použití:
### 4B5B (signalizace NRZ)

v příloze (nevím jak to sem dát) 

## 5. Srovnání výhod a nevýhod způsobů kódování: Manchester, NRZ a 4B/5B

### a) **Manchester kódování**
   - **Popis**: Manchester kódování používá přechod na střední úrovni signálu k reprezentaci bitů. Bit "1" je reprezentován přechodem z vysoké na nízkou hodnotu, a bit "0" přechodem z nízké na vysokou hodnotu.

   - **Výhody**:
     - **Self-synchronization**: Díky pravidelným přechodům signálu je možné synchronizovat vysílané data bez potřeby externího hodinového signálu.
     - **Vysoká odolnost vůči šumu**: Díky častým přechodům je kódování robustní proti šumu, což zajišťuje vysokou spolehlivost přenosu.
     - **Snadná detekce chyb**: Přítomnost přechodů usnadňuje detekci chyb v přenosu dat.

   - **Nevýhody**:
     - **Nízká účinnost pásma**: Při přenosu signálu je potřeba vyšší šířka pásma, protože každý bit je reprezentován více než jedním přechodem.
     - **Vyšší energetické nároky**: Vysílání častých přechodů může zvyšovat spotřebu energie, což je nevýhodné v energeticky citlivých aplikacích.

### b) **NRZ (Non-Return-to-Zero) kódování**
   - **Popis**: V NRZ kódování je úroveň signálu konstantní po celý čas, během kterého je přenášen jeden bit. Bit "1" je reprezentován vysokým napětím a bit "0" nízkým napětím.

   - **Výhody**:
     - **Vysoká efektivita pásma**: Každý bit je reprezentován jednou změnou signálu, což zajišťuje efektivní využití šířky pásma.
     - **Nízká spotřeba energie**: NRZ kódování může mít nižší energetické nároky, protože přechody mezi hodnotami se vyskytují méně často než u Manchester kódování.
     
   - **Nevýhody**:
     - **Problémy s synchronizací**: Pokud jsou v datovém přenosu dlouhé sekvence nul nebo jedniček, může být obtížné synchronizovat vysílaný signál, což vede k riziku ztráty synchronizace.
     - **Nízká odolnost vůči šumu**: Bez častých přechodů může být signál náchylný k chybám a šumu.

### c) **4B/5B kódování**
   - **Popis**: 4B/5B kódování je technika, kde každé 4 bity dat jsou reprezentovány 5 bity, čímž se zajišťuje minimální počet přechodů a dostatečná synchronizace. Tento způsob kódování je často používán v kombinaci s jinými způsoby kódování, jako je NRZ.

   - **Výhody**:
     - **Zajištění synchronizace**: 4B/5B kódování přidává redundantní bity pro zajištění správné synchronizace mezi vysílatelem a přijímačem.
     - **Odolnost vůči chybám**: Tento způsob kódování zajišťuje, že se ve vysílaném signálu nevyskytují dlouhé sekvence nul nebo jedniček, což zvyšuje odolnost vůči šumu.
     - **Vysoká účinnost pásma**: Při přenosu 4 bity je používáno pouze 5 bitů, což zajišťuje efektivní využití šířky pásma.

   - **Nevýhody**:
     - **Zvýšení počtu bitů**: Každé 4 bity dat jsou kódovány do 5 bitů, což znamená, že šířka pásma je o něco vyšší než u původního přenosu dat.
     - **Složitost implementace**: Implementace 4B/5B kódování může být složitější než u jednodušších metod, což může zvýšit náklady a složitost systému.
    
## 6. Co označuje synchronizace?

**Synchronizace** v oblasti digitálního přenosu dat označuje proces zajištění, že vysílané a přijímané signály mají stejný časový rámec, což umožňuje správnou interpretaci přenášených informací.


## 7. Proč nelze využít pro synchronizaci hodinový signál na samostatném vodiči?

Využití samostatného vodiče pro přenos hodinového signálu pro synchronizaci přenosu dat má několik nevýhod a omezení, zejména v moderních komunikačních systémech:

### a) **Vyšší náklady a složitost**
   - **Popis**: Použití samostatného vodiče pro hodinový signál znamená potřebu dalšího fyzického vedení (drátu, kabelu), což zvyšuje náklady na hardware a složitost celého systému. V dnešních komunikačních technologiích je preferováno minimalizovat počet vodičů, aby se zjednodušila instalace a snížila cena zařízení.
   
### b) **Prostorová náročnost**
   - **Popis**: Další vodič pro hodinový signál znamená více prostoru na desce plošných spojů a ve kabelových systémech, což není praktické ve vysoce integrovaných systémech, kde je každý vodič a každý centimetr prostoru důležitý.

### c) **Interferencí a šum**
   - **Popis**: Přenos hodinového signálu na samostatném vodiči může způsobit interferenci nebo šum mezi datovým signálem a hodinovým signálem, což může vést k chybám v přenosu nebo zhoršení kvality signálu.

## Jak jinak můžeme postupovat?

Pro zajištění synchronizace v případě, že není možné použít samostatný hodinový signál, existují alternativní metody:

### a) **Self-synchronization (Vlastní synchronizace)**
   - **Popis**: Některé kódovací metody, jako je **Manchester kódování** nebo **4B/5B kódování**, jsou navrženy tak, že přechody v signálu poskytují dostatečné informace pro synchronizaci mezi vysílačem a přijímačem, bez potřeby externího hodinového signálu.
   - **Výhody**: Synchronizace je zajištěna přímo v přenášených datech, což eliminuje potřebu samostatného hodinového signálu.
   - **Příklad**: V Manchester kódování každý bit je reprezentován změnou stavu signálu, což zajišťuje pravidelnou změnu, která může být použita k synchronizaci.

### b) **Data encoding with timing information (Kódování dat s časovými informacemi)**
   - **Popis**: Kódování dat s časovými informacemi zahrnuje přenos specifických bitů, které označují začátek a konec určitého časového okna nebo rámce. To umožňuje příjemci určit správné časování, i když přenos neobsahuje samostatný hodinový signál.
   - **Příklad**: **8B/10B kódování**, které přidává redundantní bity pro zajištění správné synchronizace.

### c) **Clock Recovery (Obnova hodin)**
   - **Popis**: V některých systémech je možné obnovit hodinový signál z přenášených dat. Tato technika je známá jako "clock recovery" a spočívá v extrakci hodinového signálu z datového proudu, který má dostatek přechodů pro správné určení časování.
   - **Výhody**: Tato metoda eliminují potřebu externího hodinového signálu a umožňuje přenos dat po jediném vodiči.

Tyto metody jsou často využívány ve vysokorychlostních komunikačních systémech, jako je Ethernet nebo optická vlákna, kde jsou náklady, prostor a složitost problémem.




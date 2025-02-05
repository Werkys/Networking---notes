# Kontrolní otázky ke kódování a synchronizaci
## 1. Vysvětlete pojmy: <br>
**bitová synchronizace** je proces, při kterém přijímač v komunikačním systému správně rozpoznává jednotlivé bity přenášeného digitálního signálu. Zajišťuje, že přijímač správně určuje začátky a konce bitů, což je klíčové pro správné dekódování přenášených dat. <br>

**kódování** je proces převodu informace do specifické formy, která je vhodná pro přenos, ukládání nebo zpracování. Používá se v telekomunikacích, počítačových vědách i datové kompresi. <br>

**signalizace** Signalizace je proces přenosu řídicích a stavových informací mezi zařízeními v telekomunikačních a počítačových sítích. Umožňuje navázání, řízení a ukončení komunikace. <br>

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

![alt text](http://url/to/img.png)





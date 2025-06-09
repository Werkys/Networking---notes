# Princip šifrování – MiS

Tento text se zaměřuje na objasnění a porovnání různých metod šifrování a zdůrazňuje rozdíl mezi **kódováním** a **šifrováním¹**.

audio rozbor: [principsifrovani.notebooklm]([https://notebooklm.google.com/notebook/da582efa-3fe9-4fd2-8339-bef62f4eacfc/audio](https://notebooklm.google.com/notebook/1332e772-f031-4f86-a214-169396b8f1ba/audio))

---

## 🧩 Rozdělení šifrovacích metod

### 🔐 Symetrické šifrovací metody
- Odesilatel i příjemce používají **společný klíč** pro šifrování i dešifrování zprávy.

### 🔑 Asymetrické šifrovací metody
Každý účastník má **dvojici klíčů**:
- **Soukromý klíč** – zná pouze vlastník.
- **Veřejný klíč** – může znát kdokoli.
- Zpráva šifrovaná veřejným klíčem lze dešifrovat pouze soukromým klíčem (a naopak)²³.

---

## ⚖️ Porovnání vlastností

### ✔️ Symetrické metody
- Výpočetně **méně náročné³**.
- **Problém s předáním klíče** na dálku, pokud není možný osobní kontakt³.
- Klíč by měl být **dlouhý, náhodný a použit jen jednou³**.

### ✔️ Asymetrické metody
- Zajišťují **nepopiratelnost odeslání zprávy²**.
- Řeší bezpečné předání klíče, i přes **nezabezpečenou síť²⁴**.
- **Jedna klíčová dvojice** umožňuje komunikaci s více partnery².
- Každý účastník **zodpovídá za svůj soukromý klíč²**.

---

## 🛡️ Zabezpečení asymetrickými metodami

- **Proti přečtení zprávy:**  
  Zpráva je šifrována příjemcovým **veřejným klíčem**, dešifruje ji pouze jeho **soukromý klíč⁵**.

- **Proti přečtení i podvržení:**  
  Zpráva je šifrována příjemcovým veřejným klíčem **a** odesilatelovým **soukromým klíčem**.  
  Příjemce dešifruje pomocí odesilatelova **veřejného klíče** a svého **soukromého klíče⁵**.  
  Útočník nemůže zprávu zfalšovat, protože **nezná soukromý klíč odesilatele⁵**.

---

## ⚠️ Možné útoky

- **Spolehlivá výměna klíčů** (např. osobně) výrazně snižuje riziko.
- **Útok typu man-in-the-middle:**  
  Útočník podstrčí vlastní veřejný klíč při výměně přes nezabezpečenou síť.
- Řešení: **certifikační autority** pro ověřenou výměnu klíčů.

---

## 💡 Běžné využití

- **Asymetrické metody** slouží k bezpečnému předání:
  - Symetrického klíče
  - Otisku zprávy (hash)
- Pro **šifrování většího objemu dat** se používají **symetrické metody**, protože jsou rychlejší.
- **TLS (dříve SSL)** je běžná šifrovací vrstva používaná např. pro protokol **HTTPS**.

---

## 🔢 Příklady šifrovacích algoritmů

### Symetrické algoritmy:
- **DES (Data Encryption Standard)**  
  – dnes již nedostatečný (56bitový klíč)⁷.
- **AES (Advanced Encryption Standard / Rijndael)**  
  – standard NIST, délky klíče 128, 192 nebo 256 bitů⁷.
- **Serpent, Twofish** – alternativy k AES⁸.

### Asymetrické algoritmy:
- **RSA (Rivest–Shamir–Adleman)**  
  – základ SSL/TLS, založen na násobení velkých prvočísel⁸.

---

## 🕰️ Historické šifry

- **Césarova šifra:**  
  Posun každého písmene o pevný počet míst v abecedě⁹.

- **Vigenèrova šifra (1556)**, **Šifra Playfair (1854)**⁹.

- **Vernamova šifra (1917):**  
  Klíč stejně dlouhý jako zpráva, dokonale náhodný.  
  **Neprolomitelná** při správném použití (dle Shannona, 1949)⁹.

- **Enigma (1918):**  
  Prolomena ve 30. letech, klíčová ve 2. světové válce.  
  Na jejím prolomení se podílel **Alan Turing¹⁰**.

---

### 📚 Poznámky
¹ Rozdíl mezi kódováním a šifrováním  
²–¹⁰ Odkazy na zdroje dle originální dokumentace

# ISS – Projekt: Music Search (MIR)

Riešenie projektu z predmetu ISS (Signály a systémy) na FIT VUT.

## Obsah úlohy
- **Music Information Retrieval (MIR)** – implementácia systému na rozpoznávanie hudobných úryvkov (štýl Shazam).
- **Spracovanie audia** – analýza `.wav` súborov (16 kHz) a tvorba spektrogramov.
- **Matica podobnosti** – algoritmus na porovnávanie neznámych nahrávok so sadou známych skladieb.
- **Dve implementácie** – optimalizovaná lokálna verzia a edukačná verzia pre Google Colab.

Projekt bol vytvorený výlučne na vzdelávacie účely.

## Hodnotenie
- Získané body: **18 / 18**

## Štruktúra a spustenie

V repozitári sa nachádzajú dve verzie riešenia. Z dôvodu limitu veľkosti súborov (50 MB) **nie sú** súčasťou repozitára zvukové dáta (`valid`, `known`, `xblizna00`).

### 1. Verzia: Lokálne Python (Rýchlejšia)
Táto verzia je optimalizovaná na rýchlejšie dosiahnutie výsledkov. Kód je stručnejší a menej komentovaný.

* **Umiestnenie:** Priečinok `./Lokalne-python/`
* **Požiadavky:** Python 3
* **Príprava:**
    1.  Stiahnite zvukové sady (`valid`, `known`) a sadu (`xblizna00`).
    2.  Vložte ich priamo do priečinka `./Lokalne-python/`.
* **Spustenie:**
    ```bash
    cd Lokalne-python
    python3 main.py
    ```
* **Výstup:** Súbor s výsledkami `eval.txt` a protokol.

### 2. Verzia: Google Colab (Komentovaná)
Táto verzia slúži na edukačné účely, obsahuje detailné komentáre a vysvetlenia postupu.

* **Umiestnenie:** Priečinok `./Google-Colab/`
* **Obsah:**
    * Odkaz na Jupyter Notebook ("Program").
    * Výsledný `eval.txt`.
    * Finálny protokol.

---

<details>
<summary><b>Zobraziť kompletné zadanie (ISS 2025/26)</b></summary>

### Úvod
Skoro každý už niekedy použil aplikácie na vyhľadávanie hudby (Music Information Retrieval, MIR) - Shazam a podobné. V tomto projekte si jednoduchú MIR aplikáciu naprogramujete na základe toho, čo ste sa naučili v ISS.

### Dáta a cieľ riešenia
Budeme pracovať s WAV súbormi (1 kanál, vzorkovacia frekvencia 16 kHz):
- **known.zip** – 706 desaťsekundových známych klipov.
- **valid.zip** – 50 testovacích päťsekundových klipov s kľúčom.
- **login.zip** – 50 evaluačných päťsekundových klipov (váš login).

**Cieľ:** Vytvoriť a okomentovať funkciu `compute_similarity_matrix`.
- **Vstup:** 50 neznámych nahrávok.
- **Výstup:** Matica 50x706 udávajúca podobnosť k 706 známym nahrávkam (väčšie číslo = väčšia podobnosť).

### Spôsob vypracovania
- Jazyk: Python (odporúčané), Matlab, C, Java, a iné.
- Zákaz externých cloudových služieb na rozpoznávanie.
- Projekt sa nezameriava na "krásu kódu", ale na funkčnosť a pochopenie princípu.

### Odporúčané postupy
- Parametrizácia signálov pomocou **spektrogramu** (pozor: známe signály majú 10s, neznáme 5s + šum).
- Použitie iba amplitúdovej zložky spektra.
- Normalizácia (napr. priemerným spektrom).
- Metódy porovnania: korelácia, prispôsobené filtrovanie, detekcia maxím (a la Shazam).

### Odovzdanie
1. **Protokol (PDF):** Odôvodnenie riešenia, popis implementácie, výsledky na validačnej sade, grafy/obrázky.
2. **Program:** Zdrojový kód (alebo odkaz na Colab).
3. **Výsledok (eval.txt):** Textový súbor s maticou podobnosti pre finálne skórovanie.

</details>

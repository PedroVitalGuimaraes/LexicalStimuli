# Lexical Stimuli Selection
A Python script to select and organize words drawn from the **Porlex v3** lexical database.

## Steps

1. Reads the `Porlex_v3_2019.xlsx` file (sheet `Porlex_v3`).
2. Filters the words that simultaneously meet:
   - `Nlet` (number of letters) between **7 and 10**
   - `CGram` (grammatical class) in **Adjective, Verb, Noun**
   - `FreqL` (lexical frequency) between **38 and 62**
3. Renames the variables:
   - `CGram` → **Grammatical Class (G)**
   - `Nlet` → **Length (C)**
   - `FreqL` → **Frequency (F)**
4. Randomly selects **80 words** (fixed seed = 42, for reproducibility).
5. Splits the 80 words into 2 lists of 40:
   - **Target Words**
   - **Distractor Words**
6. Each list of 40 is split into 2 groups of 20:
   - Target Words → **L1** and **L1A**
   - Distractor Words → **L2** and **L2A**
7. **L1** and **L1A** are further split into 4 blocks of 5 words each, **Block 1 to Block 8**.
8. For **L2**, **L2A** and **Blocks**, the following is calculated:
   - Mean and standard deviation of **Length**
   - Mean and standard deviation of **Frequency**
   - Distribution of grammatical classes, in the order **Verb, Noun, Adjective**

## Libraries
- **Pandas**
- **Statistics**

## Usage

1. Place the [Porlex_v3_2019.xlsx](https://projetoler.pt/texto/porlex) directory.
2. Run:

```bash
python select_stimuli.py
```

## Generated files

| File | Content |
|---|---|
| `filtered_words.csv` | All words that meet the filtering criteria |
| `selected_words_80.csv` | The 80 randomly selected words |
| `target_words_40.csv` | The 40 Target Words |
| `distractor_words_40.csv` | The 40 Distractor Words |
| `L1_blocks.txt` | L1 split into Blocks 1–4 |
| `L1A_blocks.txt` | L1A split into Blocks 5–8 |
| `L2_blocks.txt` | L2 split into Blocks 1–4, with statistics per block |
| `L2A_blocks.txt` | L2A split into Blocks 5–8, with statistics per block |

## References

Gomes, I., Castro, S. L., Lima, C. F., & Mesquita, A. B. (2019). *Porlex v3, uma base lexical do Português*. FPCE-UP. \
https://projetoler.pt/texto/porlex

Guimarães, P. V. (2022). ***O papel moderador da extroversão no efeito da música na memória episódica***. [Dissertação de Mestrado, Universidade do Porto]. Repositório Aberto da Universidade do Porto.
[doi:10.34626/ethm-n129](https://doi.org/10.34626/ethm-n129)



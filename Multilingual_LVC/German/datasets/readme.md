# LVC Sentence Datasets — German

The German LVC sentence dataset contains:
- Active sentences dataset
- Passive sentences dataset

This folder contains automatically generated German sentence datasets based on **Light Verb Constructions (LVCs)** and corresponding **full-verb (non-collocational) controls**. The sentences are generated from verb–noun items and short contextual expressions, allowing the same verbs to be compared in collocational and literal uses.
Scripts to to reproduce the generation of this dataset and to produce sentences with nominal subjects are contained in Sentence generation. 

## Verb inventory

The source file, `collocation_items_DE_clean_utf8.csv`, has **292 verb–noun items** for five German verbs. 
The `collocation` column distinguishes LVCs (`T`) from concrete full-verb controls (`F`).

| German verb | Collocation objects | Full-verb control objects | Total |
|---|---:|---:|---:|
| **erhalten** | 20 | 20 | 40 |
| **geben** | 25 | 25 | 50 |
| **haben** | 50 | 60 | 110 |
| **machen** | 28 | 50 | 78 |
| **nehmen** | 4 | 10 | 14 |
| **Total** | **127** | **165** | **292** |

## File structure
### Active sentences with pronominal subjects

The active files use **sie** ('they', plural) as the subject, with a preceding time expression and, optionally, an adverb.

- LVC_DE_active_future_no_adverbs.csv — Futur I, without adverbs. Example: Anfang Januar werden sie einen Fehler machen.
- LVC_DE_active_future_with_adverbs.csv — Futur I, with adverbs. Example: Anfang Januar werden sie anscheinend einen Fehler machen.
- LVC_DE_active_present_perfect_no_adverbs.csv — Perfekt, without adverbs. Example: Anfang Januar haben sie einen Fehler gemacht.
- LVC_DE_active_present_perfect_with_adverbs.csv — Perfekt, with adverbs. Example: Anfang Januar haben sie anscheinend einen Fehler gemacht.
- LVC_DE_active_past_perfect_no_adverbs.csv — Plusquamperfekt, without adverbs. Example: Anfang Januar hatten sie einen Fehler gemacht.
- LVC_DE_active_past_perfect_with_adverbs.csv — Plusquamperfekt, with adverbs. Example: Anfang Januar hatten sie anscheinend einen Fehler gemacht.

### Passive sentences
The passive dataset contains six CSV files:

- LVC_DE_passive_future_no_adverbs.csv — Futur I, without adverbs. Example: Anfang Januar wird ein Fehler gemacht werden.
- LVC_DE_passive_future_with_adverbs.csv — Futur I, with adverbs. Example: Anfang Januar wird anscheinend ein Fehler gemacht werden.
- LVC_DE_passive_present_perfect_no_adverbs.csv — Perfekt, without adverbs. Example: Anfang Januar ist ein Fehler gemacht worden.
- LVC_DE_passive_present_perfect_with_adverbs.csv — Perfekt, with adverbs. Example: Anfang Januar ist anscheinend ein Fehler gemacht worden.
- LVC_DE_passive_past_perfect_no_adverbs.csv — Plusquamperfekt, without adverbs. Example: Anfang Januar war ein Fehler gemacht worden.
- LVC_DE_passive_past_perfect_with_adverbs.csv — Plusquamperfekt, with adverbs. Example: Anfang Januar war anscheinend ein Fehler gemacht worden.

| File | Tense | Adverbs | Sentences |
|---|---|---|---:|
| `LVC_DE_passive_future_no_adverbs.csv` | Futur I | No | 1,086 |
| `LVC_DE_passive_future_with_adverbs.csv` | Futur I | Yes | 5,430 |
| `LVC_DE_passive_present_perfect_no_adverbs.csv` | Perfekt | No | 1,086 |
| `LVC_DE_passive_present_perfect_with_adverbs.csv` | Perfekt | Yes | 5,430 |
| `LVC_DE_passive_past_perfect_no_adverbs.csv` | Plusquamperfekt | No | 1,086 |
| `LVC_DE_passive_past_perfect_with_adverbs.csv` | Plusquamperfekt | Yes | 5,430 |
| **Total** | | | **19,548** |

**Passive restrictions:** Passive sentences are generated from **181 of the 292 items**. The remaining **111 items** are documented in `LVC_DE_passive_excluded_items.csv`: all **110** items with *haben* and the one *Rache nehmen* item with an oblique complement. Some generated passives, particularly with *erhalten* in its 'receive' sense, may be syntactically constructed but pragmatically unnatural; linguistic validation is recommended before experimental use.

### Active sentences with nominal subjects

The nominal-subject generator substitutes noun phrases for personal pronouns, using available German subject nouns and nominative determiners. The output retains metadata for the subject lemma, gender/number, determiner, and selected verb agreement.

Example from the saved file:

- *Ende Februar hat diese Assistentin anscheinend ein Produkt gehabt.*

The included file, `LVC_DE_active_nominal_subjects_output.csv`, has **10 randomly sampled sentences** (random seed `99`), drawn from **8,760 candidate sentences** under the current configuration. This sample should not be treated as the complete nominal-subject dataset.


## Main columns


| Column | Description |
|---|---|
|`sentence` | The full generated sentence |
| `LF` | Lexical-function label (or `no` for controls) |
| `verb_en` | English equivalent of the verb |
| `keyverb_eng` | English gloss of the object |
| `verb_de` | German verb lemma |
| `object_de` | German object lemma |
| `gen_object_de` | Object gender: `M`, `F`, or `N` |
| `num_obj_de` | Object number: `sg` or `pl` |
| `collocation` | `T` = LVC; `F` = full-verb control |
| `full_expression` | German infinitival verb–noun expression |

Other columns record the `voice`, `tense`, `adverb`, `time_spec`, subject and inflectional information, realized object phrase, and any template-placeholder resolution. Exact additional columns depend on the active, passive, or nominal-subject generator.

The files are CSVs encoded in **UTF-8 with BOM** (UTF-8-SIG).

## Reproducing the datasets

The sentence-generation code is supplied separately from this datasets folder:
- `build_LVC_sentences_short_context_German_v1.ipynb` — Jupyter notebook containing all three generation procedures.

### Input files
The code uses these normalized inputs, stored in `DE_normalized_inputs/`:

- `collocation_items_DE_clean_utf8.csv`
- `sentence_buildersDE_standardized_utf8.csv`
- `german_verbs_inflection_DE_utf8.csv`

Keep the code and input directories at the same level and run the notebook.

**Dataset totals for this release:** 292 source items; 31,536 active-pronominal sentences; 19,548 passive sentences.


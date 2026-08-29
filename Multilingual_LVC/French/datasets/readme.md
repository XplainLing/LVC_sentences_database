# LVC Sentence Datasets: French

The French sentence dataset contains: 
- Passive sentences dataset
- Active sentences dataset, pronominal subjects

This repo contains automatically generated sentence datasets with Light Verb Constructions (LVCs) and full-verb constructions.

The sentences shared in this folder use pronominal subjects. 
Scripts to to reproduce the generation of this dataset and to produce sentences with nominal subjects are contained in [sentence_generation](https://github.com/XplainLing/LVC_sentences_database/tree/main/Multilingual_LVC/French/datasets/sentence_generation)


---

## Pronominal subjects: Dataset statistics

### Verb Inventory

| Verb | Collocation Objects | Concrete Objects | Total Objects |
|---|---|---|---|
| avoir | 24 | 24 | 48 |
| faire | 60 | 35 | 75 |
| donner | 20 | 20 | 40 |
| recevoir | 20 | 20 | 40 |
| prendre | 10 | 10 | 20 |

- Temporal specifications: 170 
- Adverbial modifications: 15 
- Tense specifications: 3 (future, present perfect, past perfect)
- Voice specifications: 2 (active, passive)

---


## File Structure

### Active sentences

Active sentences are collected in six files, differing for tense and adverb specifications. 

- LVC_FR_active_future_no_adverbs.csv  - example:  Au début de janvier, ils prendront une décision.
- LVC_FR_active_future_with_adverbs.csv  - example: Au début de janvier, ils prendront certainement une décision.

- LVC_FR_active_present_perfect_no_adverbs.csv - example: Au début de janvier, ils ont pris une décision.
- LVC_FR_active_present_perfect_with_adverbs.csv - example: Au début de janvier, ils ont certainement pris une décision.
  
- LVC_FR_active_past_perfect_no_adverbs.csv - example: Au début de janvier, ils avaient pris une décision.
- LVC_FR_active_past_perfect_with_adverbs.csv - example: Au début de janvier, ils avaient certainement pris une décision.


### Passive sentences

Passive sentences are collected in six files, differing for tense and adverb specifications. 

- LVC_FR_passive_future_no_adverbs.csv - example: Au début de janvier, une décision sera prise.
- LVC_FR_passive_future_with_adverbs.csv - example: Au début de janvier, une décision sera certainement prise.

- LVC_FR_passive_present_perfect_no_adverbs.csv - example: Au début de janvier, une décision a été prise.
- LVC_FR_passive_present_perfect_with_adverbs.csv - example: Au début de janvier, une décision a certainement été prise.

- LVC_FR_passive_past_perfect_no_adverbs.csv - example: Au début de janvier, une décision avait été prise.
- LVC_FR_passive_past_perfect_with_adverbs.csv - example: Au début de janvier, une décision avait certainement été prise.


## Main columns

| Column | Meaning |
|---|---|
| `sentence` | Generated sentence |
| `voice` | `active` or `passive` |
| `tense` | Tense specification |
| `adverb` | Inserted adverb (`NA` if none) |
| `time_spec` | Temporal phrase |
| `verb_object` | phrase including the verb, object, and determiner where needed |
| `verb` | Verb |
| `object` | Object noun (sentence subject in passive)|
| `num_object_fr` | Inflected number (`sg` / `pl`) of the object noun (sentence subject in passive) |
| `gen_object_fr` | Inflected gender (`F` / `M`) of the object noun (sentence subject in passive) |
| `has_determiner` | Determiner before object, if none reports 'no' |
| `collocation` |is a collocation (T or F) |
| `LF` | Lexical Function label |

---

### Active sentence dataset specific columns

| Column | Meaning |
|---|---|
| `subject` | Generated subject phrase |
| `subject_base` | Base subject noun |
| `subject_number` | Subject number (`sg` / `pl`) |
| `subject_det` | Subject determiner |
| `subject_det_type` | Determiner type |

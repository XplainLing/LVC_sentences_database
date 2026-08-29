# LVC Sentence Datasets: Spanish

The Spanish sentence dataset contains: 
- Passive sentences dataset
- Active sentences dataset, pronominal subjects

This repo contains automatically generated sentence datasets with Light Verb Constructions (LVCs) and full-verb constructions.

The sentences shared in this folder use pronominal subjects. 
Scripts to to reproduce the generation of this dataset and to produce sentences with nominal subjects are contained in [sentence_generation](https://github.com/XplainLing/LVC_sentences_database/tree/main/Multilingual_LVC/English/datasets/sentence_generation) 


---

## Pronominal subjects: Dataset statistics

### Verb Inventory

| Verb | Collocation Objects | Concrete Objects | Total Objects |
|---|---|---|---|
| tener | 50 | 50 | 100 |
| hacer | 50 | 50 | 100 |
| tomar | 5 | 5 | 10 |
| recibir | 5 | 5 | 10 |
| dar | 30 | 30 | 60 |

- Temporal specifications: 170 
- Adverbial modifications: 15 
- Tense specifications: 3 (future, present perfect, past perfect)
- Voice specifications: 2 (active, passive)

---


## File Structure

### Active sentences

Active sentences are collected in six files, differing for tense and adverb specifications. 

- LVC_active_future_no_adverbs.csv - example: A principios de enero, tomarán una decisión.
- LVC_active_future_with_adverbs.csv - example: A principios de enero, tomarán ciertamente una decisión.

- LVC_active_present_perfect_no_adverbs.csv  - example:  A principios de enero, han tomado una decisión.
- LVC_active_present_perfect_with_adverbs.csv  - example: A principios de enero, han ciertamente tomado una decisión.
  
- LVC_ES_active_past_perfect_no_adverbs.csv - example: A principios de enero, habían tomado una decisión.
- LVC_ES_active_past_perfect_with_adverbs.csv - example: A principios de enero, habían ciertamente tomado una decisión.


### Passive sentences

Passive sentences are collected in six files, differing for tense and adverb specifications. 

- LVC_passive_future_no_adverbs.csv - example: A principios de enero, una decisión será tomada.
- LVC_passive_future_with_adverbs.csv - example: A principios de enero, una decisión será ciertamente tomada.

- LVC_passive_present_perfect_no_adverbs.csv - example: A principios de enero, una decisión ha aparentemente sido tomada.
- LVC_passive_present_perfect_with_adverbs.csv - example: A principios de enero, una decisión ha ciertamente sido tomada.
- 
- LVC_passive_past_perfect_no_adverbs.csv - example: A principios de enero, una decisión había sido tomada.
- LVC_passive_past_perfect_with_adverbs.csv - example: A principios de enero, una decisión había ciertamente sido tomada.


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


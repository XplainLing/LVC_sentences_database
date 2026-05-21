# LVC Sentence Datasets
The LVC sentence dataset contains: 
- Passive sentences dataset
- Active sentences dataset, pronominal subjects
- Active sentences dataset, nominal subjects

This repo contains automatically generated sentence datasets based on Light Verb Constructions (LVCs).

**IMPORTANT**: The sentences shared in this folder use pronominal subjects. 
Scripts to generate sentences with nominal subjects are contained in [LVC_sentences_generator](https://github.com/XplainLing/LVC_sentences_database/tree/main/datasets/LVC_sentences_generator), which also contains all the scripts to reproduce the generation of this dataset.

---

## Pronominal subjects: Dataset statistics

### Verb Inventory

| Verb | Collocation Objects | Concrete Objects | Total Objects |
|---|---|---|---|
| make | 20 | 20 | 40 |
| take | 20 | 20 | 40 |
| receive | 20 | 20 | 40 |
| have | 40 | 40 | 80 |
| give | 40 | 40 | 80 |

- Temporal specifications: 170 
- Adverbial modifications: 35 
- Tense specifications: 3 (past simple, future simple, past perfect)
- Voice specifications: 2 (active, passive)

---


## File Structure

### Active sentences

Active sentences are collected in six files, differing for tense and adverb specifications. 

- LVC_active_past_simple_no_adverbs.csv - example: In early January they made a decision.
- LVC_active_past_simple_with_adverbs.csv - example: In early January they finally made a decision.

- LVC_active_future_simple_no_adverbs.csv  - example:  In early January they will make a decision.
- LVC_active_future_simple_with_adverbs.csv  - example: In early January they will finally make a decision.
  
- LVC_active_past_perfect_no_adverbs.csv - example: In early January they had made a decision.
- LVC_active_past_perfect_with_adverbs.csv - example: In early January they had finally made a decision.


### Passive sentences

Passive sentences are collected in six files, differing for tense and adverb specifications. 

- LVC_passive_past_simple_no_adverbs.csv - example: In early January a decision was made.
- LVC_passive_past_simple_with_adverbs.csv - example: In early January a decision was finally made.

- LVC_passive_future_simple_no_adverbs.csv - example: In early January a decision will be made.
- LVC_passive_future_simple_with_adverbs.csv - example: In early January a decision will finally be made.

- LVC_passive_past_perfect_no_adverbs.csv - example: In early January a decision had been made.
- LVC_passive_past_perfect_with_adverbs.csv - example: In early January a decision had been finally made.


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
| `object` | Object noun |
| `has_determiner` | Determiner before object, if none reports 'no' |
| `obj_number` | Object number (`sg` / `pl`) |
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

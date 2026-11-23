# LVC Sentence Datasets: Italian

The Italian sentence dataset contains: 
- Passive sentences dataset
- Active sentences dataset

This repo contains automatically generated sentence datasets with Light Verb Constructions (LVCs) and full-verb constructions.

The sentences shared in this folder use **null subjects**, in line with standard Italian usage. 
Scripts to reproduce the generation of this dataset and to produce sentences with nominal subjects are contained in [sentence_generation](https://github.com/XplainLing/LVC_sentences_database/tree/main/Multilingual_LVC/Italian/datasets/sentence_generation)

---

## Null subjects: Dataset statistics

### Verb Inventory

| Verb | Collocation Objects | Concrete Objects | Total Objects |
|---|---:|---:|---:|
| avere | 60 | 60 | 120 |
| fare | 69 | 69 | 138 |
| dare | 26 | 26 | 52 |
| ricevere | 24 | 24 | 48 |
| prendere | 6 | 6 | 12 |

- Temporal specifications: 165  
- Adverbial modifications: 21  
- Tense specifications: 3 (future, present perfect, past perfect)  
- Voice specifications: 2 (active, passive)  

---

## File Structure

### Active sentences

Active sentences are collected in three released files, differing for tense specifications.

- `LVC_IT_active_future_no_adverbs.csv` - example: *All'inizio di gennaio, prenderanno una decisione.*  
- `LVC_IT_active_present_perfect_no_adverbs.csv` - example: *All'inizio di gennaio, hanno preso una decisione.*  
- `LVC_IT_active_past_perfect_no_adverbs.csv` - example: *All'inizio di gennaio, avevano preso una decisione.*  

Files with adverbs are **not released in the repository**, because they are too large.  
However, they can be generated with the scripts in `sentence_generation`.

Examples of the corresponding adverbial sentences are:

- *All'inizio di gennaio, certamente prenderanno una decisione.*  
- *All'inizio di gennaio, certamente hanno preso una decisione.*  
- *All'inizio di gennaio, certamente avevano preso una decisione.*  

### Passive sentences

Passive sentences are collected in three released files, differing for tense specifications.

- `LVC_IT_passive_future_no_adverbs.csv` - example: *All'inizio di gennaio, sarà presa una decisione.*  
- `LVC_IT_passive_present_perfect_no_adverbs.csv` - example: *All'inizio di gennaio, è stata presa una decisione.*  
- `LVC_IT_passive_past_perfect_no_adverbs.csv` - example: *All'inizio di gennaio, era stata presa una decisione.*  

Files with adverbs are **not released in the repository**, because they are too large.  
However, they can be generated with the scripts in `sentence_generation`.

Examples of the corresponding adverbial passive sentences are:

- *All'inizio di gennaio, certamente sarà presa una decisione.*  
- *All'inizio di gennaio, certamente è stata presa una decisione.*  
- *All'inizio di gennaio, certamente era stata presa una decisione.*  

---

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
| `object` | Object noun (sentence subject in passive) |
| `num_object_it` | Inflected number (`sg` / `pl`) of the object noun (sentence subject in passive) |
| `gen_object_it` | Inflected gender (`F` / `M`) of the object noun (sentence subject in passive) |
| `has_determiner` | Determiner before object, if none reports `no` |
| `collocation` | is a collocation (`T` or `F`) |
| `LF` | Lexical Function label |

---

### Active sentence dataset specific columns

| Column | Meaning |
|---|---|
| `subject` | Generated subject phrase (`NA` for null-subject sentences) |
| `subject_base` | Base subject noun or pronoun key |
| `subject_number` | Subject number (`sg` / `pl`) |
| `subject_det` | Subject determiner |
| `subject_det_type` | Determiner type |
| `subject_realized` | whether the subject is overtly realized (`yes` / `no`) |


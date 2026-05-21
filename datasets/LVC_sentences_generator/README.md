# LVC Sentence Generator Script

The script *build_LVC_sentences_short_context.ipynb* generates passive sentences, active sentences with pronouns, active sentences with nominal subjects. 
The script takes as input the files contained in this folder: 
- a list of verbs + objects, including collocations and concrete nouns (`collocation_items_IN_v1_1.csv`)
- a list of subject, dverbs and other sentence specifications (`sentence_builders.csv`)


## Input Files

### FILE1: `collocation_items_IN_v1_1.csv`

Contains the verb + object pairs. 

Important columns:

| Column | Meaning |
|---|---|
| `verb_object` | Full collocation |
| `verb` | Verb |
| `object` | Object noun |
| `has_determiner` | Determiner before object (`no` = none) |
| `obj_number` | `sg` or `pl` |
| `collocation` | Collocation label |
| `LF` | Lexical Function label |

---

### FILE2: `sentence_builders.csv`

Contains sentence-building material (subject, adverbs, determiners, other sentence specifications)

Important columns:

| Column | Meaning |
|---|---|
| `time_specs` | Temporal phrase |
| `adverbs` | Adverbs |
| `subjects_sg` | Singular subjects |
| `subjects_pl` | Plural subjects |
| `det` | Article |
| `det_pl` | Determiners that can be used with plural |
| `det_poss` | Possessive determiner to be used with nouns that admit its use |
| `det_poss_tf` | Whether possessive determiners are allowed (`T`) |


## Sentence generations 

### Passive sentences
build_LVC_sentences_short_context.ipynb - 'active sentences'

The passive examples generated with this file are collected in the [datasets](https://github.com/XplainLing/LVC_sentences_database/tree/main/datasets) repo: one file per tense, with or without adverbial modifiers. 

### Active sentences - pronouns
build_LVC_sentences_short_context.ipynb - 'active sentences' 

The active examples generated with this file are collected in the [datasets](https://github.com/XplainLing/LVC_sentences_database/tree/main/datasets) repo: one file per tense, with or without adverbial modifiers. 

### Active sentences - nouns
build_LVC_sentences_short_context.ipynb - 'active sentences with nominal subjects' 

The script generates sentences with:
- different tenses (past simple, future simple, past perfect 
- adverb/no adverb modification
- singular and/or plural subjects
- different determiners (definite article, possessive, no determiner)

See below for parameter selection and examples. 

## Output File

Main generated columns:

| Column | Meaning |
|---|---|
| `sentence` | Generated sentence |
| `voice` | Sentence voice |
| `tense` | Tense |
| `adverb` | Adverb used |
| `time_spec` | Temporal phrase |
| `subject` | Generated subject phrase |
| `subject_number` | `sg` / `pl` |
| `subject_det` | Determiner used |
| `subject_det_type` | Determiner type |

---

## Main Parameters

### Subject number

```python
SUBJECT_NUMBER = "both"
```

Options:
- `"sg"`
- `"pl"`
- `"both"`

---

### Subject determiner types

```python
SUBJECT_DET_TYPES = ["det", "det_pl", "det_poss", "no_det"]
```

Options:
- `"det"`
- `"det_pl"`
- `"det_poss"`
- `"no_det"`

---

### Adverbs

```python
USE_ADVERBS = True
```

- `True` → use adverbs
- `False` → no adverbs

---

### Tenses

```python
TENSES = ["past_simple", "future_simple", "past_perfect"]
```

Options:
- `"past_simple"`
- `"future_simple"`
- `"past_perfect"`

---

### Random subject selection

```python
RANDOM_SUBJECT_SELECTION = True
```

- `True` → one random subject per sentence
- `False` → all possible subjects

---

### Random output sampling

```python
RANDOM_OUTPUT_SAMPLE = True
```

- `True` → save random subset only
- `False` → save all generated rows

---

### Number of random rows

```python
N_RANDOM_ROWS = 100
```

Used only if:

```python
RANDOM_OUTPUT_SAMPLE = True
```

---

## Example Configurations

### Generate all possible sentences

```python
RANDOM_SUBJECT_SELECTION = False
RANDOM_OUTPUT_SAMPLE = False
```

---

### Generate 100 random sentences

```python
RANDOM_SUBJECT_SELECTION = True
RANDOM_OUTPUT_SAMPLE = True
N_RANDOM_ROWS = 100
```

---

### Only plural subjects with possessive determiners

```python
SUBJECT_NUMBER = "pl"
SUBJECT_DET_TYPES = ["det_poss"]
```

---

# Usage
The scripts for passive, acrtive, active-nominal are part of the same ipynb notebook [build_LVC_sentences_short_context.ipynb](datasets/LVC_sentences_generator/build_LVC_sentences_short_context.ipynb). 
Each can be run independently.

Make sure that the input files 'collocation_items_IN_v1_1.csv' and 'sentence_builders.csv' are in the same directory or specify the paths otherwise. 

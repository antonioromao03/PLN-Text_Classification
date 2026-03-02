# ADS509 Dataset Card

## Description

This dataset was created in an attempt to understand the nature of social media commentary beyond the usual 'positive', 'negative', 'neutral' labels. Below is a description of the sources, labels and methods used to create the dataset

## Sources

The social media comments available in this data have been pulled from the following sources

- You Tube
- Hacker News
- MetaFilter
- Reddit
- BlueSky

## Labels

### Argumentative

- Makes specific claims, predictions, or assertions supported by reasoning
- Uses evidence, anecdotes, or scenarios to build a case
- The key distinction from Opinion: there's an attempt to persuade or explain why, not just state a position

### Informational

- Shares facts, data, links, or context relevant to the discussion
- Low emotional affect — the comment is trying to inform, not convince or react
- Includes answering another commenter's question with factual content
- The key distinction from Argumentative: presenting information without advocating for a position

### Opinion

- States a value judgment, stance, or take without substantial reasoning
- "This is good/bad/wrong/overrated" — the comment asserts but doesn't argue
- The key distinction from Argumentative: no real attempt to persuade or support the claim
- The key distinction from Expressive: the comment is making a point, not just reacting

### Expressive

- Emotional reactions, sarcasm, jokes, venting, exclamations
- The comment is primarily expressing feeling rather than making a point
- Includes performative agreement/disagreement ("THIS," "lol exactly," "what a joke")
- The key distinction from Opinion: no identifiable stance being taken, just affect

### Neutral

- Clarifying or rhetorical questions, meta-commentary, off-topic remarks
- Comments that don't clearly fit the other four categories
- Includes simple factual questions directed at other commenters

## Methods

### Collection

The social media comments were pulled from posts in the above sources that fit the following criteria

Search query was 'politics' or 'US Politics'
Data range varied from 2024 to mid-Feb of 2026 depending on the nature of the site. For instance Reddit is heavily trafficked and the daily rate limit was hit for posts pulled in just the first two weeks of Feb, while Metafilter posts were pulled from as far back as 2024
Posts with less than 10 comments were ignored, and no more than 300 comments were pulled from any one post

### Labeling

A sample of 100 comments were independently labeled by 2 of our group, then compared and revised. The rest were sent via the Batch API to 3 language models: Gemini Flash 3, Chat GPT 5.1 and Calude Haiku 4.5. Included in the prompt were 10 examples of correctly labeled samples and 10 examples of samples that had been incorrectly labeled with the correct label provided. The comments that had an agreement of 2 or more models were kept with the reamining comments set aside for evaluation

### Processing

Approximately 2-3k duplicate comments were removed
NaN's were removed
Emojis were converted into text using the emoji package
Text was converted to lower case
Remaining HTML artifacts were removed
URL links were replaced with a '[URL]' tag
Some comments contained escaped characters, these were converted back e.g. (&/quot; -> ")

## Dataset_info

### Features

- text -> string  
- label

### Splits

- name: train
  - num_bytes: 10.19 Mb  
  - num_examples: 49,268  
- name: test
  - num_bytes: 2.19 Mb
  - num_examples: 10,558
- name: valid
  - num_bytes: 2.19 Mb
  - num_examples: 10,557
- download_size: 9.16 Mb
- dataset_size: 14.57 Mb

### Configs

config_name: default

data_files:  

- split: train
  - path: data/train-*  
- split: test  
  - path: data/test-*  
- split: valid  
  - path: data/valid-*  

### label2id

Neutral: 0  
Opinion: 1  
Argumentative: 2  
Expressive: 3  
Informational: 4  

### id2label

0: Neutral  
1: Opinion  
2: Argumentative  
3: Expressive  
4: Informational  

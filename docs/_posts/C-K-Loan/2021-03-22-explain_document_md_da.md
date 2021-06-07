---
layout: model
title: Explain Document Pipeline for Danish
author: John Snow Labs
name: explain_document_md
date: 2021-03-22
tags: [open_source, danish, explain_document_md, pipeline, da]
task: [Named Entity Recognition, Lemmatization, Part of Speech Tagging]
language: da
edition: Spark NLP 3.0.0
spark_version: 3.0
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

The explain_document_md is a pretrained pipeline that we can use to process text with a simple pipeline that performs basic processing steps.
         It performs most of the common text processing tasks on your dataframe

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
[Open in Colab](https://colab.research.google.com/github/JohnSnowLabs/spark-nlp-workshop/blob/2da56c087da53a2fac1d51774d49939e05418e57/jupyter/annotation/english/explain-document-dl/Explain%20Document%20DL.ipynb){:.button.button-orange.button-orange-trans.co.button-icon}
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/explain_document_md_da_3.0.0_3.0_1616437187649.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python

from sparknlp.pretrained import PretrainedPipelinein
pipeline = PretrainedPipeline('explain_document_md', lang = 'da')
annotations =  pipeline.fullAnnotate(""Hej fra John Snow Labs! "")[0]
annotations.keys()

```
```scala

val pipeline = new PretrainedPipeline("explain_document_md", lang = "da")
val result = pipeline.fullAnnotate("Hej fra John Snow Labs! ")(0)


```

{:.nlu-block}
```python

import nlu
text = [""Hej fra John Snow Labs! ""]
result_df = nlu.load('da.explain.md').predict(text)
result_df
    
```
</div>

## Results

```bash
|    | document                     | sentence                    | token                                   | lemma                                   | pos                                        | embeddings                   | ner                                   | entities            |
|---:|:-----------------------------|:----------------------------|:----------------------------------------|:----------------------------------------|:-------------------------------------------|:-----------------------------|:--------------------------------------|:--------------------|
|  0 | ['Hej fra John Snow Labs! '] | ['Hej fra John Snow Labs!'] | ['Hej', 'fra', 'John', 'Snow', 'Labs!'] | ['Hej', 'fra', 'John', 'Snow', 'Labs!'] | ['NOUN', 'ADP', 'PROPN', 'PROPN', 'PROPN'] | [[0.4006600081920624,.,...]] | ['O', 'O', 'B-PER', 'I-PER', 'I-PER'] | ['John Snow Labs!'] |
```

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|explain_document_md|
|Type:|pipeline|
|Compatibility:|Spark NLP 3.0.0+|
|License:|Open Source|
|Edition:|Official|
|Language:|da|
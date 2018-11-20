---
title: Classifiying headlines as clickbait
categories: [machine learning]
notes: https://www.evernote.com/shard/s3/nl/196239/688f6af1-ce78-480c-a7ce-335ccf0d5eb8/
---

## Overview

todo

## Technology

- **Dataprep** - prepare a dataset used for training a model
- **AutoML** - create and train a model that can classify headlines as "clickbat" or "not clickbait"
- **Cloud Function** - "serverless" approach to expose the model to the outside world
- **Chrome Extension** - scrapes headlines from a website and sends them to the model (via Cloud Function) for classification

## Dataset

The dataset is a combination of 2 different sources. This was done to increase the total size and variety of the data when training the model.

1. [Clickbait Challenge 2017](https://www.clickbait-challenge.org/)
2. [https://github.com/bhargaviparanjape/clickbait/tree/master/dataset](https://github.com/bhargaviparanjape/clickbait/tree/master/dataset)

The clickbait challenge dataset is 2 separate files that are combined.

## Cloud Dataprep

Before feeding the dataset through AutoML, it needs to be in the right format. The dataset is cleaned, restructured and formatted with Cloud Dataprep. Dataprep is all UI driven with zero code, so just about anyone can be productive with it in no time.
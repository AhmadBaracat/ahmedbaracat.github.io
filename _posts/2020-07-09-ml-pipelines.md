---
layout: essay
title: How Machine Learning Pipelines Evolve Based on your Business Maturity
date: 2020-07-09
permalink: /essays/how-machine-learning-pipelines-evolve-based-on-your-business-maturity
---

# How Machine Learning Pipelines Evolve Based on your Business Maturity

- [Disclaimer](#disclaimer)
- [The audience](#the-audience)
- [Background](#background)
- [Why Invest in an ML Pipeline](#why-invest-in-an-ml-pipeline)
- [What is an ML Pipeline](#what-is-an-ml-pipeline)
- [Business Maturity/Stages](#business-maturitystages)
  - [Starting Up](#starting-up)
  - [Short to Medium Term](#short-to-medium-term)
  - [Long-Term Investment (Custom Build)](#long-term-investment-custom-build)
- [Wrap-up](#wrap-up)

## Disclaimer

- This article is intentionally high-level and devoid from technical jargon.
- That said, at times, I will mention a few technologies/services to give you more concrete examples. For these examples, I will be referring AWS services but you should be able to find similar offerings on other cloud providers.

## The audience

This article is an overview of how an ML pipeline would look like depending on the stage your team or company is in and what to keep in mind at each stage. The main audience are engineers & scientists working on ML productionization and executives or their equivalent in startups (ex: CTOs) who want to have a broad overview of the topic.

## Background

During my tenure at Amazon, I was very lucky to be involved in multiple projects designing and building ML pipelines.

In 2017-18, I have designed and built an end-to-end ML pipeline with the different components discussed below for Amazon Advertising: the team responsible for running all personalized display advertising on behalf of Amazon worldwide with millions of Transactions per Second (TPS) and <100 ms latency.

In 2018-19, while working on Amazon Alexa, we had to manage the deployment of our models, but being a newly formed team, we faced different trade-offs as compared to Amazon Advertising.

During the past few years, I have also consulted startups and individuals on managing their ML engineering-related problems.

## Why Invest in an ML Pipeline

Imagine you are Amazon Advertising and you are using ML models to predict how much to bid on a given Ad slot, or you are Amazon Alexa and you want to filter down offensive images on multi-modal devices, or you are a startup in Egypt building eKYC solutions and you need to have models to analyze national ID cards. In all of these cases, ML models are a core component of your value proposition and technical barrier to entry.

For these reasons, you need a reliable way of managing them. Managing in this case would not only mean building a reproducible way of deploying them to production, but also keeping an eye on these models using monitoring and alarming as well as other aspects discussed below.

## What is an ML Pipeline

From a bird’s-eye view, an ML pipeline has a few components.

1. **Dataset generation:** responsible for fetching, joining and aggregating data from the different sources, cleaning the data, applying different filters (ex: subsampling) and generating cleaned training and validation datasets
1. **Training:** responsible for training the ML model, performing hyper parameter optimization and generating a trained model
1. **Validation:** responsible for running the trained model on the validation dataset and generating validation metrics
1. **Deployment:** responsible for copying the trained model to production service (if the model passes certain validation criteria and is outperforming the current model in production)
1. **Monitoring & Alarming:** there are at least 2 sets of metrics and alarms depending on the role:
   - **Engineering:** responsible for metrics such as model latency, memory usage, CPU usage, etc.
   - **Science:** responsible for metrics such as model bias, input or output distribution drift, etc.

## Business Maturity/Stages

_Note: It is crucial to understand and be explicit about the trade-offs involved in technical decisions. That’s why I will highlight a number of trade-offs associated with each stage_

### Starting Up

(doing things that don’t scale is the name of the game)

If you are just starting up, don’t be ashamed of using the least friction path for having an ML pipeline. At this stage, you are not sure yet if it is worth it to invest engineering effort building a robust ML pipeline. What you need at this stage is a cheap & quick way of getting models from development environments to production. This will allow you to assess how much value is it creating for your business. In essence, you are trading speed of experimentation with robustness.

For that reason, dataset generation, training, validation and deployment could just be a series of Python scripts that you run manually following a runbook (checked-in in your Git repo or posted on your internal wiki). Depending on your use case, monitoring & alarming may be a bonus point. Whichever path you choose, make sure that there is a reproducible and documented way of getting models into production. This is crucial and will come handy when things go awry.

_Note that if you are already familiar and can move fast by using off-the-shelf services like SageMaker then by all means use it. The important thing at this stage is to optimize for moving fast and experimenting._

### Short to Medium Term

Once you have validated that having an ML model in production actually provides value for your business and hopefully have a sense of how much value it is creating, you can justify investing engineering effort in making the ML pipeline more robust.

Note that, at this stage, you still value moving as fast as you possibly can and thus you want to spend the least time possible on engineering or maintenance of ML pipelines. For example, you would rather spend more engineering time building more valuable features for your customers.

For these reasons (improving robustness while keeping the investment low), you should consider using off-the-shelf services like SageMaker (which supports all core components of ML pipelines mentioned above). Such services will allow you to have robust ML pipelines with auto-scaling, ease of rollback, etc. without investing too much engineering time. Note that there there is still effort to be invested in setting things up, but for the most part, once that cost is paid, it should be “hands off the wheel” experience in terms of deployment and scaling.

However, SageMaker will cost more than running your own infrastructure on EC2 for example. The trade-off then is the cost on one hand and robustness & speed of experimentation on the other hand. That cost can be justifiable at this stage since you are saving precious engineering time.

### Long-Term Investment (Custom Build)

Assuming everything goes well and your business is thriving (ex: hundreds, thousands or millions of TPS), you may start to care more about cost as well as having more control over your ML pipeline since the off-the-shelf solutions may not be enough in terms of feature support. You are also willing to invest more engineering effort to build a custom solution and to maintain it. You are essentially trading off customization, cost and adding new features with engineering & maintenance effort.

Concretely, you will borrow the features that you care about from the off-the-shelf services and add more advanced custom ones depending on your use case. For example, at this stage, the pipeline may look like follows:

1. Dataset generation is automated and run at specified schedule (ex: daily or dynamically when input or output model distribution changes in production): a cluster (ex: Spark) is spun up, runs a script to gather, transform and output the data to a durable place (ex: S3)
1. Once a new dataset is generated, this will trigger the training process. The output of the training step may not only be the trained model, but also other meta information (ex: hyperparameters used, dataset version, model version, etc.)
1. Once the model is trained, a validation step is triggered and it compares how the newly trained model performance against the current model in production (ex: comparing their performance on a Golden Standard dataset but beware of dataset drift)
1. If model passes validation, the model gets deployed to production
1. Monitoring service then kicks in and keeps an eye on the important metrics and triggers alarms when an anomaly is detected and may support rolling back a model automatically
1. You also have the ability to manually intervene and roll back your models

## Wrap-up

I hope you got a good overview of what an ML pipeline is, why build one and a few points to keep in mind depending on the stage your company or team is in.

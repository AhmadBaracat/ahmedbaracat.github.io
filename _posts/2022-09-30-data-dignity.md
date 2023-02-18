---
layout: essay
title: (Request for Funding) A Business Experiment in Data Dignity
date: 2022-09-30
permalink: /essays/request-for-funding-a-business-experiment-in-data-dignity
---

# (Request for Funding) A Business Experiment in Data Dignity

- [Resources (TL;DR)](#resources-tldr)
- [The problem](#the-problem)
- [The product](#the-product)
- [Why focus on Data Dignity?](#why-focus-on-data-dignity)
- [Why logo generation?](#why-logo-generation)
- [Who are the customers?](#who-are-the-customers)
- [Differences from current offerings](#differences-from-current-offerings)
- [Action Plan](#action-plan)
- [Why bother?](#why-bother)
- [Worst Case Outcomes](#worst-case-outcomes)
- [Best Case Outcomes](#best-case-outcomes)
- [Differences from ](#differences-from)
- [Simple Business Model](#simple-business-model)
  - [Ambiguities](#ambiguities)
  - [Assumptions](#assumptions)


## Resources (TL;DR)

[Link to Pitch Deck](https://docs.google.com/presentation/d/128wFe8jcLcN4M0junncZkA227O-dABVRGRJ5ivxGgpU/edit?usp=sharing)  

[AI Grant 1.5 mins Pitch](https://youtu.be/uJzo2m74SDs)

## The problem

*   AI-focused products/startups lack a business model aligning the incentives of both the company and the domain experts (Data Dignity)
*   With the current advancements in AI generated images from text, we are going to focus on logo generation from text as a testbed for a new business model

## The product

*   Building Stability.ai DreamStudio for logo generation
*   The main hypothesis for building this startup is figuring out what would happen if the ML builders and the domain experts had co-ownership of the data/model.
*   Essentially, this is a business experiment in Data Dignity (a term coined by Satya Nadella and popularized by Jaron Lanier) economics.

## Why focus on Data Dignity?

*   Lack of business model experimentation
    *   Not many companies (if any) are experimenting with business models, which don’t alienate domain experts and provide co-ownership of the value created
*   Better data quality
    *   We have seen, first hand, how big companies like Amazon will use services like MTurk to label data cheaply and we have seen how this affects the quality of the data
*   Build better AI-products
    *   We believe we can build better AI products if we can get better alignment both financially (co-ownership) and directionally (what do we want a specific AI product to do) between the ML community and the domain experts

## Why logo generation?

*   Intuitively, it is easier to tackle than generic image generation (the domain of Stability.ai), thus needing less data
*   There is big demand for logo generation services
    *   Fiverr has 300k+ logo generation services listed

## Who are the customers?

*   Logo designers looking for creative unblock
*   Businesses looking to buy unique/inexpensive logos

## Differences from current offerings  

*   Stability AI DreamStudio
    *   You can use the generated images for commercial purposes
*   Fiverr. (Ex: you get 2 concepts & 3 revisions for $13 + 2 days delivery)
    *   You get 1k concepts for $10
    *   You get Instant delivery
    *   You get to play around with the service

## Action Plan

For the initial launch, we will have a lot of self-imposed constraints to allow us to focus on the meat of the business experiment, which is “can we get it to work economically?” i.e. are we able to get experts to share their data and for customers to use the created model to solve their use case while making sure we provide experts with financial incentive and for the AI-company to be profitable (check below, Simple Business Model).

1.  Figure out which community of artists/experts are the easier to access and are more likely to participate in this business experiment
    1.  We need an image generation task/gap that once cracked will prove profitable (as other non domain experts are likely to rely on to generate images for their use cases)
    2.  We have potential communities in mind that span different parts of the spectrum
        1.  Anime/cartoon style image generation for the general public
            1.  Experts: cartoonists and anime artists
            2.  Customers: general public
        2.  Realistic image generation for the general public
            1.  Experts: general public photos taken with their smartphones
            2.  Customers: general public
        3.  Cartoon/Diagram generation for scientific use cases (ex: to generate illustrations for papers and posters)
            1.  Experts: scientific illustrators
            2.  Customers: Masters/PhD students in STEM fields
        4.  Logo ideas generation
            1.  Experts: logo designers
            2.  Customers: other logo designers looking for creativity unblock or businesses looking to buy unique/inexpensive logos)
    3.  Cherry pick experts by hand and referrals from the ones already vetted
        1.  For v1, only onboard experts who have good reviews/ratings and who we can easily pay (ease of sending money, tax implications, etc.)
    4.  Build the data capturing tool
        1.  Need to check for collisions for similarly submitted data (we need to make sure that the data is valuable to the model before accepting it)
        2.  If the data is similar to already submitted data, we show the expert examples of similar works (either in terms of image or caption)
        3.  Vetted experts can choose to either upload new data or to vote on the validity/quality of already uploaded data
    5.  Train the model
        1.  We will first train a baseline model on public domain data
        2.  Fine tune on the provided expert data
2.   Deploy the model as a web app (similar to what Stability AI has built)
3.   Charge by API request (bulk or singular calls)
4.   Distribute the earnings

## Why bother?

*   We need alternative business models for how the current AI companies are operating
*   We need to experiment and share the outcomes of these experiments for other companies to learn 
*   We want to be as open as possible about the experiment/revenue/etc so business dashboards will be publicly accessible

## Worst Case Outcomes

## Best Case Outcomes

## Differences from 

*   Current offerings (Stability AI)
    *   You can use the generated images for commercial purposes
*   Why not use Fiverr ([example](https://www.fiverr.com/ei8htz/design-2-outstanding-logo?context_referrer=subcategory_listing&ref_ctx_id=f8bd164bd8654210fe7f273fb02bc4ec&pckg_id=1&pos=1&context_type=rating&funnel=f8bd164bd8654210fe7f273fb02bc4ec&seller_online=true&imp_id=0a4cf589-a395-4793-a679-fb2dd3e7d8a4)). Ex: you get 2 concepts (3 revisions) for $13 + 2 days delivery
    *   You get 1k revisions/images for $10, instant delivery and you get to play around

## Simple Business Model

### Ambiguities

*   How many images/labels do we need for the v1 model/service?
    *   Stability AI CLIP model is trained on 400M images
    *   But most of these images/annotations are garbage (need to cite the paper whose authors managed to train a model on 10x or 100x less iterations by discarding unneeded data)
    *   We don’t need the same scale for the number of images because we will first focus on niche (logo generation) which is easier for the model to learn + we will pay money/effort in vetting the data → i.e. high quality data
    *   Let’s assume 100k logos/captions needed for v1
*   How long does it take to create one logo?
    *   2-20 hours (Source: [Quora](https://www.quora.com/How-long-does-the-logo-design-process-usually-take))
    *   Assuming 10 hours/logo
*   How long would it take to gather and vet the v1 dataset?
    *   Let’s assume we want to create v1 in 1 month
*   How many experts?
    *   Assuming 1 month, each expert will create ~20 logos
    *   We need 5k experts (there are 300k logo services on Fiverr that we may leverage, [source](https://www.fiverr.com/categories/graphics-design/creative-logo-design?utm_source=google&utm_medium=cpc&utm_campaign=G_UK_Logo_Desktop_BMM&utm_term=BMM_Design-How-Idea_Logo&utm_content=AdID%5E230891819463%5EKeyword%5E%2Blogo%20%2Bdesign%20%2Bhow%5EPlacement%5E%5EDevice%5Ec&caid=974844185&agid=46526499337&ad_id=230891819463&kw=%2Blogo%20%2Bdesign%20%2Bhow&lpcat=gd_logo&show_join=true&cq_src=google_ads&cq_cmp=974844185&cq_term=%2Blogo%20%2Bdesign%20%2Bhow&cq_plac=&cq_net=g&cq_plt=gp&gclid=CjwKCAjwpqCZBhAbEiwAa7pXeT32egeGyJukYs6b_DQDOWViSuJB8G0i1TSgJ76tflmj_fe-kXF_7xoCwcYQAvD_BwE&gclsrc=aw.ds))
*   Initial dataset cost
    *   Assuming that we pay the experts 50% of their current rate/logo because most of the value comes from the royalties
    *   Currently, 2 concepts → $13
    *   1 logo is $7
    *   50% of that is $3.5
    *   Assuming that we need 20k unique logos 
    *   Cost for getting the 20k logos → $70k
    *   Assuming 5 captions per logo
    *   Cost for each caption is $0.1 → $10k (How much did we pay MTurks?)
    *   Assuming 5 votes per logo/caption
    *   Cost for each vote on validity of caption/logo $0.05 → $25k (How much did we pay MTurks?)
    *   Total is $70k + $10K + $25k = $105k
*   Initial training cost
    *   Cost for training CLIP model on 400M images → $221k - $767k (depending on the model, cite paper)
    *   Let’s take the lower bound as a starting model, so ~$200k
    *   We first train on 1M public domain logo images or 10M public domain images/captions 
    *   Then we fine-tune on the 100k logos/captions
    *   Assuming 10M + 100k
    *   $5k initial training cost (assuming we don’t use the idea of the paper that trained the models in 10x or 100x less iterations)
*   Total v1 cost
    *   $110k

### Assumptions

*   Assuming same pricing as Stability AI DreamStudio ($10 → 1k image generations)
*   3 ways experts can contribute (make instant money + have ownership of the model/data which means long term revenue/ )
    *   Upload an image + a corresponding caption
    *   Write new captions for existing images
    *   Vote on the validity of an image/caption pair
*   Assuming 1k hardcore users (i.e. they use the service extensively → pay us $100/month → 10k image generations)

    *   Revenue will be $100k/month
    *   Number of images generated: 10M
    *   Images generated evenly over the 30 days and 12 hours/days (to account for “peak” hours :D)
        *   ~30K images/hour
        *   500 images/min
        *   ~10 images/sec (10 TPS)
    *   Assuming a single V100 GPU can handle that load
    *   We will rent 2 v100 GPU machines for redundancy
    *   Cost on Azure is $3/hr/1xV100
    *   Cost per month for 1 machine (reverting to 24 hours/day) → ~$2k
    *   Cost of 2 machines → ~$4k
    *   Need to estimate cost of bandwidth and other API services used, but let’s assume they are $1k per month for this load
    *   So total is $5k/month
*   For safety margin, let’s assume the costs per month are $10k +$10k (each founder take $5k salary → £3k net salary per month per founder) + partial cost of training/gathering the dataset ($10k)
    *   We are including the partial cost of training/gathering the dataset because we want to model the initial investment as a cost that we need to recoup in 12 months
*   Profit will be $70k
*   Split it 10%/90% with company/experts
*   $7k for company & $63k for experts
*   We assumed 5k experts → each expert will get $12 per month (they were already paid $70 each for providing 20 logos for the v1 dataset)

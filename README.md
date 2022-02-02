# Sentiment Analysis of headlines about US presidents in their first year of mandate

> This is my final project of the Automated Media Content Analysis module, as part of the program Mannheim Master in Data Science of the University of Mannheim, during the winter semester of 2021/22.

To see the full code and report, check the **[Python Notebook file](/AMCA_Project_and_Report.ipynb)**.

## Introduction

With the wide spread of instant messaging apps such as Whatsapp and Telegram, and the frequent restriction of full-article reading by famous journals to subscribers, news' headlines and snippets have become more important in the information sharing dynamic. Headlines are the titles, often in bold and greater size, while snippets are the small text that can be read right below the headlines in instant messaging apps' and social media's pre-visualization. Both texts plus the image that appears when sharing articles are the newspaper's chance of convincing potential readers that the full content is worth a subscription, and are certainly read more frequently than the article's paragraphs.

In order to become interesting and curious, these short texts might carry sentiment, irony, analogies, and even mystery. Their vocabulary must be carefully chosen to make the article at the same time informative and instigating, and it might also reveal the newspaper's position towards some subject. Specifically in the political environment, measuring the sentiment of news' summaries regarding politicians, parties, and agendas are important for understanding its influence in social behavior.

As both media content and text processing techniques have become more easily available in the digital era through websites, API's, and open-source programming languages and packages, automated analysis of media content was also made easier. Huge text corpses that would require hours of repeated human tasks can now be processed in seconds, and using advanced Natural Language Processing (NLP) approaches in programmable techniques. Among the existing NLP tasks, Sentiment Classification has been increasingly used for analytical purposes, as it can classify some text as positive, negative or neutral, extract latent and subjective meaning from it, and therefore make different groups of text comparable objectively.

In this project report, the sentiment of headlines and snippets from The New York Times articles concerning two United States presidents - Donald Trump and Joe Biden - in their first year of government were analyzed to investigate the following research questions:

- Did the news about the polemic president Donald Trump during 2017 carry more negative sentiment than news about Joe Biden in 2021?
- Did the average sentiment of these news range during the year, possibly affected by significant occurrences?
- Does the average sentiment obtained by NLP techniques correlate with approval rates in the same periods?

To answer these questions, more than 7000 New York Time's articles about Trump (2017) and Biden (2021) were scrapped through the journal's official API, and then classified by three different pre-trained models of Sentiment Classification available in Python: Textblob, VADER and Flair. In order to choose the classifier that performed best, a random sample of 1000 articles was annotated twice by 40 different human coders. Both Inter-Annotator Agreement reliability scores Cohen's Kappa and Krippendorff's Alpha were low, and only agreement occurrences were considered as gold standard for validation. The VADER sentiment classifier showed the higher scores for F1 and macro average precision, so its labels were used for the analysis.

## Some Findings

- Donald Trump accumulated much more negative headlines during 2017 (45%) than his successor Joe Biden during 2021 (36%), while the second accumulated more positive headlines than the first (48% against 39%). Considering VADER's compound polarity score, Trump's average sentiment was slightly negative (-0.04), while Biden's was slightly positive (+0.06).

![percentage and average sentiment per president](/images/percentage_and_average_sentiment_per_president.png)

- In comparison to approval rates, Trump's rate by the end of his first year was 37.7%, while Biden's achieved 43.1%, according to the portal [FiveThirtyEight](https://projects.fivethirtyeight.com/biden-approval-rating/?ex_cid=rrpromo). However, Biden kept his approval rate more than 10 percentage points above Trump's during most of their first years, and this difference decreased after August of each year. 

![Approval rates FiveThirtyEight](/images/Approval_rates_FiveThirtyEight.png)

- When looking at average sentiment month by month, it is to notice that in August there was a special peak of negative headlines about Biden in 2021, and both presidents reached 55% of negative sentiment. This might have happened due to the withdrawal of American troops from Afghanistan during August 2021, which led to Taliban militants returning to power in this country. This was certainly the most negative and controversial episode in Biden's first year of government, and might have made his popularity fall to the same level of his predecessor's.

![Average Sentiment over Months](/images/Average_Sentiment_over_Months.png)

![Percentage of positive and negative sentiment over time](/images/percentage_of_positive_and_negative_sentiment_over_time.png)

- While looking at the most frequent words in negative and positive headlines about Trump, expressions like "White House", "republican", "leader", "American" and "administration" appear quite often in both cases. Frequent expressions that are more exclusive to negative news are "travel ban", "war", "attack", "threat" and "North Korea", and filtered samples containing such words suggest that the journal used to criticize the former president for his international diplomacy.

![Trump's Word Cloud](/images/trumps_word_cloud.png)

- In contrast to Trump's word cloud, Biden's positive headlines seem to be more about vaccinating the entire country against Covid-19 with a big investment, as suggested by the frequent expressions "vaccination", "trillion", "million", "pandemic" and "plan". On the other hand, "Afghanistan" and "climate change" are more exclusive of Biden's negative headlines. In case of samples containing "Afghanistan", the president was criticized for his decision of withdrawing American troops, which led to violent episodes and popular frustration. However, headlines containing "climate change" seem to be false negatives, because they carry mostly positive ideas but succeeded by the negative word "fight". This is one of the limitations of lexicon based approaches.

![Biden's Word Cloud](/images/bidens_word_cloud.png)

## Running the Notebook

First unzip the CSV files in `data.zip` to a folder `data/`, then install the package versions mentioned in part **3. Method**. This should be enough to run all notebook cells. There are some notes about running cells along the markdown blocks.


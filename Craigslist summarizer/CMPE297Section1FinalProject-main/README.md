# CMPE297-Section1
## FinalProject - Craigslist Ad Summarizer 

------------------------------------------------------------------------------

Project by Group-2
* Leonid Grekhov
* Naga Venkata Sai Sathwik Edupuganti
* Jihyeok Choi

## Project Overview
In our research we found an interesting problem when it came to searching for items when browsing the craigslist website. Most postings had inconsistent descriptions, sometimes being too long or inconsistent with the filled-out data fields and title descriptions. In our project, we chose to focus on speeding up the process of consuming the information in the postings by summarizing the descriptions made by the poster into short and to-the-point descriptions through the use of NLP models. 


## Dataset
For our dataset we decided to choose to make the dataset from craigslist ads which include their description. Our current dataset consists of used car sales data but can be adjusted for other items. The main purpose of our dataset is to summarize the craigslist ad descriptions for easier readability. Our current dataset consists of 720 rows and 6 columns of data. The dataset includes price, location, the title of the post, the date posted, and the full description provided by the poster.


## NLP models and techniques utilized
Initial preprocessing included the removal of white spaces and HTML tags around descriptions as the formatting on craigslist is not very user-friendly to web scraping in terms of poster description. Some users incorrectly input their information making it difficult to grab descriptions. We also applied filters to grab more consistent search results in case we must recreate our data frames. 


## Conclusions
After conducting our experimentation we can conclude that this project is valid but can use further implementation such as doing comparisons with the other fields in that dataset to further improve the accuracy of the summarizations such as cross-referencing the titles of the posts against the summarizations to see if the information is matching in both. Furthermore, the process of summarizing every posting is quite lengthy, taking as long as 6 minutes for the entire dataset summarization. Our rouge scores show promise in the accuracy of the summarizations but further finetuning will be required. A transformer that is specifically trained on car posting descriptions would also perform better in this scenario as this summarizer is trained on general data. Below are the rouge scores for the full dataset that we averaged and the time it took to calculate. 


### NLP Models
* Happy transformer
  * T5
  * DistilBART


------------------------------------------------------------------------------

## Result  
- Rouge scores
  
1. DistilBART  

||rouge-1|rouge-2|rouge-3|
|---|:---:|:---:|:---:|
|r|0.83|0.67|0.82|
|p|0.28|0.23|0.27|
|f|0.37|0.30|0.37|
  
2. DistilBART w fine tuning

||rouge-1|rouge-2|rouge-3|
|---|:---:|:---:|:---:|
|r|0.73|0.56|0.72|
|p|0.27|0.21|0.27|
|f|0.36|0.27|0.35|
  
3. T5  

||rouge-1|rouge-2|rouge-3|
|---|:---:|:---:|:---:|
|r|0.83|0.70|0.83|
|p|0.29|0.24|0.29|
|f|0.38|0.31|0.38|
  
4. T5 w fine tuning

||rouge-1|rouge-2|rouge-3|
|---|:---:|:---:|:---:|
|r|0.43|0.31|0.43|
|p|0.38|0.26|0.37|
|f|0.38|0.27|0.38|
  
------------------------------------------------------------------------

## Proposed next steps
Further optimizations of transformers can be conducted. The use of a transformer trained on specific descriptions such as car postings could create more accurate descriptions compared to a transformer pre-trained on general text. 

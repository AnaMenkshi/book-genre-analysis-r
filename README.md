# Book Genre Preference by Age Group (R)

## Overview
This work presents an end-to-end analysis of reader preferences by age group using a Goodreads-derived dataset.  
It includes data cleaning, exploratory data analysis (EDA), statistical summarization, and visualization to investigate whether age influences preference between **Fantasy/Adventure Fiction** and **Real-World Fiction**.

The full workflow is implemented using R Markdown and provided as both `.Rmd` and rendered `.html` reports.



## Objective
This work investigates whether readers’ genre preferences are influenced by age.  
The analysis was conducted entirely in R, incorporating structured data preparation, statistical testing, aggregation, and visualization.  
Specific objectives include:

- Identifying which age group prefers which genre  
- Comparing average ratings by genre and age  
- Visualizing engagement through ratings and reviews  
- Evaluating the hypothesis that older readers prefer Real-World Fiction



## Introduction
This work explores the relationship between reader age groups and their preferences for different book genres, focusing specifically on **Fantasy/Adventure Fiction** and **Real-World Fiction**. Using a Goodreads-derived dataset, it examines whether age influences genre preference and how readers rate books within these genres.  

The analysis employs visualizations, statistical summaries, and interactive plots to identify patterns, validate assumptions, and explore alternative insights.



## Dataset and Resources
The dataset was compiled from public Goodreads ratings and metadata. It includes the following files:

- `books.csv` – Metadata for 10,000 popular books, including author, title, average ratings, and genre  
- `ratings.csv` – User ratings for books (1–5 stars)  
- `to_read.csv` – Books marked as 'to read' by users  
- `book_tags.csv` and `tags.csv` – Tags and genres assigned by users  

Each book and user has a unique ID. All users rated at least two books, with a median of eight ratings per user.

**Key Columns:**

| Column | Description |
|--------|-------------|
| id | Internal row index (optional) |
| book_id | Unique identifier for each book |
| work_id | General version of the book across editions |
| books_count | Number of editions/versions |
| isbn / isbn13 | Standardized book identifiers |
| authors | Name(s) of the book’s author(s) |
| original_publication_year | Year of first publication |
| original_title / title | Book title, often with series info |
| language_code | Language of the book |
| average_rating | Average rating (1–5) |
| ratings_count | Total ratings submitted |
| work_ratings_count | Ratings across all editions |
| work_text_reviews_count | Number of text reviews |
| ratings_1–ratings_5 | Count of 1–5 star ratings |
| image_url / small_image_url | Cover image links |
| category | Genre classification: Fantasy/Adventure or Real-World Fiction |
| age_group | Simulated reader age group: young or adult |


## Thesis and Antithesis
- **Thesis:** Older readers prefer Real-World Fiction the most  
- **Antithesis:** Older readers also engage with Fantasy/Adventure Fiction, showing that genre preference is not strictly determined by age. Ratings indicate personal context and book quality may influence preference more than age alone.


## Methods
- Data cleaning and preprocessing in **R**  
- Heuristic classification of `age_group` and `category`  
- Exploratory data analysis (EDA) including bar charts, scatter plots, radial plots, and mosaic plots  
- Interactive visualizations using `plotly`  
- Statistical aggregation: average ratings, total engagement (`work_rating`)  
- Data merged and normalized using SQL Server for relational schema (authors, genres)  



## Data Preparation
The dataset was cleaned and processed to:

- Normalize title fields  
- Add `age_group` column based on simulated classification  
- Add `category` column based on title-based heuristics  
- Create a new metric: `work_rating = work_ratings_count + work_text_reviews_count`  
- Merge classification information into the main books table  



## Exploratory Data Analysis
Several analyses were conducted to identify patterns:

- Bar charts comparing book count by genre and age group  
- Average ratings for each genre by age group  
- Distribution of ratings 1–5 stars  
- Work rating engagement per genre and age group  
- Scatter and polar plots to highlight trends  


## Key Visual Insights
- Adults gave more 5-star ratings to Real-World Fiction  
- Young readers rated Fantasy/Adventure Fiction similarly high  
- Real-World Fiction showed more outlier ratings among adults  
- Work rating gaps were higher in Real-World Fiction, particularly for adults  



## Conclusion and Recommendations
- The thesis is supported: adults engage more with Real-World Fiction  
- The antithesis also holds partial ground: Fantasy/Adventure Fiction remains well-rated among adults, suggesting contextual or emotional influences  
- Future analyses could incorporate reader profiles or textual content for deeper personalization insights  



## Technical Evaluation
- Implemented using **R** and SQL Server  
- Data manipulation: `dplyr`, `tidyr`  
- Visualization: `ggplot2`, `plotly`, `ggmosaic`  
- Outputs: `.html` and `.docx` reports, `.csv` exports  
- Repository structured for reproducibility and workflow clarity  




## Repository Structure

book-genre-analysis/
│  

├── data/  

│ ├── books.sql

│  

├── reports/  

│ ├── Scripts.R 

│ ├── Scripts.Rmd   

│ └── Scripts.html   


├── .gitignore  
├── LICENSE
└── README.md



## How to Run  


1. Clone the repository:
   
```bash
git clone https://github.com/username/book-genre-analysis.git
```
2. Install required R packages:
   
```bash
install.packages(c("DBI", "odbc", "dplyr", "tidyr", "ggplot2", "ggmosaic", "reshape2", "scales", "plotly"))
```

3.Ensure all datasets are in data/
```bash
Open scripts/Scripts.Rmd in RStudio
```
4.Knit the document to HTML (Scripts.html) to view results

## Author
**Ana Menkshi**

## Disclaimer

**The analyses and visualizations in this work are for analytical and demonstration purposes only and are not intended as official reading advice.**

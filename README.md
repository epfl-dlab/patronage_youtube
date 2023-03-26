# Characterizing Patronage on YouTube

## Project description
This project explores the relationship between content creation and patronage. We try to find out if potential gains of models such as Patreon incentivize content creators to produce more videos and grow their subscription base. Thanks to the YouNiverse dataset [[Ribeiro and West 2020](https://doi.org/10.48550/arxiv.2012.10378)], this can be analyzed in detail: The audience engagement can be measured by the number of views per video, the productivity of the content creators can be evaluated with the number of videos per week posted by the channel, and the interaction with the customers can be measured by the number of comments per videos. 

## Credentials
- **Author**
  - [Francis Murray](https://github.com/francis-murray)
- **Supervisors**
  - [Manoel Horta Ribeiro](https://manoelhortaribeiro.github.io/)
  - [Kristina Gligorić](https://kristinagligoric.github.io/)
- **Hosting lab**: 
  - [Data Science Lab](https://dlab.epfl.ch/), [EPFL](https://www.epfl.ch/en/), Switzerland [<img src="https://dlab.epfl.ch/assets/img/dlab.svg" alt= “dlab_logo” width="20">](https://dlab.epfl.ch/)



## Data
### YouNiverse dataset
[YouNiverse](https://github.com/epfl-dlab/YouNiverse) is a large collection of channel and video metadata from English-language YouTube. YouNiverse comprises metadata for over 136k channels and 72.9M videos published between May 2005 and October 2019, as well as channel-level time series data of weekly subscriber and view counts.

The YouNiverse dataset contains five files:

- `df_channels_en.tsv.gz`: Channel metadata.
- `df_timeseries_en.tsv.gz`: Channel-level time series.
- `yt_metadata_en.jsonl.gz`: Raw video metadata.
- `youtube_comments.tsv.gz`: User-comment matrices.
- `youtube_comments.ndjson.zst`: Raw comments.

### Graphtreon dataset

The Graphtreon dataset was crawled by Manoel Ribeiro, and contains three files:

- `creators.csv`: List with all creator names.
- `final_processed_file.jsonl.gz`: All Graphteon time series.
- `pages.zip:` Raw HTML of the pages in Graphteon.


## Code organisation

### EDA
*Notebook: [exploratory_data_analysis.ipynb](https://github.com/epfl-dlab/patronage_youtube/blob/main/exploratory_data_analysis.ipynb)*
- 0. Files and brief explanation of those
- 1. Exploratory Data Analysis (EDA)
  - 1.1. YouNiverse dataset
    - 1.1.1 Channel metadata
    - 1.1.2 YouTube Channels time-series data
    - 1.1.3 Raw video metadata
    - 1.1.4 user-comment matrices
    - 1.1.5 raw comments
  - 1.2. Graphtreon dataset
    - 1.2.1 List with all creator names.
    - 1.2.2 All graphtreon time-series
    - 1.2.3 Raw html of the pages in graphteon.


### Preprocessing
*Notebook: [preprocessing.ipynb](https://github.com/epfl-dlab/patronage_youtube/blob/main/preprocessing.ipynb)*
- 1. Preprocess data
  - 1.1. Preprocess YouTube metadata
  - 1.2 Link YT channels and Patrons
  - 1.3 Filter YouTube timeseries - Restrict YouTube channels (4 filters)
  - 1.4 Preprocess Graphtreon timeseries



### Characterizing Patronage on YouTube
*Notebook: [patronage_youtube.ipynb](https://github.com/epfl-dlab/patronage_youtube/blob/main/patronage_youtube.ipynb)*
- 1. Load data
  - 1.0 Preprocessing
  - 1.1. Load YouTube metadata
  - 1.2 Load "Link" dataframe (channel/patreon)
  - 1.3 Load YouTube timeseries
  - 1.4 Load Graphtreon dataset
  - 1.5 Select top patreon accounts (> 200 patrons)
- 2. Jointly examine time series related to patronage and YouTube statistics
  - 2.1 Detecting bursts (breakpoints) of incoming patrons
- 3. Granger causality
  - 3.1 Compute Granger Tests
  - 3.2 Granger causality plots
- 4. Observational Study
  - 4.1 Select "treated" accounts
  - 4.2 Select "control" accounts
  - 4.3 Naive analysis
  - 4.4 Propensity Score Matching (PSM)
  - 4.5 Compute difference between means of the different periods
- 5. Analyze balanced dataset



### Scripts
*Notebook: [scripts.ipynb](https://github.com/epfl-dlab/patronage_youtube/blob/main/scripts/scripts.ipynb)*
- 1. Filter YouTube metadata containing patreon id
- 2. Filter Graphtreon to keep only records which patreon id exists the YouTube metadata


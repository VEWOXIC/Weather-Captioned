# Weather Captioned - First Time Series - Text Multi-modal Dataset

Raw data and processing scripts of Weather Captioned Dataset in TGTSF

## Data Source

The time series data is from the [Max-Planck-Institut fur Biogeochemie, jena](https://www.bgc-jena.mpg.de/wetter/weather_data.html), WS Beutenberg site specifically. The raw data is in the [](./raw_data) folder.

We gather the weather forecast report from a publically avaliable weather forecast platform. The raw data is also in the [](./raw_data) folder. 

## About Caption

The caption is generated with raw data retrieved from a publically avaliable weather forecast source. **No time series is provided to the large language model. **

We provide all the caption we generated in [](./captions). The caption is generated with GPT4 with the scripts in [](./data_process_scripts/weather_caption.py). 

⚠ Caution: The caption of whole dataset can cost over 400 USD with GPT4!!!

Our caption may not be the optimal result. We encourage you to do your own version of captioning. 

## About Pre-embedding

We provide the pre-embedding of the news text in the dataset. You can download them [here](https://drive.google.com/drive/folders/1feNhuijyls5DtxkeDjoKM0lISEF-UaPf?usp=sharing) with `gdown`. The embedding is generated with the scripts in [](./data_process_scripts/embedding_caption_local.ipynb) and [](./data_process_scripts/embedding_caption.ipynb). 

## Data Pipeline

We use two hashtable to manage the news data to make it aligned with the time series in temporal order. The embedding of news taxt is saved as npy file with the hash key as the filename.

Timestamp for time series segment -- [Date2Hash hashtable] --> News hash key list for the timestamp -- [Hash2Emb hashtable] --> Read the embedding from the npy file

You can use the hash2text hashtable to check the news text for the hash key. 

Hash key -- [Hash2Text hashtable] --> News text

## 


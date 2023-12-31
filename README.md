﻿
# Synthia - A Generative AI Chatbot

Synthia's a generative AI Chatbot assisting users with their queries on the MOAs made available by the City of San Jose. This generative AI chatbot is trained on a collection of PDF Documents - Memorandum of Agreement (MOAs) signed between the City of San Jose and various bargaining units in the City.

## Poetry for managing Dependencies

Poetry is a powerful tool for managing Python dependencies and packaging our project. It simplifies the process of handling project dependencies and ensures reproducibility by generating a 'pyproject.toml' file.

## Poetry Usage

To start using Poetry for the project, follow these steps:

1. Installation: pip install poetry

2. Initializing Poetry: poetry init

Package name [synthia_anaconda]:  synthia-anaconda

Version [0.1.0]:  0.1.0

Description []:  Generative AI Chatbot for the City of San Jose

Author [None, n to skip]:  Koushik Modekurti <koushik.modekurti@sjsu.edu>

License []:

Compatible Python versions [^3.11]:  ^3.11

3. Adding Dependencies: 

poetry add requests 

Poetry will automatically update your pyproject.toml file.

4. Creating a Virtual Environment: 

poetry install

5. Activate Virtual Environment:

poetry shell

5. Check the environment information:

poetry env information
## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

`WATCH_DIRECTORY`

`GCS_KEY_PATH`

`GCP_PROJECT_ID`

`GCS_BUCKET_NAME`

`OPENAI_API_KEY`

`OPENAI_API_BASE`

`OPENAI_EMBEDDING_ENGINE`

`OPENAI_ENGINE`

`GRAPHD_HOST`

`GRAPHD_PORT`

`NEBULA_USER`

`NEBULA_PASSWORD`

`NEBULA_ADDRESS`


## Documentation

1. Data Ingestion :

    We have established a robust data ingestion pipeline to efficiently retrieve data from the source webpages, which can be accessed at - 
https://www.sanjoseca.gov/your-government/departments-offices/office-of-the-city-manager/employee-relations/labor-relations-information 

The scraped PDF documents are stored in a designated local directory for easy access and reference. The pipeline is designed to automatically detect and handle newly added PDF files. When the scraper identifies a new document, it seamlessly pushes it to a Google Cloud Storage (GCS) Bucket.

2. Data Understanding : 

Once the data is safely stored in the GCS Bucket, the data understanding process commences. Data is fetched from the GCS Bucket and undergoes basic data understanding techniques to make it ready for analysis and further use.

Data Understanding consists of following steps :

-> Data Collection Procedure
-> Descriptive Statistics of the data
-> Content Exploration
-> Data Quality Report Generation
-> Potential Challenges Identification
-> Preliminary Text Analysis

3. Data Preparation :

After Data Understanding, data preparation and transformation is undertaken.

Data Preparation involves following steps:
    
-> Data Preparation (Training, Validation and Test Data Generation)
-> Data Cleaning
-> Text-Tokenization
-> Documnent Structuring and Chunking
-> Initial Feature Engineering
-> Defining Service Context
-> Defining Storage Context
-> Setting up Nebula GraphDB in Docker Containers
-> Data Transformation (Chunks Embeddings & Knowledge Graph Extraction)

![Why LLMs for Knowledge Graph Extraction](https://github.com/Koushik15042000/Synthia/blob/main/assets/img/Why_LLM_for_KG_Extraction.png?raw=true)

-> Vector Indexing
-> Knowledge Graph Indexing

![Knowledge Graph Building with LLM & their Indexing](https://github.com/Koushik15042000/Synthia/blob/main/assets/img/KG_Building_Indexing.png?raw=true)


4. Data Modeling :

Data Modeling includes the following tasks :

-> Text2Cypher Query Engine Modeling

![Text2Cypher with LLM](https://github.com/Koushik15042000/Synthia/blob/main/assets/img/Text2Cypher_with_LLM.png?raw=true)
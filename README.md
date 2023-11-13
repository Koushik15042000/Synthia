
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


## Documentation

1. Data Ingestion :

    We have established a robust data ingestion pipeline to efficiently retrieve data from the source webpages, which can be accessed at - 
https://www.sanjoseca.gov/your-government/departments-offices/office-of-the-city-manager/employee-relations/labor-relations-information 

The scraped PDF documents are stored in a designated local directory for easy access and reference. The pipeline is designed to automatically detect and handle newly added PDF files. When the scraper identifies a new document, it seamlessly pushes it to a Google Cloud Storage (GCS) Bucket.

2. Data Understanding : 

    Once the data is safely stored in the GCS Bucket, the data understanding process commences. Data is fetched from the GCS Bucket and undergoes basic data understanding techniques to make it ready for analysis and further use.

    Data Understanding consists of following steps :

        1. Data Collection Procedure
        2. Descriptive Statistics of the data
        3. Content Exploration
        4. Data Quality Report Generation
        5. Potential Challenges Identification
        6. Preliminary Text Analysis

3. Data Preparation :

    After Data Understanding, data preparation and transformation is undertaken.

    Data Preparation involves following steps:
    
        1. Data Preparation (Training, Validation and Test Data Generation)
        2. Data Cleaning
        3. Text-Tokenization
        4. Documnent Structuring and Chunking
        5. Initial Feature Engineering
        6. Defining Service Context
        7. Defining Storage Context
        8. Setting up Nebula GraphDB in Docker Containers
        9. Data Transformation (Chunks Embeddings & Knowledge Graph Extraction)

        ![Why LLMs for Knowledge Graph Extraction](./assets/img/Why_LLM_for_KG_Extraction.png)

        10. Vector Indexing
        11. Knowledge Graph Indexing

        ![Knowledge Graph Building with LLM & their Indexing](./assets/img/KG_Building_Indexing.png)


4. Data Modeling :

    Data Modeling includes the following tasks :

        1. Text2Cypher Query Engine Modeling

        ![Text2Cypher with LLM](./assets/img/Text2Cypher_with_LLM.png)
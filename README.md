# Doggy Delights

## Data Gathering & Warehousing

DSSA-5102 - Spring 2025

*Data Science and Strategic Analytics Graduate Program* - [Stockton University](https://stockton.edu)

![Doggy Delights logo](https://github.com/Decabra/pet-puffs/blob/da7e229e5bfd86a678aeaf549bcc0936b8842103/images/doggy_delights_gwp_logo.png)

### Languages & Environment

- Python, SQL, Google Colab, Jupyter Notebook, MySQLWorkbench, GitHub

### Mission

Doggy Delights is a fictitious company that exists to enhance the bond between pets and their owners by delivering innovative, unforgettable treat experiences for all.

### Data Sources

- The dog breed data set was extracted from the [American Kennel Club website](https://www.akc.org/) by [tmfilho](https://github.com/tmfilho/akcdata). All rights to the information contained here belong to the AKC.
- Add other sources here
- product_catalog, treat_consumption, and survey_response data was generated using the [Faker Python package](https://pypi.org/project/Faker/) and custom scripts.

### Data Cleaning and Transformation

Python was used to clean and transform the Doggy Delights dataset. The following actions were performed:

- converted all coluimn names to lowercase with no spaces or special characters to better work with SQL
- removed duplicate rows if they were identical
- removed leading and trailing whitespace characters from column names
- removed unused columns from the American Kennel Club dataset
- checked for outliers
- replaced NaN values with None, Unknown, or 0 values depending on column needs

### Formulas Used in Column Creation

### Data Dictionary

#### dog_breed

| Column Name            | Definitions                    | Example |
| ---------------------- | ------------------------------ | --------|
| breed_id               | a unique integer for each athlete | 3 |
| breed                  | the specifc dog breed         | Labrador Retriever |
| temperament            | breed temperament described in keywords | Energetic, Alert, Curious |
| popularity             | popularity ranking  (1-195)    | 5 |
| min_height             | minimum height in cm           | 30.48 |
| max_height             | maximum height in cm           | 40.64 |
| min_weight             | minimum weight in kg           | 5.443108 |
| max_weight             | maximum weight in kg           | 7.257478 |
| min_expectancy         | minimum life expectancy in years | 12.0 |
| max_expectancy         | maximum life expectancy in years | 15.0 |
| energy_level_value     | numerical value representing energy level | 0.8 |
| energy_level_category  | categorization of energy level | Energetic |
| trainability_value     | numerical value representing trainability | 0.6 |
| trainability_category  | categorization of trainability | Agreeable |
| demeanor_value         | numerical value of reaction to strangers or other pets | 0.4 |
| demeanor_category      | categorization of reaction to strangers and other pets | Reserved with Strangers |

#### pet

| Column Name            | Definitions                    | Example |
| ---------------------- | ------------------------------ | ------- |
| id                     | a unique integer for each pet  | 10579 |
| name                   | name of the pet                | Moose |
| dob                    | pet's date of birth            | 2015-10-08 |
| sex                    | gender of the pet              | Neutered Male	|
| color                  | color of the pet               | White/Brown |
| age                    | age of the pet when recorded   | 2 years |
| type                   | dog, cat or other              | Dog |
| breed_id               | foreign key connecting the dog_breed table | 26 |

#### pet_outcome

| Column Name            | Definitions                    | Example |
| ---------------------- | ------------------------------ | ------- |
| id                     | a unique integer for each pet outcome | 147 |
| outcome_type           | Adoption, Return to Owner, Transfer, Rto-Adopt, Euthanasia, Died, Missing, Disposal, Stolen, Lost, Relocate | Adoption | Adoption |
| outcome_subtype        | additional notes regarding the outcome | Out State |
| outcome_datetime       | date and time of the outcome     | 2019-05-08 06:20:00 PM |
| pet_id                 | foreign key connecting the pet table | 26 |

#### region

| Column Name            | Definitions                    | Example |
| ---------------------- | ------------------------------ | ------- |
| id                     | a unique integer for each region | 19 |
| state                  | state name                       | New Jersey |
| pet_ownership_rate     | rate of pet ownershit in the region | 29.1 |
| average_income         | average income of the region     | 89296 |

#### product_catalog

| Column Name            | Definitions                      | Example |
| ---------------------- | -------------------------------- | ------- |
| id                     | a unique integer for each product | 4 |
| name                   | name of the product              | Bark Bites |
| flavor                 | flavor of the product            | Chicken & Rice |
| size                   | recommended size of dog          | Medium |
| launch_date            | date the product was released    | 2023-02-15 |
| recommended_for        | recommended type of dog          | Active |

#### treat_consumption

| Column Name            | Deinitions                       | Example |
| ---------------------- | -------------------------------- | ------- |
| id                     | a unique integer for consumption | 24 |
| quantity               | number of treats consumed    | 7 |
| frequency              | how often treats are consumed | |
| dog_breed_id           | foreign key connecting the dog_breed table | 6 |
| product_catalog_id     | foreign key connecting the product_catalog table | 4 |


#### survey_response

| Column Name            | Definitions                      | Example |
| ---------------------- | -------------------------------- | ------- |
| id                     | a unique integer for each survey response | 235 |
| concern                | option of type of cncern the dog owner may have | |
| interest_level         | how interested the dog was with the treat given     | |
| respondant_name        | The name of the pet owner    | Cesar Millan |
| submission_date        | date of survey submission        | 2025-04-19 |
| dog_breed_id           | foreign key connecting the dog_breed table | 6 |
| product_catalog_id     | foreign key connecting the product_catalog table | 4 |

### Regulations to Using this Data

You are free to use this data in anyway you see fit, have fun. The [source data](https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results) is licensed under the [CCO: Public Domain](https://creativecommons.org/publicdomain/zero/1.0/), so please respect any of their wishes and credit them where appropriate.

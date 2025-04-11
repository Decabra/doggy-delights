# Pet Puffs

## Data Gathering & Warehousing

## DSSA-5102 - Spring 2025

*Data Science and Strategic Analytics Graduate Program* - [Stockton University](https://stockton.edu)

![Pet Puffs logo](https://github.com/Decabra/pet-puffs/blob/d152c8dd62c9cb3ffb36f3fd7f18228cea91d5cc/images/pet_puffs_logo.png)

### Languages & Environment

- Python, SQL, Google Colab, Jupyter Notebook, MySQLWorkbench, GitHub

> [!NOTE]
> This is a satirical company and we do not endorse or support its mission and products.

Pet Puffs exists to enhance the bond between pets and their owners by delivering innovative, unforgettable smoking experiences for all. 

### Data Sources

- The dog breed data set was extracted from the [American Kennel Club website](https://www.akc.org/) by [tmfilho](https://github.com/tmfilho/akcdata). All rights to the information contained here belong to the AKC.
- Add other sources here

### Data Cleaning and Transformation

Python was used to clean and transform the Pet Puffs dataset.  The following actions were performed:

- converted all coluimn names to lowercase with no spaces or special characters to better work with SQL
- removed duplicate rows if they were identical
- removed leading and trailing whitespace characters from column names
- removed unused columns from the American Kennel Club dataset
- checked for outliers

### Formulas Used in Column Creation

### Data Dictionary

#### dog_breed

| Column Name            | Definitions                    |
| ---------------------- | ------------------------------ |
| breed_id               | a unique integer for each athlete |
| breed                  | the speciifc dog breed         |
| temperament            | breed temperament described in keywords |
| popularity             | popularity ranking  (1-195)    |
| min_height             | minimum height in cm           |
| max_height             | maximum height in cm           |
| min_weight             | minimum weight in kg           |
| max_weight             | maximum weight in kg           |
| min_expectancy         | minimum life expectancy in years |
| max_expectancy         | maximum life expectancy in years |
| group                  | one of 9 breed groups designated by the akc |
| energy_level_value     | numerical value representing energy level |
| energy_level_category  | categorization of energy level |
| trainability_value     | numerical value representing trainability |
| trainability_category  | categorization of trainability |
| demeanor_value         | numerical value of reaction to strangers or other pets |
| demeanor_category      | categorization of reaction to strangers and other pets |

#### pet

| Column Name            | Definitions                    |
| ---------------------- | ------------------------------ |
| id                     | a unique integer for each pet  |
| breed_id               | foreign key connecting the dog_breed table |
| name                   | name of the pet                |
| dob                    | pet's date of birth            |
| sex                    | gender of the pet              |
| color                  | color of the pet               |
| age                    | age of the pet when recorded   |
| type                   | dog, cat or other              |

#### pet_outcome

| Column Name            | Definitions                    |
| ---------------------- | ------------------------------ |
| id                     | a unique integer for each pet outcome |
| pet_id                 | foreign key connecting the pet table |
| outcome_type           |                                  |
| outcome_subtype        |                                  |
| outcome_datetime       | date and time of the outcome     |

#### region

| Column Name            | Definitions                    |
| ---------------------- | ------------------------------ |
| id                     | a unique integer for each region |
| city                   | city name                      |
| state                  | state name                       |
| county                 | county name                      |
| pet_ownership_rate     | rate of pet ownershit in the region |
| average_income         | average income of the region     |

#### product_catalog

| Column Name            | Definitions                      |
| ---------------------- | -------------------------------- |
| id                     | a unique integer for each product |
| name                   | name of the product              |
| flavor                 | flavor of the product            |
| nic_level              | level of nicotine in the product |
| size                   | size of the product              |
| launch_date            | date the product was released    |
| recommended_for        | target audience of the product   |

#### cigarette_consumption

| Column Name            | Deinitions                       |
| ---------------------- | -------------------------------- |
| id                     | a unique integer for consumption |
| breed_id               | foreign key connecting the dog_breed table |
| product_id             | foreign key connecting the product_catalog table |
| quantity               | number of cigarettes consumed    |
| frequency              | how often cigarettes are consumed |

#### survey_response

| Column Name            | Definitions                      |
| ---------------------- | -------------------------------- |
| id                     | a unique integer for each survey response |
| breed_id               | foreign key connecting the dog_breed table |
| product_id             | foreign key connecting the product_catalog table |
| concern_flag           |                                  |
| interest_level         |                                  |
| submission_date        | date of survey submission        |

### Regulations to Using this Data

You are free to use this data in anyway you see fit, have fun. The [source data](https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results) is licensed under the [CCO: Public Domain](https://creativecommons.org/publicdomain/zero/1.0/), so please respect any of their wishes and credit them where appropriate.
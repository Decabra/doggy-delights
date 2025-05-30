# Doggy Delights

## Data Gathering & Warehousing

DSSA-5102 - Spring 2025

*Data Science and Strategic Analytics Graduate Program* - [Stockton University](https://stockton.edu)

![Doggy Delights logo](https://github.com/Decabra/doggy-delights/blob/124cb054556644048abd83cc5b2bb20d842968dd/images/doggy_delights_fixed_logo.png)

### Languages & Environment

- Python, SQL, Google Colab, Jupyter Notebook, MySQLWorkbench, GitHub

### Mission

Doggy Delights is a fictitious company that exists to enhance the bond between pets and their owners by delivering innovative, unforgettable treat experiences for all.

### Data Sources

- The dog breed data set was extracted from the [American Kennel Club website](https://www.akc.org/) by [tmfilho](https://github.com/tmfilho/akcdata). All rights to the information contained here belong to the AKC.
- The pet and pet outcomes dataset was extracted from them [Austin Animal Center Outcomes](https://catalog.data.gov/dataset/austin-animal-center-outcomes) and maintained by [ASO Open Data Asset Owners (Animal Services)](http://data.austintexas.gov). This dataset is intended for public access and use.
- The pet ownership by state dataset was extracted from [The American Veterinary Medical Association (AVMA)](https://ebusiness.avma.org/Files/ProductDownloads/2019%20ECO-PetDemoUpdateErrataFINAL-20190501.pdf) by the [World Population Review](https://worldpopulationreview.com/state-rankings/pet-ownership-statistics-by-state). All rights to the information contained here belong to the AVMA.
- The median household income by state dataset was extracted from the [US Census Bureau](https://data.census.gov/table/ACSST1Y2021.S1903?t=Income+(Households,+Families,+Individuals)&g=010XX00US$0400000&moe=false&tp=true) by the [World Population Review](https://worldpopulationreview.com/state-rankings/median-household-income-by-state). All rights to the information contained here belong to the US Census Bureau.
- product_catalog, treat_consumption, and survey_response data was generated using the [Faker Python package](https://pypi.org/project/Faker/) and custom scripts.

### Data Cleaning and Transformation

Python was used to clean and transform the Doggy Delights dataset. The following actions were performed:

- converted all coluimn names to lowercase with no spaces or special characters to better work with SQL
- removed duplicate rows if they were identical
- removed leading and trailing whitespace characters from column names
- removed unused columns
- validated that data conforms to specific formats (date, integer, float, etc.)
- checked for outliers
- replaced NaN values with None, Unknown, or 0 values depending on column needs

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
| pet_ownership_pct      | rate of pet ownershit in the region | 29.1 |
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
| frequency              | how often treats are consumed | daily |
| dog_breed_id           | foreign key connecting the dog_breed table | 6 |
| product_catalog_id     | foreign key connecting the product_catalog table | 4 |


#### survey_response

| Column Name            | Definitions                      | Example |
| ---------------------- | -------------------------------- | ------- |
| id                     | a unique integer for each survey response | 235 |
| concern                | option of type of cncern the dog owner may have | Dog refused to eat |
| interest_level         | how interested the dog was with the treat given     | 3 |
| respondant_name        | The name of the pet owner    | Cesar Millan |
| submission_date        | date of survey submission        | 2025-04-19 |
| dog_breed_id           | foreign key connecting the dog_breed table | 6 |
| product_catalog_id     | foreign key connecting the product_catalog table | 4 |

### Results

Our data aids Doggy Delights in making critical business decisions, notably:
- How best to spend marketing budget to efficiently target new and existing customers
- Whom to feature in product marketing

### Visualizations

![Top 3 Most Owned Dog Breeds](https://github.com/Decabra/doggy-delights/blob/5f46cbedc0a135e0399256611c07593d586a170a/images/top-3-owned.png)

![Top 3 Most Adopted Breeds](https://github.com/Decabra/doggy-delights/blob/6ec76912b32f62fcc4dfe6045c90210b997ec5c0/images/top-3-adopted.png)

![Top 3 Most Liked Products](https://github.com/Decabra/doggy-delights/blob/6ec76912b32f62fcc4dfe6045c90210b997ec5c0/images/top-3-products.png)

![Top 3 Avg Life Expectancies](https://github.com/Decabra/doggy-delights/blob/6ec76912b32f62fcc4dfe6045c90210b997ec5c0/images/top-3-life.png)

![Pet Ownership Data by State](https://github.com/Decabra/doggy-delights/blob/ce72e95c682486f3e7a7ccdd3d6f9809a1ca934a/images/pet-ownership-state.png)

![Median Income by State](https://github.com/Decabra/doggy-delights/blob/ce72e95c682486f3e7a7ccdd3d6f9809a1ca934a/images/median-income-state.png)

![Largest Breeds that are Energetic](https://github.com/Decabra/doggy-delights/blob/35ed1c59b5dbf0a11893a84f17471905ec0eeee6/images/largest-energetic.png)

![Most Popular Dog Breeds](https://github.com/Decabra/doggy-delights/blob/35ed1c59b5dbf0a11893a84f17471905ec0eeee6/images/most-popular.png)

### Regulations to Using this Data

You are free to use this data in anyway you see fit, have fun. The [source data](https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results) is licensed under the [CCO: Public Domain](https://creativecommons.org/publicdomain/zero/1.0/), so please respect any of their wishes and credit them where appropriate.

# House Price Prediction
Predicting house price for house listings.

## Dataset
The dataset is found in `house_listings.csv`

We have the following features:
* **category**: Types of building ({'Yeni tikili' : 'New building', 'Köhnə tikili' : 'Old building'}).
* **price**: Price of the house.
* **currency**: Currency of the house price.
* **price_1m2**: One square meter price for the house.
* **title**: Title of the house advertisement.
* **address**: The address where the house is located.
* **floor**: For instance: 7/9. In this context, "7" represents the floor of the house, while "9" indicates the floor of the building.
* **area**: Area of the house.
* **title_deed**: Title deed of the house ({'yoxdur' : 'no'. 'var' : 'yes'}).
* **repair**: Repair of the house ({'yoxdur' : 'no'. 'var' : 'yes'}).
* **mortgage**: Chances of getting a mortgage on the house ({'yoxdur' : 'no'. 'var' : 'yes'}).
* **url**: Url of the house.
* **room_number**: How many rooms does the house have?

## Data Cleaning
This research is heavily built on data cleaning and transformation. It is to be note that there's no such thing as a correct methodology to be used but rather involves the use of both fine-tuned and crude tools in trying to make the data more appropriate for further use.

During cleaning, some realizations are discovered at a later stage which would have made us avoid doing unneccessary work if known earlier. Given that I still included those work, you will need to follow along to discover them as well.

Here are some things carried out during cleaning:
1. `Trying to understand the data:` This is where you realize issues with the data and have to use intuition and code to discover this issues. We did the following:
    - Check missing values count for each feature and the overall percentage of missing count for the dataset.
    - Verify if there are rows with fully missing values so we can drop. **This should be paid more attention to and we didn't and paid a heavy price for it.**
    - Check unique values per feature. This helps us to know the cardinality of categorical features.
2. `Ideas for Cleaning:` From the above process, we need to choose methods for handling issues discovered. 
    - We made usage of **imputation** by **most_frequent** and **median** to handle missing values depending on the nature of data (categorical or numerical).
    - **Default values** are used especially for text data without an inherent [interestingness] meaning.
3. `Peforming cleaning:` We used approaches outlined above and perform cleaning. 
    - During this process, we realize some malformed data which needed further cleaning before imputation e.g area values containing their units of measurment(metres square).
    - For someting like **floor**, we had to feature engineer it into three features; **apartment_floor**, **building_floors**, and **floor_ratio**.
    - We combine all cleaned features into our cleaned dataset. We do step 1 of cleaning again and discover **url** is useless given that they gave no important information when opened on a browser. And also given each url is unique, it doesn't help us. So we drop it from our dataset.
    - After droping it, we check for duplicates again we discovered that our previous famous _37_ missing value rows should have been dropped. Or at least we should have checked rows with more than 50% of missing data. We just go ahead and drop these fields.
    - We drop **title** as well since it is a combination of other fields and not useful for our model.
    - We drop duplicates rows. It is important to note that it is peferable to drop fields not relevant to our study first before checking for duplicates.
    - We perform **encoding** of categorical fields i.e. ordinal and nominal data. While doing this, we drop features with high cardinality as this can result to overfitting. 

## Exploratory Data Analysis (EDA)
We get visualization of the data using descriptive statistics and visualization.

## Modeling
We build a multivariate linear regression model to handle the dataset.

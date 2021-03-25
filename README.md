# capstone_2

# Beth Sung

## proposal 1: Bengali AI Handwritten Grapheme Classification

### Classify the components of handwritten Bengali

[dataset](https://www.kaggle.com/c/bengaliai-cv19)


**Files**

* train.csv

    - image_id: the foreign key for the parquet files
    - grapheme_root: the first of the three target classes
    - vowel_diacritic: the second target class
    - consonant_diacritic: the third target class
    - grapheme: the complete character. Provided for informational purposes only, you should not need to use this.

    * test.csv

    - Every image in the test set will require three rows of predictions, one for each component. 
    This csv specifies the exact order for you to provide your labels. 
    - row_id: foreign key to the sample submission 
    - image_id: foreign key to the parquet file 
    - component: the required target class for the row (grapheme_root, vowel_diacritic, or consonant_diacritic)

* sample_submission.csv

    - row_id: foreign key to test.csv
    - target: the target column

* (train/test).parquet

    - Each parquet file contains tens of thousands of 137x236 grayscale images. The images have been provided in the parquet format for I/O and space efficiency. Each row in the parquet files contains an image_id column, and the flattened image.

* class_map.csv

    - Maps the class labels to the actual Bengali grapheme components.*




## proposal 2: Sales Time Series Forecasting

### predicting item sales at California store

[dataset](https://www.kaggle.com/c/sales-time-series-forecasting-ca-afcs2020/data)

**Files**

The historical data range from 2011-01-29 to 2016-06-19 (sales [d_1 - d_1941]). 
Thus, the Hobbies products have a (maximum) selling history of 1,9412 days / 5.4 years 
(test data of h=28 days not included).

* calendar_afcs2020.csv 
    - Contains information about the dates on which the products are sold.
* sales_train_validation_afcs2020.csv 
    - Contains the historical daily unit sales data per product by CA3 store [d_1 - d_1913]. This can be used as a training set for models.

    * sampleSubmission_afcs2020.csv 
    - The correct format for submissions. the evaluation rows, this corresponds to [d_1942 - d_1969], 28 forecast days (F1-F28).
* sell_prices_afcs2020.csv 
    - Contains information about the price of the products sold by CA3 store and date
* sales_train_evaluation_afcs2020.csv 
    - Complete dataset that includes sales [d_1 - d_1941] and serves to evaluate from [d_1914 - d_1941], 28 days of the complete training sample (sales_train_validation_afcs2020.cs).




## proposal 3: Shopee - Price Match Guarantee

### Determine if two products are the same by their images

[dataset](https://www.kaggle.com/c/shopee-product-matching/overview)

**Files**

* [train/test].csv 
- the training set metadata. Each row contains the data for a single posting. 
Multiple postings might have the exact same image ID, but with different titles or vice versa.

- posting_id - the ID code for the posting.
- image - the image id/md5sum.
- image_phash - a perceptual hash of the image.
- title - the product description for the posting.
- label_group - ID code for all postings that map to the same product. Not provided for the test set.

* [train/test]images 
    - the images associated with the postings.

* sample_submission.csv 
    - a sample submission file in the correct format.
    - posting_id - the ID code for the posting.
    - matches - Space delimited list of all posting IDs that match this posting. Posts always self-match. Group sizes were capped at 50, so there's no need to predict more than 50 matches.

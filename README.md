# AIM:
To read the given data and perform Feature Encoding and Transformation process and save the data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Encoding for the feature in the data set.
STEP 4:Apply Feature Transformation for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE ENCODING:
1. Ordinal Encoding
An ordinal encoding involves mapping each unique label to an integer value. This type of encoding is really only appropriate if there is a known relationship between the categories. This relationship does exist for some of the variables in our dataset, and ideally, this should be harnessed when preparing the data.
2. Label Encoding
Label encoding is a simple and straight forward approach. This converts each value in a categorical column into a numerical value. Each value in a categorical column is called Label.
3. Binary Encoding
Binary encoding converts a category into binary digits. Each binary digit creates one feature column. If there are n unique categories, then binary encoding results in the only log(base 2)ⁿ features.
4. One Hot Encoding
We use this categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.

# Methods Used for Data Transformation:
  # 1. FUNCTION TRANSFORMATION
* Log Transformation
* Reciprocal Transformation
* Square Root Transformation
* Square Transformation
  # 2. POWER TRANSFORMATION
* Boxcox method
* Yeojohnson method

# CODING AND OUTPUT:

import pandas as pd
    df=pd.read_csv("/content/Encoding Data (1).csv")
    df

![Screenshot 2024-10-05 112832](https://github.com/user-attachments/assets/853bc18c-35fc-459a-b351-17c2df13f6f7)

 from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
     pm=['Hot','Warm','Cold']
     e1=OrdinalEncoder(categories=[pm])
     e1.fit_transform(df[["ord_2"]])

![Screenshot 2024-10-05 112839](https://github.com/user-attachments/assets/9fb0cf8b-b105-45d3-9f6a-7b54c0109b98)

df['bo2']=e1.fit_transform(df[["ord_2"]])

![Screenshot 2024-10-05 112849](https://github.com/user-attachments/assets/320b5a25-9e16-4da1-9d77-ab86c081795a)

le=LabelEncoder()
     dfc=df.copy()
     dfc['ord_2']=le.fit_transform(dfc['ord_2'])

![Screenshot 2024-10-05 112900](https://github.com/user-attachments/assets/bf7dd03e-044a-46f0-a694-25ac04fe5006)

from sklearn.preprocessing import OneHotEncoder
       ohe=OneHotEncoder(sparse=False)
       df2=df.copy()
       enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))

![Screenshot 2024-10-05 112908](https://github.com/user-attachments/assets/964c1654-b338-4c45-85fd-9c588565f038)

 df2=pd.concat([df2,enc],axis=1)

![Screenshot 2024-10-05 112922](https://github.com/user-attachments/assets/50c0cfdd-9b81-4b5a-8c0a-098523cceaa1)

from category_encoders import BinaryEncoder
         df=pd.read_csv("/content/data.csv")
         be=BinaryEncoder()
         nd=be.fit_transform(df['Ord_2'])
         dfb=pd.concat([df,nd],axis=1)
         dfb1=df.copy()

![Screenshot 2024-10-05 112932](https://github.com/user-attachments/assets/75e05bb9-0995-48e3-acbf-00507fe7fd8f)

  from category_encoders import TargetEncoder
         te=TargetEncoder()
         cc=df.copy()
         new=te.fit_transform(X=cc["City"],y=cc["Target"])
         cc=pd.concat([cc,new],axis=1)

![Screenshot 2024-10-05 112942](https://github.com/user-attachments/assets/1e807376-57dc-4ffd-9d30-9c9562bec0c7)
![Screenshot 2024-10-05 112950](https://github.com/user-attachments/assets/9d6168d4-6234-407d-9326-3145c5c6d80f)
![Screenshot 2024-10-05 112959](https://github.com/user-attachments/assets/5c452f0b-c9e2-4bda-9bd8-d98e10255031)
![Screenshot 2024-10-05 113008](https://github.com/user-attachments/assets/9afeef29-9d58-4a35-827f-6378182c2a12)
![Screenshot 2024-10-05 113018](https://github.com/user-attachments/assets/f726cb8e-8715-45ed-8151-8ce41b2822af)

df["Higly Positive Skew_borcox"],parameters=stats.boxcox(df["Highly Positive Skew"])
image


df["Highly Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Highly Negative Skew"])

![Screenshot 2024-10-05 113025](https://github.com/user-attachments/assets/c2c11fa3-5264-420b-9b22-fb6d66a8643c)

from sklearn.preprocessing import QuantileTransformer
         qt=QuantileTransformer(output_distribution='normal')

![Screenshot 2024-10-05 113036](https://github.com/user-attachments/assets/aefca40a-c5fd-48ca-8224-2f2bf05cba61)
![Screenshot 2024-10-05 113044](https://github.com/user-attachments/assets/55c2a96b-44b0-4ceb-bef7-8486812be54b)
![Screenshot 2024-10-05 113058](https://github.com/user-attachments/assets/0189b8ff-600c-4596-a5ae-359accf87f62)
![Screenshot 2024-10-05 113109](https://github.com/user-attachments/assets/ebdf7354-85ea-45f2-8656-75372eec9b08)
![Screenshot 2024-10-05 113125](https://github.com/user-attachments/assets/2400314a-de05-4fd3-9789-5dbb1f8cc44f)
![Screenshot 2024-10-05 113135](https://github.com/user-attachments/assets/eff706ec-34c4-4b61-83ad-d65bda00ba75)
![Screenshot 2024-10-05 113149](https://github.com/user-attachments/assets/f3bca7b8-c6de-45bc-bece-7eb388d61978)
![Screenshot 2024-10-05 113201](https://github.com/user-attachments/assets/3d7253a2-e594-44ca-831c-f880eaa02043)
![Screenshot 2024-10-05 113220](https://github.com/user-attachments/assets/cbc50ff0-6f6a-4628-b0f7-d118676280e8)


# RESULT:
Thus To read the given data and perform Feature Encoding and Transformation process and save the data to a file has successfully executed
       

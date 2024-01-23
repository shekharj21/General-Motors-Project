# General-Motors-Project

## Understanding the UseCase :

![Screenshot (501)](https://github.com/shekharj21/shekharj21/assets/54074505/c05c2615-69b8-49f9-858b-4f068b7b64e5)

1. Vehicel has thord party IoT device which will send the telemetry data (in JSON Format) over the AWS cloud.
2. We need to move the Data from third party AWS to GeneraMotors Azure Cloud.
3. You need to validate the JSON SOmetimes it could incomplete or wrong JSON which needs to be rejected.
4. Once JSON got validate then, data will be stored in the SQL Database which will be further utilized by data science team.


## Project Architecture :
![Screenshot (504)](https://github.com/shekharj21/shekharj21/assets/54074505/28e9998a-9cb4-4eda-9fba-289873de9c84)

1. AWS S3 : Where JSON data is Stored
2. Azure Data Factory : To move the data 
3. Azure function : To Validate the JSON Data
4. Azure SQL Server : Destination

## Create S3 bucket in AWS :

![Screenshot (505)](https://github.com/shekharj21/shekharj21/assets/54074505/3b9424b0-d43e-4530-90d7-464855d47874)

1. login to AWS portal and create S3 Bucket.
2. Add folder 2023
3. add folder 12 inside 2023
4. Add folder 15 inside 12
5. This structure of folder desribes Year----> Month-----> Day------>
6. Add the file inside folder "15"

## create Storage Account and add landing Folder :

![Screenshot (506)](https://github.com/shekharj21/shekharj21/assets/54074505/ae46bb5c-fe51-4fef-b815-260c7a03bf75)


1. Create a Resource Group first.
2. Create a Storage Account in it.
3. Inside storage account, Click on Container and add a Container named as "input".
4. Inside The input Add a Directory named as "Landing".

## Create a Data factory Account :
![Screenshot (507)](https://github.com/shekharj21/shekharj21/assets/54074505/a3b43644-b850-473d-a03f-7911cb069646)


## Running a Pipeline :

![Screenshot (517)](https://github.com/shekharj21/shekharj21/assets/54074505/65e4f80b-946b-466d-a128-c7502da5126b)

1. We know that Source of our data is S3 and Destination is ADLS.
2. We will create a linked service for S3 and ADLS so we can use it in Azure Data Factory.
3. After Successfully connecting, we can open data factory and can click on author tab.
4. in the author tab, select create pipeline and give aname to it.
5. in the source add S3 and hardcode the destination because we want to collect IOt information everydaay and in S3 the files are in this format 'iotsendordata/YYYY/MM/dd'
   - @concat(formatDateTime(utcnow(), 'yyyy'), '/', formatDateTime(utcnow(), 'MM'), '/', formatDateTime(utcnow(), 'dd'), '/')
6. Similarly, At the destination, the data is in Landing folder and we want the same format like 'YYYY/MM/dd'. We need to hardcode with the following code.
   -@concat('landing/'formatDateTime(utcnow(), 'yyyy'), '/', formatDateTime(utcnow(), 'MM'), '/', formatDateTime(utcnow(), 'dd'), '/')
7. ADF will take the iot data every day so make sure while running the pipeline, that day's folder is available in S3 otherwise it will return error.
8. Following is the output of debug operation of ADF pipeline.

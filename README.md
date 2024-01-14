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
   

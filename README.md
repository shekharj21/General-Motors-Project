# General-Motors-Project

## Understanding the UseCase :

![Screenshot (501)](https://github.com/shekharj21/shekharj21/assets/54074505/c05c2615-69b8-49f9-858b-4f068b7b64e5)

1. Vehicel has thord party IoT device which will send the telemetry data (in JSON Format) over the AWS cloud.
2. We need to move the Data from third party AWS to GeneraMotors Azure Cloud.
3. You need to validate the JSON SOmetimes it could incomplete or wrong JSON which needs to be rejected.
4. Once JSON got validate then, data will be stored in the SQL Database which will be further utilized by data science team.


Project Architecture :
![Screenshot (504)](https://github.com/shekharj21/shekharj21/assets/54074505/28e9998a-9cb4-4eda-9fba-289873de9c84)


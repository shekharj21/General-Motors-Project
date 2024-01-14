# General-Motors-Project

## Understanding the UseCase :
1. Vehicel has thord party IoT device which will send the telemetry data (in JSON Format) over the AWS cloud.
2. We need to move the Data from third party AWS to GeneraMotors Azure Cloud.
3. You need to validate the JSON SOmetimes it could incomplete or wrong JSON which needs to be rejected.
4. Once JSON got validate then, data will be stored in the SQL Database which will be further utilized by data science team.

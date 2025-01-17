# NBA-Datalake-for-Analytics
This is an automated NBA data lake that is going  to support some sports analytics. 

## 🚀 Key Features
1. **Data Collection:** Collects NBA data via [SportsData.io](https://sportsdata.io) and stores it in an AWS S3 bucket.
2. **Data Preparation:** Prepares raw data stored in S3 for analytics using AWS Glue.
3. **Data Querying:** Enables querying and analytics on the data using AWS Athena.
4. **Visualization:** Easily visualize data using AWS QuickSight for intuitive dashboards and reports.

## ✅ Prerequisites
1. API Key from https://sportsdata.io and save it in the .env file.
2. **AWS Permissions**: Ensure the required AWS permissions are set up for S3, Glue, and Athena:

   **S3 Permissions**:
   - `s3:CreateBucket`
   - `s3:PutObject`
   - `s3:DeleteBucket`
   - `s3:ListBucket`

   **Glue Permissions**:
   - `glue:CreateDatabase`
   - `glue:CreateTable`
   - `glue:DeleteDatabase`
   - `glue:DeleteTable`

   **Athena Permissions**:
   - `athena:StartQueryExecution`
   - `athena:GetQueryResults`

     
## ⚙️ Setting Up the Project
1. log into your AWS Console and in the cloudshell, use the following command to Create a file: `nano setup_nba_data_lake.py`
2. Paste your Python script from src/setup_nba_data_lake.py.
3. Create an `.env` file: `nano .env` and paste your .env details.
4. After saving the two files, run the command `python3 setup_nba_data_lake.py` to run the python code.
5. Confirm the creation of the S3 bucket.
6. Go to the Athena and run the following query, make sure to select the correct Glue database.  
   ```sql
     SELECT FirstName, LastName, Position, Team
     FROM nba_players
     WHERE Position = 'PG';
     ```
7. To visualize data from Athena using AWS QuickSight, Open a standard account and create a **New Analysis**.
8. Select New dataset and select Athena as the source.
9. Select the database and proceed to visualize the data.
10. You can also use an SQL query to create a specific dataset and proceed to visualize the reqults.

<p>For a more detailed documetation of the project, visit https://medium.com/@violasangut/creating-data-lake-for-nba-analytics-using-amazon-s3-aws-glue-and-amazon-athena-39710e4ca523 </p>


   

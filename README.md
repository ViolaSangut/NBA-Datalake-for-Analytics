# NBA-Datalake-for-Analytics
This is an automated NBA data lake that is going  to support some sports analytics. 

# Key Features

1. Collects NBA DATA and store it in AWS S3 bucket.
2. Prepare the raw data in S3 bucket for analytics by AWS Athena using AWS Glue.
3. Perform querying and analytics on the S3 bucket data directly using schema created by AWS Glue.

# Prerequisites
1. API Key from https://sportsdata.io and save it in the .env file.
2. Ensure the user has required permission for S3, AWS Glue and  Athena
<p>S3: s3:CreateBucket, s3:PutObject, s3:DeleteBucket, s3:ListBucket</p>
<p>Glue: glue:CreateDatabase, glue:CreateTable, glue:DeleteDatabase, glue:DeleteTable </p>
<p>Athena: athena:StartQueryExecution, athena:GetQueryResults</p>

# Setting up the project
1. log into your AWS Console and in the cloudshell, use the following command to create a new file: nano setup_nba_data_lake.py
2. Copy the ython file in setup_nba_data_lake.py and paste it to the file
3. enter the command nano .env and copy the contents of the .env file .
4. After saving the two files, run the command python3 setup_nba_data_lake.py to run the python code.
5. Confirm the creation of the S3 bucket.
6. Go to the Athena and enter the following query, make sure to select the correct Glue database.

   <P>SELECT FirstName, LastName, Position, Team</P>.
   <P>FROM nba_players</P>
   <P>WHERE Position = 'PG';</P>

   

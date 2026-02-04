Design Note

In order to create the pipeline, here is the process I would follow:

1. After spending more time to understand the different types of errors that can appear in each school's data, I would refactor the school-specific extract tasks into a single, more robust function. This way I could iterate through a large number of school files without needing separate logic for each one.
1. Next, I would configure a cloud-based file transfer and storage solution like Amazon S3 or Azure Blob Storage to receive the files from each school, and I would work with school staff to automate a recurring export of their data.
1. At the other end of the pipeline, I would set up a data warehouse solution like AWS Redshift or Azure Databricks so that I could load the clean data, rather than just writing to csv.
1. Finally, I would package and containerize my ETL logic so that it can deployed on a remote server or executed via a serverless compute solution. From there it could either be run on a schedule or triggered in response to various events.

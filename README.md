# Python-Scripts used in big data piplines
## Inquiry_pool_File_watcher.py
    This Script as a whole looks at a secured sftp and gets the most recent files based
    on a particular format and regex stored in a datastore
    
    Some of the main function employed here are a binary search to efficiently search a 
    school format within a table and make the time objects timezone aware , convert all to
    UTC and do calculation in UTC as a good practice 
    
    Also it does account for daylight savings 
    
 ## delivery_scheduler.py
    The delivery scheduler , gets a json file as a api call request from marketo ( one json file per record) 
    The script will create one file per partner by collecting all json objects per partner in one file 
    And finally move files from a inbox S3 bucket to outbox where the files will be ready for ingestion into a database
    
## test_delivery_scheduler.py 
   Has Unit test cases for the functions in delivery_scheduler
    
## s3-sftp_1_9_2020.py
   This is the National Clearinghouse project, The script transports objects on s3 to a secured SFTP folder as a intermediatory step
   
## you_visit_api.py 
  The projects gets leads from the you_visit API for furthur ingestion into a snowflake based postgres datastore, also with a potential bug due to global variables defined which     was rectified causing leakage in parallel run times. 
  
  It hits a api , gets the records and iterates based on records/api call , updates a postgres database , and creates a csv file based on api calls 
  The thing to note is the headers are created dynamically and not hardcoded based on changing heeader requirements by comparing to a previous header.
    
   

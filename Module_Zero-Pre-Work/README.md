# SA-Galaxy-Workshop

Repository to be Used by SAs to facilitate On-Site Galaxy Workshops

## Steps to Prepping for an Onsite Galaxy Workshop

1. Get list of attendees from Prospect
   - Identify Workshop coordinator/lead from prospect and request the following information
   - Understand # of attendees
   - Gather emails and roles from attendees
   - [Optional] Goals of the attendees from the workshop, years of experience
2. Create a Galaxy Domain for the Prospect [Create a Galaxy Domain ](https://www.starburst.io/platform/starburst-galaxy/start/)
   - You can use youremail+yourgalaxyprospect@starburstdata.com (add + after your email to create additional domains using your same email)
   - For user creation, you can use youremail+yourgalaxyprospectUser1@starburstdata.com, youremail+yourgalaxyprospectUser2@starburstdata.com, etc 
3. Configure Cross Account Role for the Prospects Domain
   - WIP
4. Copy Data into Requisite location within AWS s3, reference this [doc](https://github.com/starburstdata/SA-Galaxy-Workshop/blob/main/Module_Zero-Pre-Work/AWS_S3_Setup.pdf) for more info 
5. Create an RDBMS to be used later if needed (Federation or Data Products or Data Discovery)
   - [RDBMS](https://github.com/starburstdata/SA-Galaxy-Workshop/blob/main/Module_One-Galaxy-Overview/Create_Database_Catalog.pdf)
      - Reference the "AWS Redshift" credentials within Keeper to configure connection details
      - Leverage your bastion host to connect 
6. Create a Role to be used by attendees with the following constraints
   - Does not have "Grant to creating role?" access on the Add new Role screen
   - Has the following Account level permissions
   - <img width="836" alt="image" src="https://github.com/starburstdata/SA-Galaxy-Workshop/assets/115039992/90531608-79d2-4954-8c2b-6c1ea0acc536">

   - Location Access to "s3://starburst-galaxy-workshop/org_a (e.g. walmart)/*"
   - Select Only Access to RDBMS Catalog
   - Full access to s3 catalog (read/write)
   

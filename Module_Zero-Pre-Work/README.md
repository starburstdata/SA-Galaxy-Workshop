# SA-Galaxy-Workshop

Repository to be Used by SAs to facilitate On-Site Galaxy Workshops

## Steps to Prepping for an Onsite Galaxy Workshop

****DANGER! You need to validate that Galaxy can issue queries from the UI and the client can access Galaxy IP/DNS from their work WIFI/VPN ****DANGER****

1. Get list of attendees from Prospect
   - Identify Workshop coordinator/lead from prospect and request the following information
   - Understand # of attendees [Modules designed for smaller total # of Attendees, 3-15]
   - Gather emails and roles from attendees
   - [Optional] Goals of the attendees from the workshop, years of experience
   - Once you have the attendee list, create up to 3 seperate groups [Group A, B, C]
        -These groups will be used for live execution of workshop tasks
        -3 Groups because we can only have up to 3 free clusters per domain in Galaxy
2. Create a Galaxy Domain for the Prospect [Create a Galaxy Domain ](https://www.starburst.io/platform/starburst-galaxy/start/)
   - You can use youremail+yourgalaxyprospect@starburstdata.com (add + after your email to create additional domains using your same email)
   - For user creation, you can use youremail+yourgalaxyprospectUser1@starburstdata.com, youremail+yourgalaxyprospectUser2@starburstdata.com, etc
        - Record each username and password. You will provide these to the attendees yourself. Use a generic lab password.
        - The role assigned to these users will be created in step 6
3. Configure Cross Account Role for the Prospects Domain (utilize the starburstdata-field account with the solution_architect role)
   - Reference documentation within Galaxy [here](https://docs.starburst.io/starburst-galaxy/cloud-settings/aws.html)
   - Reference documentation for AWS [here](https://docs.starburst.io/starburst-galaxy/security/external-aws.html#cross-account-iam-role)
4. Copy Data into Requisite location within AWS s3, reference this [doc](https://github.com/starburstdata/SA-Galaxy-Workshop/blob/main/Module_Zero-Pre-Work/AWS_S3_Setup.pdf) for more info
   - Download the PDF to view, or click "More Pages" at the very bottom to see entirety of PDF
5. Create an RDBMS to be used later if needed (Federation or Data Products or Data Discovery) **the instructions below reference Redshift but we will be using Postgres
   - [RDBMS](https://github.com/starburstdata/SA-Galaxy-Workshop/blob/main/Module_One-Galaxy-Overview/Create_Database_Catalog_Galaxy.pdf)
      - Reference the "Galaxy Onsite Workshop Postgres" credentials within Keeper to configure connection details (Reach out to an SA on the West 4 team if you need access)
      - Select Only Access to RDBMS Catalog
6. Create a Role to be used by attendees with the following constraints
   - Does not have "Grant to creating role?" access on the Add new Role screen
   - Has the following Account level permissions
      <img width="836" alt="image" src="https://github.com/starburstdata/SA-Galaxy-Workshop/assets/115039992/90531608-79d2-4954-8c2b-6c1ea0acc536">

   - Location Access to "s3://starburst-galaxy-workshop/org_a (e.g. walmart)/*"
  
      <img width="899" alt="image" src="https://github.com/starburstdata/SA-Galaxy-Workshop/assets/115039992/3d92dfbe-8476-439e-bf7f-46a44ab51d91">
   - Table Privileges (All Schemas / All Tables, **Select from table**)
7. Add users to cluster with the role created in Step #6 above
     - Note the invite link is currently only valid for 24hrs so please complete this step within that timeframe of the workshop starting.
8. Delete Sample Cluster that comes by default with the domain.
   

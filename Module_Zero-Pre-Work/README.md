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
3. Once you have access to the cluster create the following Catalogs
   - [s3](https://github.com/starburstdata/SA-Galaxy-Onsite-pre-work/blob/main/module_one/Create_S3_Catalog.pdf) 
      - Access Keys to s3 are located within Keeper (search for "Starburst Galaxy Workshops AWS Access Key")
      - s3 bucket is located within the starburstdata-field AWS account (188806360106)
        - Bucket: s3://starburst-galaxy-workshop/
        - Create a new directory within that path (e.g. "org_a")
        - Copy the "copy_from_here" path into newly created directory
      - Galaxy Configuration
        - Prohibit Creating and Writing to External Tables
        - Only Role that SA is using has write privileges
        - Connect to sample cluster in us-east-2
        - Run Schema Discovery (ensure that you have added location access to the s3 uri (e.g. s3://starburst-galaxy-workshop/org_a/*)
   - [RDBMS](https://github.com/starburstdata/SA-Galaxy-Onsite-pre-work/blob/main/module_one/Create_Database_Catalog.pdf)
4. Create a Role to be used by attendees with the following constraints
   - Does not have "Grant to creating role?" access on the Add new Role screen
   - Location Access to "s3://starburst-galaxy-workshop/org_a/*"
   - Select Only Access to s3 Catalog
   - Select Only Access to RDBMS Catalog
   - Use Cluster Access for Cluster "Sample"
   - Deny Access to Create/Alter Existing Roles

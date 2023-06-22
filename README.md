# SA-Galaxy-Onsite-pre-work

Repository to be Used by SAs to facilitate On-Site Galaxy Workshops

## Steps to Prepping for an Onsite Galaxy Workshop

1. Get list of attendees (users)
2. SA Creates account Domain [Create a Galaxy Domain ](https://www.starburst.io/platform/starburst-galaxy/start/)
3. Add users to Domain with the appropriate role
   - Does not have "Grant to creating role?" access on the Add new Role screen
   - Location Access to "s3://starburst-galaxy-workshop/<org_a>/*"
   - Select Only Access to s3 Catalog
   - Select Only Access to RDBMS Catalog
   - Use Cluster Access for Cluster "Sample"
   - Deny Access to Create/Alter Existing Roles
5. Once you have access to the cluster create the following Catalogs
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
   - [RDBMS](https://github.com/starburstdata/SA-Galaxy-Onsite-pre-work/blob/main/module_one/Create_RDBMS_Catalog.pdf)

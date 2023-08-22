<h1 align="center">Build and Access RDS Server using MySQL Workbench</h1>

## Objective:
* Create RDS MySQL instance
* Launch the database with specific requirements
* Update Security Groups for accessiblity
* Establish MySQL connectivity in My SQL workbench

# Create a RDS Database instance

<details>
<summary>Rundown Check</summary>
 
1. Launch Database with following settings.

2. Create Database

3. Copy Endpoint port

4. Navigate to VPC Secuirty Group in the Connectivity & Security Section

5. Edit Inbound Rules to allow Traffic from Anywhere

6. Open MySQL Workbench
</details>

### Tutorial (Step-By-Step):

1. Create a RDS Database instance.

2. Select a standard creae and MySQL

![RDS-project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/RDS/RDS-IMG1.png)

3. Use the Free Tier template. 

![RDS-project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/RDS/RDS-IMG2.png)

4. Select t3.micro.

![RDS-project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/RDS/RDS-IMG3.png)

5. Configure settings for the DB instance

![RDS-project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/RDS/RDS-IMG4.png)

![RDS-project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/RDS/RDS-IMG5.png)

![RDS-project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/RDS/RDS-IMG6.png)
# Security Use Cases

## UC1: Enterprise-Wide Visibility & Management

<img style="height:40%;width:50%" src="devsecops-sec-uc1.png" /> 

### Pre-Req
Best Practices "Policy Settings" published by Offering or Service Owner or Security competency, for various elements - configmaps, secrets, dockerfile, Helm Charts etc.

### IaC Elements
1. Develop, Test & publish code to implement best practice "Policy Settings" for target environments
2. Develop, Test & publish code to validate best practice "Policy Settings" are in place in target environments
3. Develop, Test & publish code to remediate incorrect "Policy Settings" in target environments
**NOTE**: Multiple code packages may need to be developed to address various platforms and environments including VMWare, OpenShift, IBM Cloud, AWS etc. 
 
### DevSecOps Elements
1. All above IaC development will follow DevSecOps practices and pipelines to develop code, test (Functional, performance, static code, integration) and publish the code in trusted repository.
2. Optionally, deploy or remediate "policy settings" on target environments, using DevSecOps Tools.  Alternately, use existing automations in the environment (Ansible, Chef, etc) to deploy the policies as well as for checking and remediation.
3. Incorporate best practice "Policy Settings" as part of DevSecOps pipeline to perform these checks during code build and remediate the same.

### Sample UseCase Flow: Policy Setting Validation & Remediation
1. Automation tool(Ansible or any) inspects target environment against policies and identifies non-compliance
2. If Automated remediation already available thru’ existing tools, non-compliance is corrected
3. If no remediation exist, request for new remediation


## UC2: Vulnerability Management

### Pre-Req
Best Practices defined for:

- Vulnerability Checks
	- Image check in artifact repository
	- OSSC Validation
	- Container image validation
	- Software Composition Analysis(SCA)
	- SAST, DAST
	- Other checks
- Image Drift Checks

### IaC Elements
1. Develop, Test & publish code to perform Vulnerability checks & Image Drift checks on target platforms
2. Develop, Test & publish code to remediate Vulnerability Checks & Image Drift checks on target platforms
**NOTE**: Multiple code packages may need to be developed to address various platforms and environments including VMWare, OpenShift, IBM Cloud, AWS etc. 
 
### DevSecOps Elements
1. All above IaC development will follow DevSecOps practices and pipelines to develop code, test (Functional, performance, static code, integration) and publish the code in trusted repository.
2. Optionally, deploy or remediate "policy settings" on target environments, using DevSecOps Tools.  Alternately, use existing automations in the environment (Ansible, Chef, etc) to deploy the policies as well as for checking and remediation.
3. Incorporate Vulnerability checks as part of Build Checks in DevSecOps pipeline for IaC, and publish code only when checks are successful 
4. Incorporate Image Drift checks as part of deployment pre-checks in DevSecOps pipeline for IaC, and deploy code only after remediating drift in target environment.


## UC3: Health Check Management
These are Day 2 checks to validate if Corporate Security policies are implemented and in-use in production environments.
This is applicable in traditional, cloud and cloud native environments.
**NOTE/QUESTION**: Shouldnt these Corporate policies be part of the Vulnerability check & Image Drift Check ?

### Pre-Req
ITSS, CIS or equivalent defined for Newco

### IaC Elements
1. Develop, Test & publish code to perform Health check compliance & Image Drift checks on target platforms
2. Develop, Test & publish code to remediate non-compliance on target platforms

**NOTE**: Multiple code packages may need to be developed to address various platforms and environments including VMWare, OpenShift, IBM Cloud, AWS etc. 

### DevSecOps Elements
1. All above IaC development will follow DevSecOps practices and pipelines to develop code, test (Functional, performance, static code, integration) and publish the code in trusted repository
2. Incorporate health-checks as part of Build Checks in DevSecOps pipeline for IaC, and publish code only when checks are successful 


## UC4: Inventory Management (of Repositories)
This is an inventory of all Github/GitLab repositories, and the goal is to ensure these repositories contain images which are authorized and follow various guidelines, including ensuring image contains all dependencies.

### Pre-Req
- Define information that need to be included as part of image (e.g. Owner, Repository instance, creation date, etc)
- Define dependencies, if any, for images

### IaC Elements
1. Develop, Test & publish code to check and validate images in trusted repositories are compliant, including dependency checks 

**NOTE**: Multiple code packages may need to be developed to address various platforms and environments including VMWare, OpenShift, IBM Cloud, AWS etc. 

### DevSecOps Elements
1. Above IaC development will follow DevSecOps practices and pipelines to develop code, test (Functional, performance, static code, integration) and publish the code in trusted repository
2. Incorporate checks within DevSecOps pipeline to ensure image contains all required information and contains all dependencies as defined above




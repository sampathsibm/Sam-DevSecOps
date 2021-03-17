# Security Use Cases

## Enterprise-Wide Visibility & Management

<img style="height:40%;width:50%" src="devsecops-sec-uc1.png" /> 

### IaC Elements:

1. Define/Update “Policy Settings” for various elements - configmaps, secrets, dockerfile, Helm Charts etc..
2. Define “Remediation automations” to address non-compliance
 
### DevSecOps Elements:

1. Develop, Test & publish code to implement "Policy Settings", using pre-defined policies, for target environments
2. Develop, Test & publish code to validate "Policy Settings" against pre-defined policies
3. Develop, Test & publish code to remediate incorrect "Policy Settings", 
4. Optionally, deploy or remediate "policy settings" on target environments, using DevSecOps Tools OR use existing automations in the environment (Ansible, Chef, etc(
5. All above will follow DevSecOps practices and pipelines to publish the code, and deploy the same if needed.

### Sample UseCase-1: Policy Setting Validation & Remediation
1. "Policy Settings" best practices published by Offering or Service Owner
2. Automation tool(Ansible or any) inspects target environment against policies and identifies non-compliance
3. If Automated remediation already available thru’ existing tools, non-compliance is corrected
4. If no remediation exist, request for new remediation

### Sample UseCase-2: Policy Setting Remediation Development

1. Remediation developed for missing "Policy Setting" remediation, following DevSecOps practices
2. Remediation Code published in trusted repository
3. Updates deployed to target systems OR automation tool uses newly published code to initiate remediation



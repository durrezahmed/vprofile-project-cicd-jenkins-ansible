# DevOps Project - Continuous Delivery and Configuration Management of Vprofile Project using Jenkins, Ansible, Nexus, SonarQube and Slack

This is a DevOps project for _Continuous Delivery_ and _Configuration Management_ of vprofile project using Jenkins, Ansible, Nexus, SonarQube and Slack. This project is a continuation of [_vprofile-project-ci-jenkins_](https://github.com/durrezahmed/vprofile-project-ci-jenkins) project.

[Link](https://github.com/durrezahmed/vprofile-project-devops) for vprofile app repository.

## Scenario - Current Situation:

- Agile Software Development

- Continuous Code Commit

- Package/Software/Artifact Deployment on Server

- Software Testing/Integration Testing after Deployment

- Test Report gets Evaluated and Approval for Production Issued

- Deploy → Test → Deploy → Test (Dev, QA, UAT)

- Dependent on Ops Team

- Deploy → Test → Deploy → Test (Dev, QA, UAT, Prod)

## Problem - Issues with Current Situation:

- In an Agile SDLC, there will be Frequent Code Changes

- Manual Code Deployment is Time Consuming

- Involves Task Assignment/Ticketing/Approvals

- Different Owners for Different Environment

## Solution - Fix:

- Build, Test, Deploy and Test for Every Commit

- Automated Deployment Process

- Notification at Every Step in Pipeline

- Integrate Automation Tool

- Remove/Minimize Human Intervention

- Fix Code if Bugs or Error found Instantly rather than Waiting

## Tools used in the Project:

- [**Amazon EC2**](https://aws.amazon.com/ec2/) - Compute Resource

- [**Jenkins**](https://www.jenkins.io/) - Continuous Integration and Continuous Delivery Server

- [**Ansible**](https://www.ansible.com/) - Configuration Management

- [**Git and GitHub**](https://github.com/) - Version Control System

- [**Maven**](https://maven.apache.org/) - Build Tool

- [**Checkstyle**](https://checkstyle.org/) - Code Analysis Tool

- [**Nexus Sonatype Repository**](https://www.sonatype.com/products/nexus-repository) - Artifact / Software Repository

- [**SonarQube**](https://www.sonarsource.com/products/sonarqube/) - Code Analysis Server

- [**Tomcat**](https://tomcat.apache.org/) - Application Server

- [**Slack**](https://slack.com/) - Notifications

## Usage (Flow of Execution):

1. Update `GitHub Webhook` with new Jenkins IP and Resize Jenkins volume

2. Launch `EC2 Instance` for `app01-staging`

3. Jenkins Prerequisites

   - Install Ansible

   - Install Ansible Plugin

   - Save app01 SSH Login Creds

   - Timestamp Variable

4. Copy Ansible code from this Repository to your own Repository

5. Create DNS record in Route 53 for `app01-staging`

6. Create Inventory file in Ansible Code

7. Update Security Group Rules

   - Allow Port `22` in `app-sg` from `jenkins-sg`

   - Allow Port `8081` in `nexus-sg` from `app-sg`

8. Write `Jenkinsfile` to run Ansible Playbook from Jenkins

9. Create Pipeline in `Jenkins` and Test it

10. Update Ansible Code in the `Production` Branch

11. Launch `app01-production` , DNS record in Route 53, Create Inventory file

12. Create Pipeline in `Jenkins` and Test it

13. Test of Promoting changes to `Production` branch by Merge

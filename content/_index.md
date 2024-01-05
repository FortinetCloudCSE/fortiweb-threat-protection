---
title: "Fortinet Fortiweb Threat Protection"
menuTitle: "Getting Started"
weight: 1
archetype: home
---

### Welcome!

In this workshop you will learn how to configure profiles with different protection modules enabled on Fortinet's FortiWeb Web application and API protection firewall. 

### About TEC Workshops

TEC Workshops provide the learner with the opportunity to put into practice newly developed skills in an easy to launch environment that can be used for customer engagements. At a minimum a TEC Workshop will include the following:

* A use case description
* An integrated lab and demo environment

  * Informational call-outs for key points to discuss or highlight to a customer
  * Questions that could be asked while giving the TEC Workshop as a demo
  * Points of value that relate the business value to the technical feature
* A reference architecture(s)

Optional components may be included for certain use cases

The TEC Workshop will not be a completely, self-contained learning experience for a single product. A TEC Workshop will cover features and often multiple products where they relate to the use case of interest.  

Deployments will be automated for those tasks that are not salient to the learning or demonstration activity in the use case. For example, for a TEC Workshop focused on Indicators of Compromise, the system may deploy a FortiGate and FortiAnalyzer with configurations for these systems. However, the leaner will have to configure the Event Handlers for IOC setup.  

## FortiWeb Threat Protection: 

**Introduction:**

FortiWeb, Fortinet's web application firewall (WAF) solution, is designed to address the increasing threats and vulnerabilities associated with web applications. Here are several reasons why organizations might choose to implement FortiWeb:

* Web Application Security with Sigantures and Machine learning.
* Data Protection
* Compliance Requirements
* Threat Intelligence Integration
* Application Layer Attacks Prevention
* Authentication and Access Control
* Web Traffic Visibility and Monitoring 
* SSL/TLS inspection and many others

**Fortiweb features include:**

* OWASP Top 10 protection signature database
* Machine learning based Anomaly and Bot detection
* ZTNA 
* API Schema protection
* Machine learning based API learning
* API gateway

The purpose of this TEC Workshop is to familiarize the learner with FortiWeb protection profiles, setting up policies to provide robust defense to Web apps and API. 

## TEC Workshop Objectives

Lab-1: 

* Deploy the FortiWeb and all the required components like Kali Linux, Web application called Juiceshop. 
* Configure Server pools and VIP on Fortiweb
* Configure Protection profiles to include basic signature database
* Configure Bot mitigation with Biometrcis based detection.


{{< notice warning >}}
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Fortinet and Azure services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments without full understanding of how they operate.
{{< /notice >}}
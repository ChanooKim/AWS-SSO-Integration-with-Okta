# AWS-SSO-Integration-with-Okta

## Executive Summary 

AWS Single Sign-On is a cloud-based signal sign-on (SSO) service that makes it easy to centrally manage SSO access to all of your AWS accounts and cloud applications. Specifically, it helps you manage SSO access and user permissions across all your AWS accounts in AWS Organizations. AWS SSO supports automatic provisioning of user and group information from Okta into AWS SSO using the System for Cross-domain Identity Management (SCIM) v2.0 protocol. To configure this connection in Okta, you use your SCIM endpoint for AWS SSO and a bearer token that is created automatically by AWS SSO. 

## Pre-requisites 

- An Okta account with admin privileges. Install AWS Single Sign-On application on Okta
- SAML connection from Okta account to AWS SSO
  + AWS Single Sign-On 
    + Settings → Change Identity Source → External Identity Provider
    + Copy AWS SSO Sign-in URL, AWS SSO ACS URL, and AWS SSO Issuer URL. 
    + IdP SAML metadata: get this through the Okta Admin dashboard  
- An AWS SSO-enabled account 

## Design

Allowing for administrator access to AWS account through AWS Single sign-on integration with Okta. 

## Implementation

1. Enable provisioning in AWS SSO 
    - Use AWS SSO console to enable automatic provisioning
2. Configure provisioning in Okta 
    - In Okta admin portal, enable integration between AWS SSO and AWS Single Sign-On app. 
3. Assign access for users and groups in Okta 
    - Okta users who belong to groups that you assign are synchronized automatically to AWS SSO. To minimize administrative overhead, assign and push groups instead of individual users.
4. Assign user access to AWS account 
    - Assign SSO access to users and groups in your connected directory and use permission sets to determine their level of access. 

## Troubleshooting Guide

- Make sure to have okta admin privileges otherwise you cannot complete SSO 
- For SAML connection you must generate Idp SAML metadata on the Okta admin page

#### API Specification for OYOH

### About
OYOH API is an OAuth 2.0 API that was built as a joint initiative at the CBIT (Center for Business and Information Technologies) at the University of Louisiana at Lafayette, in close cooperation with the Department of Health and Hospitals, and the Venyu cloud hosting service.

### General
Sign up at:

https://cajuncodefest.dhh.la.gov

Create a new application and use the application and security token in your OAuth 2.0 projects

### API v1
## Patients
You log into a patient with the first_name, last_name, and date_of_birth

    /api/v1/me.json

    {"patient":{"patient_id":"ff....","first_name":"....","last_name":"....","address":"...","city":"...","state":"LA","zip":"...","date_of_birth":"1999-09-19","gender":"F"}}

### SDKs
## Ruby OmniAuth
    gem install omniauth-oyoh
    https://github.com/fishman/omniauth-oyoh
	
If you're interesting in using ruby. Please try the sample application at:
    https://github.com/fishman/oyoh-devise-client

## Python

## .NET

## Java

## Node

### Similar
Eligible API [https://www.eligibleapi.com]

### Credits
CBIT
DHH
Venyu


#### API Specification for OYOH

### About
OYOH API is an OAuth 2.0 API that was built as a joint initiative at the CBIT (Center for Business and Information Technologies) at the University of Louisiana at Lafayette, in close cooperation with the Department of Health and Hospitals, and the Venyu cloud hosting service.

### General
Sign up at:

    https://cajuncodefest.dhh.la.gov

Create a new application and use the application and security token in your OAuth 2.0 projects

### OAuth endpoints
    https://cajuncodefest.dhh.la.gov/oauth/authenticate
    https://cajuncodefest.dhh.la.gov/oauth/access_token


### Logging in
Logging in happens by using the Patients first name, last name, and date of birth

### API v1
## Patients
You log into a patient with the first_name, last_name, and date_of_birth

    /api/v1/me.json

    {"patient":{"patient_id":"ff....","first_name":"....","last_name":"....","address":"...","city":"...","state":"LA","zip":"...","date_of_birth":"1999-09-19","gender":"F"}}

## Prescriptions
    /api/v1/patient/prescriptions/

## Claims
    /api/v1/claims

    Returns an array of claims associated to the logged in patient

    [{"claim":{"claim_id":"...","claim_type":"03","proc_code":"HR403","date_of_service":".."}},{"claim":{"claim_id":"...","claim_type":"04","proc_code":"CC001","date_of_service":"..."}}
    

    /api/v1/claims/:id

    Returns the detail view of a specific claim

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

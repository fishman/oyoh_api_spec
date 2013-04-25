#### API Specification for OYOH

### About
OYOH API is an OAuth 2.0 API that was built as a joint initiative at the CBIT (Center for Business and Information Technologies) at the University of Louisiana at Lafayette, in close cooperation with the Department of Health and Hospitals, and the Venyu cloud hosting service.

### General
Sign up at:

    https://cajuncodefest.dhh.la.gov

Create a new application and use the application and security token in your OAuth 2.0 projects

### OAuth endpoints
    https://cajuncodefest.dhh.la.gov/oauth/authorize
    https://cajuncodefest.dhh.la.gov/oauth/token


For the token exchange to work you must use post and add the following parameters:


    request_token_params=
    {
      'response_type': 'code'
    }
    
    access_token_params=
    {
      'grant_type': 'authorization_code'
    }


### Logging in
Logging in happens by using the Patients first name, last name, and date of birth

### API v1
## Patients
You log into a patient with the first_name, last_name, and date_of_birth, for sample purposes please use:

    First Name: Tammy
    Last Name: Crotean
    Birthdate: 1970-04-16

    /api/v1/me.json

    {"patient":
      {
        "patient_id":"ff....",
        "first_name":"....",
        "last_name":"....",
        "address":"...",
        "city":"...",
        "state":"LA",
        "zip":"...",
        "date_of_birth":"1999-09-19",
        "gender":"F"
      }
    }

## Prescriptions
    /api/v1/patient/prescriptions
    
    [
      {"prescription":{"rx":"2344","name":"INSULIN SYRINGE","date_of_service":"2008-11-16"}},
      {"prescription":{"rx":"2344","name":"INSULIN SYRINGE","date_of_service":"2008-11-16"}}
    ]
    
    /api/v1/patient/prescriptions/:rx
    
    [
      {"prescription":{"ndc":"08290328440","name":"INSULIN SYRINGE","quantity":"100.0","strength":"31GX5/16\"","dosage":"DISP SYRIN","date_of_service":"2008-11-16","provider":{"npi":"1235150517","type":"26","type_description":"Pharmacy (out-of-state for crossovers only)","name":"WINN DIXIE PHARMACY #1463","address":"1803 HWY 3125","address_2":"GRAMERCY","county":"ST. JAMES","state":"LA","zip":"700525602"}}},
      {"prescription":{"ndc":"08290328440","name":"INSULIN SYRINGE","quantity":"100.0","strength":"31GX5/16\"","dosage":"DISP SYRIN","date_of_service":"2008-11-16","provider":{"npi":"1235150517","type":"26","type_description":"Pharmacy (out-of-state for crossovers only)","name":"WINN DIXIE PHARMACY #1463","address":"1803 HWY 3125","address_2":"GRAMERCY","county":"ST. JAMES","state":"LA","zip":"700525602"}}},
      {"prescription":{"ndc":"08290328440","name":"INSULIN SYRINGE","quantity":"100.0","strength":"31GX5/16\"","dosage":"DISP SYRIN","date_of_service":"2008-06-07","provider":{"npi":"","type":"26","type_description":"Pharmacy (out-of-state for crossovers only)","name":"WINN DIXIE PHARMACY #1463","address":"1803 LA HWY 3125","address_2":"GRAMERCY","county":"ST. JAMES","state":"LA","zip":"700520000"}}}
    ]

## Claims
    /api/v1/claims

    Returns an array of claims associated to the logged in patient

    [
      {"claim":{"claim_id":"...","claim_type":"03","proc_code":"HR403","date_of_service":".."}},
      {"claim":{"claim_id":"...","claim_type":"04","proc_code":"CC001","date_of_service":"..."}}
    ]

    /api/v1/claims/:claimid
    
    {"claim":{
      "claim_type":"03",
      "claim_type_desc":"Outpatient",
      "proc_code":"HR320",
      "proc_code_desc":"...",
      "dx1":"...",
      "dx1_desc":"...",
      "dx2":"...",
      "dx2_desc":"...",
      "charge_amt":"120",
      "paid_amt":"50",
      "provider":{
        "npi":"234",
        "type":"87",
        "type_description":"Rural Health Clinic (Independent) (in-state only)",
        "name":"21 Test",
        "address":"21 S COLLEGE ST",
        "address_2":"",
        "county":"ST. PIZZA",
        "state":"LA",
        "zip":"721523659"
       }
      }
    }

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

### Disclaimer
All data has been deidentified

### Credits
CBIT
DHH
Venyu
Singly
Doorkeeper
Whoeverdesignedthatfrontpage

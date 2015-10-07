#V2 Resources and Endpoints

**[See REST Guide For Help](/restful-guide.md)**

Each header belongs to the resource you are representing and all the endpoints are listed underneath it for that resource.

##Oauth


##Me/My

**GET /v2/me**  
**GET /v2/my**  

Response: 200  
```
{  
  “first_name”: string,  
  “last_name”: string,  
  “address_1”: string,  
  “address_2”: string,  
  “city”: string,  
  “state_province”: string,  
  “postal_code”: string,  
  "benefits_summary": {  
    "is_individual": boolean,  
    "is_group_member" : boolean,  
    "is_primerica": boolean,  
    "has_legal_emergency_access": boolean,  
    "has_small_business": boolean,  
    "has_idshield": boolean,  
    "has_legacy_identity_theft": boolean,  
    "has_cdlp": boolean,  
    "has_legal": boolean  
  }
}
```

**PATCH /v2/me**  
**PATCH /v2/my**  

Request:
```
{    
  “first_name”: string,  
  “last_name”: string,  
  “address_1”: string,  
  “address_2”: string,  
  “city”: string,  
  “state_province”: string,  
  “postal_code”: string  
}
```

Response 202:  
```
Same as the GET /v2/me endpoint. Returns the full new JSON resource
```

###Benefits Summary

**GET /v2/me/benefits_summary**  
**GET /v2/my/benefits_summary**  

Response 200:
```
{  
  "is_individual": boolean,  
  "is_group_member" : boolean,  
  "is_primerica": boolean,  
  "has_legal_emergency_access": boolean,  
  "has_small_business": boolean,  
  "has_idshield": boolean,  
  "has_legacy_identity_theft": boolean,  
  "has_cdlp": boolean,  
  "has_legal": boolean  
}
```

###Plans

**GET /v2/me/plans**  
**GET /v2/my/plans**  

Response 200:
```
[  
  {  
    “id”: numeric  
    "display_name": string,  
    "account_number": numeric,    
    "member_services_number": string,  
    "member_services_email": string,  
    "emergency_access": boolean,  
    "emergency_number": string,
    "provider": {  
      “phone_number”: string,  
      “name”: string  
    },
  }  
]
```

###Billing

**GET /v2/me/billing**  
**GET /v2/my/billing**  

Response: 200  
```
{  
  “next_draft_date”: date,  
  “draft_account”: string  
}  
```

##Users



##Plans

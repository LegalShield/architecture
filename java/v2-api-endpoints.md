#V2 Resources and Endpoints

###These endpoints are not the source of truth for this API. Think of this as a whiteboard where you can design the endpoints in a RESTful way and get it reviewed by other people on the team before you start coding the wrong thing.  
  
**[See REST Guide For Help](/restful-guide.md)**
  
Each header belongs to the resource you are representing and all the endpoints are listed underneath it for that resource.
  
##Oauth

##Me/My

**GET /v2/me**  
**GET /v2/my**  

Response: 200  
```
{  
  "first_name": string,  
  "last_name": string,  
  "address_1": string,  
  "address_2": string,  
  "city": string,  
  "state_province": string,  
  "postal_code": string,  
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
  "first_name": string,  
  "last_name": string,  
  "address_1": string,  
  "address_2": string,  
  "city": string,  
  "state_province": string,  
  "postal_code": string  
}
```

Response 202:  
```
Same as the GET /v2/me endpoint. Returns the full new JSON resource
```

###Plans

These need to be redesigned for v2!!!

**GET /v2/me/plans**  
**GET /v2/my/plans**  

Response 200:
```
[  
  {  
    "id": numeric  
    "display_name": string,  
    "account_number": numeric,    
    "member_services_phone_number": string,  
    "member_services_email": string,  
    "emergency_access": boolean,  
    "emergency_phone_number": string,
    "provider_phone_number": string,
    "provider_name": string
  }  
]
```

###Billing

**GET /v2/me/billing**  
**GET /v2/my/billing**  

Response: 200  
```
{  
  "next_draft_date": date,  
  "draft_account": string  
}  
```

##Users

GET `/v2/users`

Query:

```javascript
phone_number=3172429840
last_4_SSN=5555
date_of_birth=1982-12-11T00:00:00.000+00:00
```

Status: 200

Headers:

```javascript
{ "X-Resource-Count": 3465 }
```

Body:

```javascript
[
  {
    id: 1234,
    last_4_ssn: 2222,
    name: "Jonathon Storer",
    date_of_birth: "1982-12-11T00:00:00.000+00:00",
    memberships: [
      {
        id: 1234,
        type: "LegalShield Personal",
        status: "PreCancel",
        email: "jon@shakelaw.com",
        phone_number: "13172429840",
        updated_at: "2015-12-11T00:00:00.000+00:00",
        created_at: "2014-12-11T00:00:00.000+00:00"
        exceptions: [
          {
            code: 28,
            message: "you done effed up"
          },
          {
            code: 45,
            message: "we done effed up"
          }
        ],
        member_resolution: {
          id: 1234,
          status: "Active"
        },
        address: {
          street_1: "123 Main St",
          street_2: "Apt 3",
          city: "Ada",
          state_province: "OK",
          zip_code: "11205",
          country: "US"
        },
        entitlements: {
          can_edit_billing: true,
          can_direct_transfer: true,
          can_bypass_menu: true
        },
        billing: {
          type: "Credit Card"
          last4: 1234
          past_due_amount: "19.95",
          past_due_date: "2015-10-21T00:00:00.000+00:00"
        },
        provider: {
          id: 9765,
          name: "Fulfilment Partner Name",
          phone_number: "13335554444"
        }
      }
    ]
  }
]

```

Enums

```
memberships.type => [ "LegalShield Personal", "LegalShield Small Business", "LegalShield CDLP", "IDShield" ]
memberships.status => [ "Active", "PreCancel, "Pending Cancel Exceptoin", "Pending Cancel", "Canceled" ] (???)
memberships.member_resolution.status => [ "Active", ??? ]
memberships.address.country => [ "US", "CA" ]
memberships.entitlements.can_bypass_menu => (true when "small business", exception code 23, account status is "Canceled", account status is "Canceled")
memberships.billing.type => [ "Credit Card", "Bank Draft", "Premium Billing" ]
```

##Plans

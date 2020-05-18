# Store APIs Key in FrontEnd SDK issues

## Context

Provide a service and SDK\(include customer's key\) for frontend \(web/mobile\)

## Issue

Attacker can get the key and spam/abuse services -&gt; customer can be highly charged 

## Wrap Solution

### Flow: Customer's frontend -&gt; provider's backend

* Rate limit by IP
* Rate limit by user data

### Flow: Customer's frontend -&gt; Customer's backend -&gt; Customer's frontend -&gt; provider's backend

* Encrypt data by customer's secret key in customer's backend
* Customer's backend limits request by user's auth 


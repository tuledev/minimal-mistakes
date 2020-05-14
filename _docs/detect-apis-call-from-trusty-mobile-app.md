# APIs abuse issues

## I. Context

In this post, I will just mention to abusing issues 

We're providing services which fee base on request numbers. The services run on web, iOS,  and Android platforms.

## II. Issues

What attacker can:

* Abuse sms api to many phone -&gt; customer can lost money
* Abuse sms api to phone -&gt; annoy users
* Use the service key for attacker's service -&gt; customer can lost money

Why 

* Attackers want to attack customers
* Attackers want to attack us.

The issues come from platforms:

* Easy to catching the request and keys on browsers -&gt; attackers can capture and simulate requests 
* Can't restrict by domain or while list IP on mobiles -&gt; attackers can capture and simulate requests 
* Leak secret\_key/APIs key on mobile -&gt; attackers can use it for other services. For example: using for web services
* Don't know requests come from trusty apps or not

## III. Wrap Solutions

### Separate Android/iOS and web APIs

Build 3 APIs flows so attackers can't use hacked from a platform to another platform, especially from mobile to web 

### System

* Limit APIs request rate by IP
* Prevent by country IP
* Alert  

### Restrict usage on Web, Android and iOS app

* Web: limit by domain
* Android: add package name and SHA-1signing-certificate fingerprint/app ID to restrict usage to  Android app.
* iOS: accept requests from the iOS app with the bundle identifier that supply

### Using JWT as short-live token

Using JWT with cryptography signature created from app for request

* The signature cryptography algorithm is created from .so in Android, and .framework in iOS to prevent reverse engineering
* The signature can be gen in the customer's backend

### 



{% embed url="https://www.twilio.com/docs/verify/developer-best-practices" %}

{% embed url="https://www.twilio.com/docs/verify/api/programmable-rate-limits" %}

{% embed url="https://www.twilio.com/docs/usage/anti-fraud-developer-guide" %}



## Conclusion

In mobile app can do

#### Layer 1

* Using JWT from file config
* Restrict by App ID 

#### Layer 2

* Prebuild JWT in mobile to c++ lib


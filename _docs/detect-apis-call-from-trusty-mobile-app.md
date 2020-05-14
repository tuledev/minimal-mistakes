# Detect APIs call from trusty mobile app

## I. Context

We're providing services which fee base on request numbers. The services run on web, iOS,  and Android platforms. 

We need to sercue the system to proect customer. Preventing attackers use the hacked infomation to overuse our services.

## II. Issues

What attacker can:

* Abuse sms api to many phone -&gt; customer can lost money
* Abuse sms api to phone -&gt; annoy users
* Use the service key for attacker's service -&gt; customer can lost money

The issues come from mobile platforms:

* Can't restrict by domain or while list IP -&gt; attackers can capture and simulate requests 
* Leak secret\_key/APIs key on mobile -&gt; attackers can use it for other services. For example: using for web services
* Don't know requests come from trusty apps or not

## III. Wrap Solutions

### Separate Android/iOS and web APIs

Build 3 APIs flows so attackers can't use hacked from a platform to another platform, especially from mobile to web 

### Restrict usage on Android and iOS app

* Android: add package name and SHA-1 signing-certificate fingerprint to restrict usage to  Android app.
* iOS: accept requests from the iOS app with the bundle identifier that supply

### Using JWT as short-live token

Using JWT with cryptography signature created from app for request

* The signature cryptography algorithm is created from .so in Android, and .framework in iOS to prevent reverse engineering
* The signature can be gen in the customer's backend



### System

* Limit APIs request rate by IP
* 
{% embed url="https://www.twilio.com/docs/verify/developer-best-practices" %}

{% embed url="https://www.twilio.com/docs/verify/api/programmable-rate-limits" %}






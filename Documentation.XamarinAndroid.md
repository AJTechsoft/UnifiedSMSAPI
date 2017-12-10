# Unified SMS Sending for Xamarin.Android
This is a common interface for sms services that provide the possibility for programmatically send SMS.

## Support SMS Services
**Nexmo**| <img src="https://appinstitute.com/apptools/wp-content/uploads/2016/07/eqwAwiC-3.png" width="48" height="48" />|
**Twilio** | <img src="https://static.blockspring.com/tag-icons/twilio.png" width="48" height="48" />  
------------ | ------------- |------------ | ------------- 
**Twizo**| <img src="https://www.twizo.com/wp-content/themes/twizo/_/images/twizo-logo-0474ce6f.png" width="48" height="48" />|**Msg91**| <img src="https://www.thetmstore.com/wp-content/uploads/msg_icon_450px_1_1.png" width="48" height="48" /> 
## How to Download
You can download the library using **Nuget**
#### Gradle
```csharp
Install-Package UnifiedSmsApi -Version 1.0.0
```
## How to Use
### SMS API Initialization
```java
SMS sms = new SMS(this); // Activity
```
### Nexmo SMS Service
```csharp
Nexmo nexmo = new Nexmo("[Nexmo API Key]", "[Nexmo API Secret]");
Response response = sms.SendSMS(nexmo, "[Sender Name]", "[To number with country code]", "[Text Message]");
string str = response.Body().String();
```
### Twilio SMS Service
```csharp
Twilio twilio = new Twilio("[Twilio Account SID]", "[Twilio Auth Token]");
Response response = sms.SendSMS(twilio, "[Sender Name]", "[To number with country code]", "[Text Message]");
string str = response.Body().String();
```
### Twizo SMS Service
```csharp
Twizo twizo = new Twizo("[Twizo Key]");
Response response = sms.SendSMS(twizo, "[Sender Name]", "[To number with country code]", "[Text Message]");
string str = response.Body().String();
```
### Msg91 SMS Service
```csharp
Msg91 msg91 = new Msg91("[Msg91-Auth-Key]");
Response response = sms.SendSMS(msg91, "[Sender Name]", "[To number]", "[Text Message]", "[Country Code]");
string str = response.Body().String();
```

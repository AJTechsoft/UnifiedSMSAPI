# Unified SMS Sending for Android
This is a common interface for sms services that provide the possibility for programmatically send SMS.

## Support SMS Services
**Nexmo**| <img src="https://appinstitute.com/apptools/wp-content/uploads/2016/07/eqwAwiC-3.png" width="48" height="48" />|
**Twilio** | <img src="https://static.blockspring.com/tag-icons/twilio.png" width="48" height="48" />  
------------ | ------------- |------------ | ------------- 
**Twizo**| <img src="https://www.twizo.com/wp-content/themes/twizo/_/images/twizo-logo-0474ce6f.png" width="48" height="48" />|**Msg91**| <img src="https://www.thetmstore.com/wp-content/uploads/msg_icon_450px_1_1.png" width="48" height="48" /> 
## How to Download
You can download the library using **Gradle** or **Maven**
#### Gradle
```groovy
compile 'com.ajts.library.unifiedsms:unifiedsmslibrary:1.0.0'
```
#### Maven
```groovy
<dependency>
  <groupId>com.ajts.library.unifiedsms</groupId>
  <artifactId>unifiedsmslibrary</artifactId>
  <version>1.0.0</version>
  <type>pom</type>
</dependency>
```
## How to Use
### SMS API Initialization
```java
SMS sms = new SMS();
```
### Nexmo SMS Service
```java
Nexmo nexmo = new Nexmo("[Nexmo API Key]", "[Nexmo API Secret]");
sms.sendSMS(nexmo, "[Sender Name]", "[To number with country code]", "[Text Message]", new SMSCallback() {
	@Override
	public void onResponse(Call call, Response response) {
		Log.v("nexmo", response.toString());
	}

	@Override
	public void onFailure(Call call, Exception e) {

	}
});
```
### Twilio SMS Service
```java
Twilio twilio = new Twilio("[Twilio Account SID]", "[Twilio Auth Token]");
sms.sendSMS(twilio, "[Sender Name]", "[To number with country code]", "[Text Message]", new SMSCallback() {
	@Override
	public void onResponse(Call call, Response response) {
		Log.v("twilio", response.toString());
	}

	@Override
	public void onFailure(Call call, Exception e) {

	}
});
```
### Twizo SMS Service
```java
Twizo twizo = new Twizo("[Twizo Key]");
sms.sendSMS(twizo, "[Sender Name]", "[To number with country code]", "[Text Message]", new SMSCallback() {
	@Override
	public void onResponse(Call call, Response response) {
		Log.v("twizo", response.toString());
	}

	@Override
	public void onFailure(Call call, Exception e) {

	}
});
```
### Msg91 SMS Service
```java
Msg91 msg91 = new Msg91("[Msg91-Auth-Key]");
sms.sendSMS(msg91, "[Sender Name]", "[To number]", "[Text Message]", "[Country Code]", new SMSCallback() {
	@Override
	public void onResponse(Call call, Response response) {
		Log.v("msg91", response.toString());
	}

	@Override
	public void onFailure(Call call, Exception e) {
		Log.v("msg91", e.toString());
	}
});
```

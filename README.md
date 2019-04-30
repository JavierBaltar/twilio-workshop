# twilio-workshop
<p align="center">
  <a href="#Getting-Started">Getting Started</a> •
  <a href="#Code">Code</a> •
  <a href="#related">Related</a> •
  <a href="#Authors">Authors</a>
</p>

## Getting Started
To run an Ansible Playbook with AWX, you need to configure the following items


- Twilio account details
![](twilio-account-details.png)

- Twilio verified called IDs
![](twilio-verified-caller-ids.png)

- Geo Restrictions
![](twilio-voice-geo-permissions.png)


- Announcement The <Say> verb converts text to speech that is read back to the caller.
```xml
<?xml version="1.0" encoding="UTF-8"?>
<Response>
    <Say voice="alice" language="es-ES">Esta es una llamada de prueba!</Say>
</Response>
```

## Code

```python
from twilio.rest import Client

#Set From and To numbers variables
From_Number = "+16692015XXX"
To_Number = "+34XXXXXXXXX"

#Set announcement xml resource
Src_Path = "http://demo.twilio.com/docs/voice.xml"

#Set Account SID, AUTH TOKEN parameters
account_sid = 'ACXXXXXXXXXXXXXX'
auth_token = 'your_auth_token'
client = Client("account_sid","auth_token")

#Call triggering
call = client.calls.create(to=To_Number, from_=From_Number, url = Src_Path, method = 'GET')
print('Call triggered successfully')

#Print call sid and status
print(call.sid, call.status)
```

## Related
* [Twilio Programmable Voice Docs](https://www.twilio.com/docs/voice) - Twilio API documentation
 
## Authors
* **Javier Baltar** - *Initial work* - [GitHub](https://github.com/JavierBaltar)


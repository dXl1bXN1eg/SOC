# SOC - 101


### Elastic Download [Tıkla](https://www.elastic.co/guide/en/kibana/current/deb.html)


### İlk Adım
`` Elimizde envanter olması gerekiyor ``

### İlk Tespit
### Sonrası
### Kibana Query Language Kural Yazımı

``event.provider:``
  ``"Microsoft-Windows-Sysmon"``
  ``"Microsoft-Windows-Security-Auditing"``
``event.code:"1"`` 
``agent.type :"endpoint"``  
``process.entity_id :* ``
``host.name:"desktop-xxxxxxx"`` 
``process.name :"rundll32.exe"`` 
``process.args:"MiniDump"``
``process.command_line:*HKLM*``
``message:"Invoke"``  
``Winlog.event_data.CurrentDirectory:"C:\Users\Administrator\Download"``  


### Event Code 

[Ultimate Windows Security](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/default.aspx)



# SOC - 101


### Elastic Download

[Elastic Search Download](https://www.elastic.co/guide/en/kibana/current/deb.html)


### İlk Adım

`` Elimizde envanter olması gerekiyor ``

### İlk Tespit

``*``


### Sonrası

``Verileri bir formatta indirip ilk aşamada göze çarpan birşey varmı bakılır.``

``Path bazlı kontrol edilebilir.``

``C:\Users\Administrator\Download.``

``iki veya tek harfli exe ler kontrol edilebilir.``

``İlk nereye bakılacağını analiz etmek.``

`` .``


### Kibana Query Language Kural Yazımı

``event.provider:"Microsoft-Windows-Sysmon"``

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



# SOC - 101

## Elastic Download

``https://www.elastic.co/guide/en/kibana/current/deb.html``


## İlk Adım

`` Elimizde envanter olması gerekiyor ``

## İlk Tespit

``Suncuumu client mı sormamız gerekiyor
sunucu ise 
şirket te önce sunuculara firewal kurulur 
case den sonra o vaka da neler olmuş sürecin dışına çıkan bişey varmı
``

``kimler erişebilir``

``üzerinde özel bir servis varmı``

``bağlı olduğu uygulama varmı.``

`` ilgili sistemin ip adresi hostnamei ve domaine dahilmi kontrol edilmeli.``

``**Sistemde şüpheli bir aktivite görüp bilgisayar kapatıldımı. (Memoride tutulan bilgileri kaçırmış oluruz eğer kapatılmışsa) ``

`` .``


## Sonrası

``Verileri bir formatta indirip ilk aşamada göze çarpan birşey varmı bakılır.``

``Path bazlı kontrol edilebilir.``

``C:\Users\Administrator\Download.``

``iki veya tek harfli exe ler kontrol edilebilir.``

``İlk nereye bakılacağını analiz etmek.``

`` .``


## Kibana Query Language Kural Yazımı

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


## Event Code 

[Ultimate Windows Security](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/default.aspx)


## Antivirus & EDR arasındaki farklar ? 
   --

```
*  Antivirus malware imza tabanlı.
   Gelişmiş Antivirüs
   Makine öğrenmesi ile çağrılan patern Match yapıyor.

*  EDR (Endpoint Detection Response)
   Yapılan aktivitenin tüm ağacını çıkartır.
   Kural, korelasyon yapar.
   Olay sonrası kısmı daha güçlü.
   Oluşan bütün eventleri, çalışan makroları sistem dosyalarına hangi process e 
   erişilmiş ise hepsini getirir. Bütün olayı atar.
   Network aktiviteleri de takip edilir.
   Process takip, life sykel, yaşam döngüsü.
   Uzaktan komut çalıştır ve sonuçların yaşam döngüsünü bana logla.

   XDR
   Farklı endpoint de çalışan olayları birleştirir.
   Korelasyon yapar binevi.
   Ajan olmayan makinalardan gelen trafikleri gördüğü için
   bu makinalarında da alarm üretir

   MDR

   Farklı process id ile işleme devam edersen bu ürünleri atlatabilirsin
```

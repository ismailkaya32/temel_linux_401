### **Komutlara giriş 4:**

 ## PAKET KAVRAMI
  
- Paketler, genelde bir yazılımın derlenmiş hali ya da kaynak kodudur.

- Paket 4 maddde içerir:
1) Kaynak kodlar
2) Bağımlılıklar
3) Kurulum Dosyaları
4) Dokümantasyon

### PAKET YÖNETİCİSİ KAVRAMI

- Paket yöneticileri, bilgisayarımıza bir paketi kolaylıkla kurmamızı, kaldırmamızı ve yapılandırmamızı sağlayan sistemlerdir.

### apt Paket Yöneticisi

- apt, bilgisayarımıza bir paketi kolaylıkla kurmamızı, kaldırmamızı ve yapılandırmamızı sağlayan paket yönetim sistemidir.

- update, paketlerin listesini günceller. Sadece yönetici izni(root) ile kullanabiliriz. Örneğin; 'sudo apt update'

  <div align="center">
	<img src=""/>
</div>

 <br/>

- install, paketi yükler. Sadece yönetici izni(root) ile kullanabiliriz.  Örneğin; 'sudo apt install paket_ismi'

<div align="center">
	<img src=""/>
</div>

 <br/>
 
- remove, paketi kaldırır. Sadece yönetici izni(root) ile kullanabiliriz. Örneğin; 'sudo apt remove paket_ismi'

<div align="center">
	<img src=""/>
</div>

 <br/>
 
- autoremove, gereksiz paketleri kaldırır. remove komutundan sonra kullanılması önerilir. Sadece yönetici izni(root) ile kullanabiliriz. Örneğin; 'sudo apt autoremove'

<div align="center">
	<img src=""/>
</div>

 <br/>
 
- purge, hem yüklü olan uygulamayı siler hem de bu uygulamanın ayalarını siler. Ama yine de tüm paketleri silinmez. Bundan dolayı autoremove komutunu kullanmak lazım. Sadece yönetici izni(root) ile kullanabiliriz. Örneğin; 'sudo apt purge paket_ismi'

<div align="center">
	<img src=""/>
</div>

 <br/>
 
- upgrade, kurulu paketleri günceller. Örneğin; 'sudo apt upgrade'

- ---

cat /etc/apt/sources.list komutu apt'nin internetteki hangi kaynaklara bağlanarak paketleri güncellediğini görebiliriz.
 
<div align="center">
	<img src=""/>
</div>

 <br/>

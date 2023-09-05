### **Komutlara giriş 4:**

 # PAKET KAVRAMI:
  
 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/8e105bdc-9cee-4ede-979b-fca1030aaa58"/>
</div>

 <br/>

# PAKET YÖNETİCİSİ KAVRAMI:

- Paket yöneticileri, bilgisayarımıza bir paketi kolaylıkla kurmamızı, kaldırmamızı ve yapılandırmamızı sağlayan sistemlerdir.

<br/>

## apt Paket Yöneticisi:

  <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/7a493149-7d5c-496e-9bff-b2c857cc77ee"/> 
</div> 

- ---
#### update:
- update, paketlerin listesini günceller. Sadece yönetici izni(root) ile kullanabiliriz. Örneğin; `sudo apt update`

Örnek: Aşağıdaki örnekte update komutunu yönetici yetkisi olmadan yapmaya çalıştık. Ama olmadı.

  <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/d8836db7-6ea7-4ffe-82cd-ab51de5ca7cb"/>
</div>

 <br/>
 
Örnek: Aşağıdaki örnekte update komutunu yönetici yetkisi ile yaptık. Ve oldu.
 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/b1a657cb-23db-4298-aaa5-88604e272f84"/>
</div>

- ---
#### install:

- install, paketi yükler. Sadece yönetici izni(root) ile kullanabiliriz.  Örneğin; `sudo apt install paket_ismi`

Örnek: Aşağıdaki örnekte vlc uygulamasını install komutu ile yükledik. 
  
<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/5a342254-3673-4028-b299-af6f263e53bc"/>
</div>

- ---
#### remove:
 
- remove, paketi kaldırır. Sadece yönetici izni(root) ile kullanabiliriz. Örneğin; `sudo apt remove paket_ismi`

Örnek: Aşağıdaki örnekte yüklü olan vlc uygulamasını remove komutu ile kaldırdık. 

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/4b4d0d3d-11d1-4860-b15c-2db4062d04a6"/>
</div>

- ---
#### autoremove:
 
- autoremove, gereksiz paketleri kaldırır. remove komutundan sonra kullanılması önerilir. Sadece yönetici izni(root) ile kullanabiliriz. Örneğin;  `sudo apt autoremove`

Örnek: Aşağıdaki örnekte yüklü olan vlc uygulamasını remove komutu ile kaldırmıştık. vlc uygulamasından geriye gereksiz kalan paketleri kaldırdık.

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/9f1552f2-1ace-450b-9728-70243d09550e"/>
</div>

- ---
#### purge:
 
- purge, hem yüklü olan uygulamayı siler hem de bu uygulamanın ayalarını siler. Ama yine de tüm paketleri silinmez. Bundan dolayı autoremove komutunu kullanmak lazım. Sadece yönetici izni(root) ile kullanabiliriz. Örneğin;  `sudo apt purge paket_ismi`

Örnek: Aşağıdaki örnekte ikinci yol olan purge komutu ile vlc uygulamasını kaldırıyoruz. Ama önceden ben vlc uygulamasını sildiğim için bulunmamaktadır uyarısı vermiştir. 

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/b61e952f-f486-442f-ba73-268687124780"/>
</div>

- ---
#### upgrade:
 
- upgrade, kurulu paketleri günceller. Ama çok paket olduğu için bu iş çok uzun sürer. Örneğin;  `sudo apt upgrade`

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/5d8d32e8-54f5-4397-9d50-874d711dc7e1"/>
</div>

- ---
#### list --upgradable:

 - list --upgradable, bilgisayarda yüklü olan güncellenebilir tüm uygulamaları görürüz.

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/62a8ed06-5434-43c1-a033-be266773b9a5"/> 
</div>

- ---

- cat /etc/apt/sources.list komutu ile apt'nin internetteki hangi kaynaklara bağlanarak paketleri güncellediğini görebiliriz.
 
- ---
# dpkg PROGRAMI:

### debian paket kurma:
- Debian paket yönetim sisteminin temelini oluşturur.

Örnek: Aşağıdaki örnekte leafpad'i kuracağız.
- İlk başta leafpad'in paketinin yüklü olduğu deb uzantılı dosyayı indirdik. 
- Aşağıdaki görselde kırmızı ok ile gösterdiğim gibi cd komutu ile deb uzantılı dosyanın olduğu dizine gidiyoruz.
- Sonra ls komutu ile o dizinde bulunan dosyaları görüntülüyoruz.
- Aşağıdaki görselde yeşil ok ile gösterdiğim satır çalışmıyor. Çünkü `dpkg -i leafpad_0.8.18.1-5_amd64.deb` paketini yüklerken yönetici yetkisi yani root ile yapmadık. Ama sarı ok ile gösterdiğim satırdaki gibi başına sudo ekleyip yönetici yetkisini verdiğimiz zaman deb uzantılı paket yüklenecektir. Ve leafpad'imiz kurulmuş olacak. 

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/bf845942-04f4-4439-8316-841d559b8807"/> 
</div>
 
- ---

### debian paket silme:

Örnek: Aşağıdaki örnekte leafpad'i kaldıracağız.
- İlk başta aşağıdaki görselde kırmızı ok ile gösterdiğim satırda dpkg -l komutu ile dpkg paketli tüm dosyalar ekranda gözükmesin diye grep leafpad komutunu da ekleyip sadece leafpad'e ait olan dizin ekrana geliyor.
- Sonra aşağıdaki görselde yeşil ok ile gösterdiğim satır çalışmıyor. Çünkü `dpkg -r leafpad` paketini silerken yönetici yetkisi yani root ile yapmadık. Ama sarı ok ile gösterdiğim satırdaki gibi başına sudo ekleyip yönetici yetkisini verdiğimiz zaman deb uzantılı paket kaldırılacaktır. Ve leafpad'imiz silinmiş olacak. 

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/69341bf3-231e-4e02-9d1b-bbd9abfba3b4"/> 
</div>    

 <br/>

 - ---
 - ---
 
# ÖZGÜR YAZILIM DÜNYASI VE GNU/Linux

- Özgür yazılım, bedava yazılım demek değildir kullanıcıların özgürlüklerini savunan yazılımdır.

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/c94f51fc-f6cd-40e8-9157-72f09f9576d5"/>
</div>

 <br/>

 ## GNU NEDİR?

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/c130d5be-a412-4e55-9e37-23ab5247f0a2"/>
</div>

 <br/>

## DESKTOP ENVİRONMENT NEDİR?

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/4ce820eb-0b18-425e-ba3a-360ba8e46372"/>
</div>

- ---

Örnek: KDE Plasma 5  --> https://kde.org/tr/plasma-desktop/

- Bu masaüstü arayüzü sade yapıda ve sistemi yormaz.

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/d206f0b6-556c-451a-a8cb-46e793d0ec11"/>
</div>

- ---

Örnek: GNOME  --> https://www.gnome.org/

- Bu masaüstü arayüzü sisteme yük bindirsede başlangıç kullanıcılar için daha uygundur. Çünkü daha büyük göserller ve iconlar barındırır. 

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/ba5cce0a-29ce-45dc-9425-ec99441f0076"/>
</div>

 - ---

Örnek: Unity -->  https://ubuntuunity.org/

- Çok uzun süre ubuntunun varsayılan environment'iydi. Ama sonra sistemde çok ağırlık yapan ve çöken bir yapısıdan dolayı yeni sürümlerde varsayılan arayüz olarak kullanılmamaktadır.
 
<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/0d141ca1-b438-484b-99db-d851d7b887f4"/>
</div>

 - ---

Örnek: xfce4 --> https://www.xfce.org/

- 'sudo apt install xfce4' komutu ile desktop environment indirebiliriz.
 
<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/bd20bd03-3f16-4ef1-8981-5b38af365ab6"/> 
</div>

 <br/>

- Kurulum:
<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/3eb2d018-40ce-4936-ae65-1ecc9062cc2e"/> 
</div>  

- ---

Örnek: mate -->  https://mate-desktop.org/

- 'sudo apt install ubuntu-mate-desktop' komutu ile desktop environmenti indirebiliriz.

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/2e9a7f2f-ae95-44cb-b05e-af6f7271d606"/> 
</div>

 <br/>

 ## PARDUS NEDİR? 

 - Debian tabanlıdır.
 - https://www.pardus.org.tr/ web sitesinden daha ayrıntılı bilgi edilinebilir. 

 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/7a419e52-c3e0-4b7d-a2dc-ce6bfa499c55"/> 
</div>

 <br/>

<div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/0278dfd1-df60-4411-84b3-3acc92f20b2e"/>

</div>

- ---

# SHELL PROGRAMLAMA (KABUK PROGRAMLAMA) 

## echo:

- Ekrana bir şeyler yazdırmamızı sağlar.

Örnek: Aşağıdaki örnekte ekrana ben ismail yazdırıyorum.

 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/d9e721e3-daa2-437b-a8ca-16a544a0cbcf"/> 
</div>      

- ---

### EN YAYGIN KULLANILAN SHELLER (KABUKLAR) :

#### sh : 
- Unix kabuğudur.
- İlk kabuk versiyonudur.
- dash kabuğuna bağlıdır. Aşağıdaki görselde bir file dosyasına ait sh kabuğunun dash kabuğuna bağlantılı olduğunu görebiliriz.

 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/c7720e65-1f30-4e77-97a9-fd011bfe5d17"/> 
</div>   

<br/>

#### bash : 
- ilk başta sh tabanlı iken sonra geliştirmeler ile sh'tan ayrılmıştır.
- Ve artık daha popüler olan bir kabuktur.

#### dash : 
- Debian için geliştirilmiştir.
- bash'a göre 2 kat daha hızlıdır.
- Daha az sistem kaynağı (CPU,RAM,vb) kullanır.

- ---

- Aşağıda shell programlama örneklerini adım adım göreceğiz.

ÖRNEK 1: 

Adım 1: Önce oluşturacağımız dosyanın hangi dizinde olmasını istiyorsak o dizine gidiyoruz. Ondan sonra istediğimiz dosyayı nano komutu ile oluşturuyoruz. 

- Yukarıda verilen adıma göre ben önce Desktop konumuna gittim. Sonra nano komutu ile merhaba.sh dosyasını oluşturdum. Bunu aşağıda bulunan görselden görebiliriz.

 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/2dd5c924-80a3-462e-a9b7-042b0861a79d"/> 
</div>  

<br/>

Adım 2 : Sonra nano ile oluşturup açtığımız dosyanın içine yapmak istediklerimizi yazıyoruz.

- Yukarıda verilenlere göre ben nano ile oluşturup açtığım merhaba.sh 'ın içine yapmak istediklerimi yazıyorum. Aşağıdaki görselde yapmak istediklerim yazıyor. Görselin altında da yapmak istediklerimi açıkladım.

 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/f0dfa872-375e-4d1c-8389-96ef6208b558"/> 
</div>   

<br/>

Açıklama:

- Öncelikle nano komutu ile merhaba.sh dosyasını oluşturup içine girdik.
- merhaba.sh 'ın içine girdiğimiz zaman birinci satıra kullanacağımız kabuğun yolunu yazdık.
- Üçüncü satırda echo komutu ile ekrana ben İSMAİL yazmasını sağladık.
- Dördüncü satırda merhaba.sh dosyasını çalışırdığımız zaman merhaba.sh dosyasının bulunduğu konuma touch komutu ile ismail.txt dosyasını oluşturdu.
- Beşinci satırda ismail.txt dosyasının içine tanıştığıma memnun oldum yazmasını sağladık.

<br/>

Adım 3: Yapmak istediklerimizi yazıp ctrl+x kısayolu ile dosyanın içine kaydediyoruz. Ve dosyamız kaydettiğimiz konumda görünüyor olacak. 

- Yukarıda verilenlere göre ben ctrl+x kısayolu ile yapmak istediklerimi dosyanın içine kaydediyorum. Ve dosyam Desktop dizininde gözüküyor. Aşağıda bulunan görselden bunu görebiliriz.

 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/3e421fe3-2683-48c5-b5bf-40bd3c2a13dc"/> 
</div>    

<br/>

Adım 4: Oluşturduğumuz dosyayı çalıştırmak için dosyanın bulunduğu dizine gidip yöneticiye çalıştırma yetkisini atamak gerekiyor. Bunun için aşağıdaki görsel üzerinden adımları takip edebiliriz. Aşağıda bulunan görselin altında açıklamaları yazmaktadır.

 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/066d2fb7-adc2-4f49-8d8c-4f6114b2937e"/> 
</div>     

<br/>

Açıklama:

- Yukarıda verilenlere göre merhaba.sh dosyasını çalıştırmak için önce kırmızı okla gösterilen yerde ls komutu ile Desktop dizininde bulunan dosyaları listeledim. Orada merhaba.sh 'ı buldum.
- Sonra yeşil okla gösterilen yerde ./merhaba.sh komutu ile dosyayı çalıştımak istedim ama bu dosyayı çalıştırma yetkimin olmadığına dair uyarı aldım.
- Öyle olunca mavi okla gösterilen yerde ls -al komutu ile Desktop dizininde bulunan dosyaların izinlerine baktım. Ve merhaba.sh dosyasında yönetici olarak çalıştırma yetkimin olmadığını gördüm.
- Bundan dolayı sarı okla gösterilen yerde chmod +x komutu ile merhaba.sh dosyasına yönetici çalıştırma yetkisini veriyorum.
- Mor okla gösterilen yerde ll komutu ile (ls -al komutu) merhaba.sh dosyasına yöneticinin çalıştırma yetkisinin verilip verilmediğini kontrol ediyorum. Ve verildiğini görüyorum.
- En son olarakta turuncu okla gösterilen ./merhba.sh komutu ile dosyayı çalıştırıyorum. Ve dosyanın çalıştığını görebiliyorum. Ekrana ben İSMAİL yazarken Desktop dizinine de ismail.txt dosyasının oluştuğunu görüyorum.

Adım 4 Alternatifi:

- Direkt yönetici yetkisi vermeye gerek kalmadan bash komutu ile dosyayı çalıştırabiliriz. Mesela aşağıdaki görselde gördüğünüz üzere bash komutu ile direkt merhaba.sh komutunu çalıştırıp ekrana ben İSMAİL yazarken Desktop dizinine de ismail.txt dosyasının oluştuğunu görüyoruz.

 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/240c5272-cb57-4e03-b9ca-ec1c9db55448"/> 
</div>   

- ---

 * ÖRNEK 1' DE AYRINTILI ADIMLARI ANLATTIĞIM İÇİN DİĞER ÖRNEKLERDE DİREKT İÇİNE YAZILANLARI VE ÇIKTILARI VERECEĞİM !!!

- --- 

ÖRNEK 2: 

Adım 1: deneme1.sh adlı dosya oluşturdum.

<br/>

Adım 2: deneme1.sh 'ın içine yapmak istediklerimi yazdım.

 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/c2a65149-e1df-431b-b1d7-845011b6a753"/> 
</div>      

<br/>

Adım 3: Alternatif yolu yani bash komutunu kullanarak  deneme1.sh dosyasını çalıştırıyorum. Ve çıktıyı alıyorum.

 <div align="center">
	<img src="https://github.com/ismailkaya32/temel_linux_401/assets/122615472/52434977-b9e0-4650-8976-c498bf1be2d9"/> 
</div>      

- ---

ÖRNEK 3: 


...
...
...


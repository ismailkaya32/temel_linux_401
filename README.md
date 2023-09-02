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

cat /etc/apt/sources.list komutu apt'nin internetteki hangi kaynaklara bağlanarak paketleri güncellediğini görebiliriz.
 
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

 <br/>

 

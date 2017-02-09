### Kontrol Paneli Yedek Alma İşlemi
cPanelimizden **"Dosyalar"** kategorisinden **"Yedekleme"** aracına giriş yapoyoruz.

![Yedekleme](https://kova1.ni.net.tr/warden/bilgi-bankasi/ZbifR1UWMlTOucoNtOSfrCBxoD1cIQ1U4eAwDZzO.png)

Bu yedekleme aracında hesabınızın kısım kısım yedeğini alabilirsiniz. ancak bu yöntemi önermiyoruz. Hesabınızın tam bir yedeğini oluşturmak için **"Tam Bir Web Sİtesi Yedeği İndir"** seçeneğine tıkıyoruz.

![Yedekleme2](https://kova1.ni.net.tr/warden/bilgi-bankasi/GYR6kjDVPWzizyq1gYBuGqfcVM7rPxPwAXs5dx8P.png)


![Yedekleme3](https://kova1.ni.net.tr/warden/bilgi-bankasi/TKjeHoOAaAjdnQNyKx9OQTPWQ7ql8bXmJJrZ5rEI.png)

**“Yedekleme hedefi”** yedeğinizin alındıktan sonra bulunacağı dizini belirler eğer giriş dizini olarak kalır ise yedeğiniz ftp ile bağlandığınızda karşınıza gelen dosyaların içerisinde görünecektir. Yedek oluştur dediğinizde e-posta adresi belirtirseniz. Yedekleme tamamlandığında mail adresinize bilgi maili gelecektir.
Yedekleme işlem süresi dosya adetinizin ve disk kapasitenizin durumuna göre değişmektedir. “Geri dön” dedikten sonra yedekleme işleminin başladığını aşağıdaki resimde görebilirsiniz,

![Yedekleme4](https://kova1.ni.net.tr/warden/bilgi-bankasi/a2YBnQtRfloPLCGZl9Fk1C9d8iV1bnzVmpUbZEab.png)

**“İndirilebilir yedekler”** kısmından yedeğinizi bilgisayarınıza indirebilirsiniz. İndirmiş olduğunuz yedeği hosting hizmeti aldığınız yere iletirseniz/yüklerseniz restore komutu ile yedeğinizi kolaylıkla açabilirsiniz. Yedeğiniz ayrıca ftp ana dizininde yer almaktadır, daha sonra kullanmak isterseniz yedeğinize bu dizinden ulaşabilirsiniz.

![Yedekleme5](https://kova1.ni.net.tr/warden/bilgi-bankasi/Gsq9TVKpO1SMjuRUURFWznMIec4ie8L2RvrzVdPo.png)

Yedek alma işlemimiz tamamlanmıştır.

----

### Yedek Yükleme & Restore İşlemi
Bu işlemi gerçekleştirebilmek için SSH yetkiniz olması gerekmektedir. standart hosting paketi veya reseller hizmeti alıyorsanız SSH yetkisi size verilmez. elinizde cPanel kontrol paneli üzerinden alınmış bir **tar.gz** yedeği mevcut ise hizmet aldığınız yere iletmeniz yeterli olacaktır. Anlatımımızı cPanel kontrol paneline sahip bir sanal sunucu yada fiziksel sunucunuz olduğunu varsayarak ilerliyoruz.

```
cd /home 
/scripts/restorepkg cpmove-ozgurcif.tar.gz
```
İşlem tamamlandığında yedeğimiz yüklenmiş olacaktır. Dikkat etmemiz gereken konu **"ozgurcif"** adlı kullanıcının sunucuda olmaması gerekmektedir. eğer eski bir yedeği mevcut **"ozgurcif"** hesabının üzerine yüklemek isterseni aşağıdaki komutu uygulamanız gerekmektedir.

```
/scripts/restorepkg cpmove-ozgurcif.tar.gz --force
```
Komutu ile mevcut hesabımızın üzerine yazarak yedeğimizi yüklemiş oluyoruz. Yedek alma işlemimizi cPanel'e giriş yapmadan da yapabiliriz. aşağıdaki komutu uygulayarak SSH üzerinden hesabınızın yedeğini kolaylıkla alabilirsiniz.

```
/scripts/pkgacct ozgurcif
```
Komut'u ile yedeğimizi home dizinie almış oluyoruz. **cd /home** dizinini görüntülediğimizde tar.gz şeklinde yedeğinizi görüntüleyebilrisiniz.

SSH üzerinden herhangi bir hesap silmek istiyor isek

```
/scripts/removeacct ozgurcif
```

Komut ile **"ozgurcif"** isim kullanıcımızı sunucumuzdan silmiş oluyoruz.

---

### Özet
```
/scripts/pkgacct kullanıcı adı = Hesabımızın yedeğini alır.
/scripts/restorepkg yedek.tar.gz = Hesabımızın yedeğini açar.
/scripts/removeacct kullanıcı adı = Hesabımızın yedeğini siler
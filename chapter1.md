### Giriş
Yedekleme işlemi internet sitenizin tam bir kopyasının belirli bir lokasyonda tutulması anlamına gelmektedir. Sitenizde herhangi bir nedenden dolayı oluşabilecek sorunlar ve veri kayıplarına karşı web-sitelerinizin düzenli olarak yedeğini almalısınız. Aksi halde herhangi bir problem karşısında sitenizdeki tüm verilerinizi kaybedebilirsiniz. Bu yüzden değer verdiğiniz sitelerin yedeklerini almanızı öneriyoruz. Bu makaleimizde cPanel kontrol panelinde en sağlıklı ve basit şekilde yedek nasıl alınır ve  cPanel kontrol panelinden aldığımız bir yedeği SSH üzerinden nasıl yükleyebileceğimizi öğreneceğiz.

----
### Kontrol Paneli Yedek Alma İşlemi
cPanelimizden **"Dosyalar"** kategorisinden **"Yedekleme"** aracına giriş yapoyoruz.
![](/assets/yedekleme.png)
Bu yedekleme aracında hesabınızın kısım kısım yedeğini alabilirsiniz. ancak bu yöntemi önermiyoruz. Hesabınızın tam bir yedeğini oluşturmak için **"Tam Bir Web Sİtesi Yedeği İndir"** seçeneğine tıkıyoruz.


 ### Giriş
Yedekleme işlemi internet sitenizin tam bir kopyasının belirli bir lokasyonda tutulması anlamına gelmektedir. Sitenizde herhangi bir nedenden dolayı oluşabilecek sorunlar ve veri kayıplarına karşı web-sitelerinizin düzenli olarak yedeğini almalısınız. Aksi halde herhangi bir problem karşısında sitenizdeki tüm verilerinizi kaybedebilirsiniz. Bu yüzden değer verdiğiniz sitelerin yedeklerini almanızı öneriyoruz. Bu makaleimizde cPanel kontrol panelinde en sağlıklı ve basit şekilde yedek nasıl alınır ve cPanel kontrol panelinden aldığımız bir yedeği SSH üzerinden nasıl yükleyebileceğimizi öğreneceğiz.

----
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

**“Yedekleme”** bölümünün alt kısmında **“Kısmi yedekleme”** bulunmaktadır, bu kısımda ayrı olarak sql ve mail yedeklerinizi alabilir farklı hesaplara yükleyerek kullanabilirsiniz. (Kısmı yedekle stabil çalışmaması nedeniyle çok kullanılan bir özellik değildir.)

![Yedekleme6](https://kova1.ni.net.tr/warden/bilgi-bankasi/1tnuziedRkVUiJC1QVinFyTHQ3ccy0cjjJ2iwyrL.png)

Yedek alma işlemimiz tamamlanmıştır.

### Yedek Yükleme & Restore İşlemi
Bu işlemi gerçekleştirebilmek için SSH yetkiniz olması gerekmektedir. standart hosting paketi veya reseller hizmeti alıyorsanız SSH yetkisi size verilmez. elinizde cPanel kontrol paneli üzerinden alınmış bir **tar.gz** yedeği mevcut ise hizmet aldığınız yere iletmeniz yeterli olacaktır. Anlatımımızı cPanel kontrol paneline sahip bir sanal sunucu yada fiziksel sunucunuz olduğunu varsayarak ilerliyoruz.



```
cd /home
[/home]# /scripts/restorepkg cpmove-ozgurcif.tar.gz
```


###Plesk Panel "Disallowed Path Characters" Sorunu
Bir çok kullanıcı için Plesk Panel windows serverlar için vazgeçilmez kontrol panelidir. 11 ve 12 sürümü ile daha stabil hale gelen ve eski sürümlere göre oldukça geliştirilen plesk panelde, ASP tabanlı
yazılımlarda karakter hataları görülebilmektedir. Bu hatalardan bir tanesi de **Disallowed Path Characters** hatasıdır. Sitenizi sunucuya attıktan sonra eğer bu hatayı alıyorsanız çözüm için aşağıdaki
adımları takip etmeniz yeterli olacaktır.

Öncelikle alacağınız hata koduna bir örnek verelim.

```
`Disallowed Path Characters`

`Server.MapPath() error 'ASP 0175 : 80004005'`
```

####Çözüm

Plesk Panele giriş yaparak sorun yaşadığınız hesaba ulaşın.Hesabınız altındaki **Websites&Domain** altında bulunan **Virtual Directories** dizine giriş yapın.

![Plesk](/assets/pls1.png)

Bu bölüme giriş yaptıktan sonra karşınıza gelen sayfada **Directory Properties** bölümüne giriş yapın.

![Plesk2](/assets/plsk2.png)

Karşınıza gelen sayfa üzerinde **Allow to use parent paths** bölümünü göreceksiniz.Bu ayarın sağ tarafındaki kutucuğu işaretleyerek kaydedin.

![Plesk3](/assets/plsk3.png)

Bu adımları eksiksiz olarak yaptığınızda aldığınız karakter hatasının düzeldiğini göreceksiniz.
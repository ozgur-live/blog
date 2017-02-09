cPanel'e giriş yapmanın birden fazla yolu bulunmaktadır. cPanel hesabınıza giri yapabilmek için WHM panel içerisinde bir hesap oluşturulması **"Create an Account"** gerekmektedir. Eğer hosting hizmeti sağlayan bir firmadan Linux cPanel hosting paketi aldıysanız bu işlemler sunucuda otomatik olarak gerçekleştirilir ve cPanel hesap bilgileriniz mail adresinize otomatik olarak gönderilir.
WHM panel yönetimi sizde olan bir sunucu yada reseller hizmetiniz var ise içerisindeki hesaplara WHM panel üzerinden de erişim sağlayabilirsiniz. Bu makalemizde cPanel hesabınıza bağlanmanızın birçok yöntemini göstereceğiz.

----
#### **_Gereksinimler_**
Linux cPanel hosting paketi yada Linux cPanel sunucu

----

#### **_Kurulum & Anlatım_**

##### İp adresi ile şifrelenmiş bir bağlantı üzerinden erişim

_**https://192.168.0.1:2083**_   İp adresinizin sonuna :2083 yazılarak cPanel hesabınıza bağlanabilrisiniz

##### İp adresi ile şifrelenmemiş bir bağlantı üzerinden erişim

_**http://192.168.0.1:2082**_ İp adresinizin sonuna :2082 yazılarak cPanel hesabınıza bağlanabilrisiniz

##### **Alan adı ile şifrelenmiş bir bağlantı üzerinden erişim**

_**https://example.com:2083**_  Alan adınızın sonuna :2083 yazılarak cPanel hesabınıza bağlanabilrisiniz

##### Alan adı ile şifrelenmemiş bir bağlantı üzerinden erişim

_**http://example.com:2082**_ Alan adınızın sonuna :2082 yazılarak cPanel hesabınıza bağlanabilirisiniz

_**http://example.com/cPanel (önerilen)**_  Alan adınızın sonuna /cpanel yazılarak cPanel hesabınıza bağlanabilirisiniz.

-----
#### **_Yapılandırma_**
<br>
WHM panel üzerinden oluşturmuş olduğunuz hesapların direkt olarak cPanel'lerine giriş sağlayabilirsiniz. Bunun için Home _**Account Information »List Accounts**_ Tab'larından işlem gerçekleştirebilirsiniz.

![WHM Panel](https://kova1.ni.net.tr/warden/bilgi-bankasi/khqntqv7qjwCkRolKtyAJ0UtN7MvysHjOpQHIudh.png)
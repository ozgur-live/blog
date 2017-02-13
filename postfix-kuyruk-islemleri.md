Postfix mail serverde kontrol edilmesi gereken yerlerden biri olan kuyruk\(queue\) işlemleri, mail serverde ortaya çıkan geç gitme gibi problemlerin çözümü açısından bilinmesi gereken yönetim arayüzlerinden birisi. Bu yazıda olası sorunlarda işinize yarayabilecek bir kaç kod bloğundan bahsedeceğim.

Postfix mail kuyruğu yönetim arabirimi olan postqueuenin bazı özellikleri şu şekilde.

#### Mail kuyruğunda kaç tane mail olduğunu görmek için

```
postqueue -p
```

Bu kod okunabilir bir şekilde serverinizdeki işlem gören veya beklemede olan mailleri çıktı olarak ekrana basar

Örnek çıktı

```
A0A563005B5*     599 Fri Nov 13 14:43:48  mail@sanalsantral.org
                                          mail@enisozgen.com
-- 0 Kbytes in 1 Request.
```

#### Kuyduktaki maillerin tekrar gönderilmesini sağlamak için

Serverde herhangi bir değişiklik yaptıktan sonra kuyrukta biriken mailleri gönderme işlemi

```
postqueue -f
```

#### Kuyruktaki mailleri silme işlemi

Çıkabilecek sorunu göze almak şartı ile mail kuyruğunda fazlada mailin biriktiği taktirde kullanılabilir.

```
postsuper -d ALL
```

#### Kuyruktaki belirli bir kişiden gelen mailleri silmek için

Bu komut ile serverinizde sorun çıkan kişinin maillerini manuel olarak da silebilirsiniz.

```
mailq | tail -n +2 | grep -v '^ *(' | awk  'BEGIN { RS = "" } { if ($8 == "USER@EXAMPLE.COM" && $9 == "") print $1 } ' | tr -d '*!' | postsuper -d -
```

#### Yapılandırdığınız serverin gelişmiş queue ayarlarını görmek içinse

Bu kod ile yapılandırmanızda varsayılan olarak gelen veya sizin yapılandırmış olduğunuz ayarları main.cf veya master.cf den daha kaliteli olarak görebilirsiniz.

```
postconf -d | grep queue
```




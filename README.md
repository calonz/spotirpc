```
Discord RPC Client için Spotify eklentisi.

Bu araç Discord biyografinizde hangi müziği dinlediğinizi, Albüm - Podcast - Sanatçı verilerinin 
hepsini durumunuza ekler. Kullanılan diller Node.JS (JavaScript) ve C# olarak belirtilmektedir.
Bu araç tamamen legal olup, herhangi bir şekilde Spotify'ın kurallarına, gizlilik sözleşmesine
ve veri kullanım bilgilerine zarar veya kayıp verdirmemektedir. Spotify'ın geliştiriciler için 
yayınlamış olduğu WebAPI üzerinden bulunduğu cihaz (Bilgisayar) üzerinden anlık olarak çalınan müzik 
bilgilerini ve podcast detaylarını alarak Discord'un Developer Tools aracılığı ile bulunduğu cihaz 
üzerinden Rich Presence verisi olarak sunucuya iletmektedir.
```

```
Bu güçlendirmeyi mümkün kılan kişi : @MuhammedMGS (evet, rica ederim <3)

macesdev rolü : Kurucu
Instagram : @muhammedmgs
Twitter : @muhammedmgs
Discord : MuhammedMGS#1881
```

```
Kullanımı

Programı indirdikten sonra spotipod_setup.exe (Windows için geçerlidir*) dosyası ile kurulumunuzu 
rahatlıkla yapabilirsiniz. Discord ve Spotify uygulamalarınızı açın, Discord > Kullanıcı Ayarları > Bağlantılar
sekmesinden Spotify hesabınızı Discord hesabınız ile eşitledikten sonra "Spotify durumumu profilimde
görüntüle" seçeneğini aktif hale getirin. Ardından Windows Tepsisi üzerinden RPC > Çalıştır seçeneğine tıklayarak
aktif edebilirisiniz. Artık uygulama anlık olarak dinlediğiniz müziği Spotify'a aktaracaktır. Eğer bir sorun ile
karşılaşırsanız proje/Issues sekmesinden talep oluşturabilirsiniz.
```

```
Gereksinimler (İhtiyaç Duyulan Yazılımlar)

.NET Framework 4.2.7 (https://dotnet.microsoft.com/download/dotnet-framework/net472 - minumum sürüm : 4.2.7), 
Node.JS (https://nodejs.org/en/download/current/ - minumum sürüm : 16.7.0).

Eğer kurulumları yapmanız halinde sorun
yaşıyorsanız proje/Issues sekmesinden talep oluşturabilirsiniz.
```

```
Config (JSON) Detaylandırması ve WebAPI Yapılandırması

Uyarı! : Bu madde teknik detayları içermektedir. Eğer pek bilginiz yoksa ayarlarla oynamamanız tavsiye edilir.

Uygulamayı kurduğunuz dizin üzerinden ./spotipod/config/app.json dosyası üzerinden yola çıkıcak olursak, verilerimizi 
ve ne işe yaradıklarını detaylıca inceleyelim isterseniz.
```

```json
Taslak

{
    "webapiLocation": "/webapi",
    "webapiRunCommand": "node webapi.js",
    "webapiValueExractLocation": "/chace.json"
}
```

```json
STRING : webapiLocation Nedir?

Programın Spotify uygulaması üzerinden veri alabilmesi için kullandığı Spotify Developer Tools sadece 
JavaScript dili ile anlaşabildiği için, ana uygulama (C#) diliyle programlandığından dolayı uyumsuzluk 
oluşacaktır. Bu yüzden ana uygulama (C#) WebAPI den veri alabilmek için JavaScript üzerinden (cmd snipplet
ile veri çekebilme olasılığı olduğundan dolayı NodeJS tercih edildi) veri oluşturacak ve bunu bir json 
dosyasına yazacaktır. ana uygulama (C#) bu json dosyasını okuyarak RPC'yi aktif edebilir. Bu veri de 
WebAPI'nin konumunu belli etmekle görevlidir.

Örneğin : 

{
    "webapiLocation": "C:\\Program Files\\macesdev\\spotipod\\webapi",
}
```

```json
STRING : webapiRunCommand Nedir?

wenapiLocation ana uygulamanın (C#) JavaScript (NodeJS)'i tetikleyerek veri çekmesine sebep olur. Komut geliştirici
(macesdev) otomatik olarak kurulum esnasında ayarlar. Eğer WebAPI'nin çalışmadığını düşünüyorsanız bu komutu WebAPI
üzerinden çalıştırarak veri elde edilip edilmediğini kararlaştırabilirsiniz

Örneğin : 

{
    "webapiRunCommand": "node webapi.js"
}

Burada webapiLocation klasörü içerisindeki webapi.js dosyasını tetiklereyek veri elde eder, C# ise bunu okuyarak
RPC'yi çalıştırmasına yardımcı olur.
```

```json
STRING : webapiValueExractLocation Nedir?

WebAPI'nin tetiklendikten sonraki elde edilen verilerin saklandığı (depo edildiği) konumdur. Bu verilerin
değiştirilmesi programın düzgün
çalışmamasına sebep olabilir. Chace dosyası aşağıdaki şekilde olmalıdır.


{
    "audioPodcastName": "B16 - Bize Tavsiye Edebileceğiniz Filimler Var mı?",
    "mainPodcastName": "Bir Elit Bilim İnsanı: Prof. Dr. Celal Şengör",
    "podcastBannerURL": "https://i.scdn.co/image/465c4b24a397642055863081c83719c4992d006a",
    "audioPodcastTime": 4.02,
    "audioLatestTime": 1.05,
    "webapiSyntaxVersion": 1
}
```

```
Bu aracı mümkün kılan Spotify Developer Tools ve Discord Developer Portal'a teşşekürler <3
```

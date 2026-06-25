🌟 MOTTOVERSE - SIKÇA SORULAN SORULAR VE CEVAPLAR (FAQ) 🌟
========================================================================

1. KURULUM, BAĞIMLILIKLAR VE ÇALIŞTIRMA
------------------------------------------------------------------------
Soru: Uygulamayı çalıştırmak için ekstra bir Python kütüphanesi kurmam gerekiyor mu?
Cevap: Hayır. Mottoverse tamamen Python'ın yerleşik (built-in) kütüphanelerini kullanır. 
       Bu sayede herhangi bir "pip install" komutu çalıştırmanıza gerek kalmadan çalışır.

Soru: Python scriptini başlattığımda pencere aniden kapanıyor veya ekrana gelmiyor, neden?
Cevap: Eğer uygulamayı ilk kez çalıştırıyorsanız veya geçerli bir ayarınız yoksa, uygulama 
       ana widget penceresini gizler ve ekranın ortasında "Veri Kaynağı Ayarları" penceresini 
       açar. Bu pencereyi kapatırsanız uygulama tamamen sonlanır. Ayarları yapıp kaydettiğinizde 
       widget görünür olacaktır.

Soru: Uygulamanın hazır bir .exe sürümü var mı?
Cevap: Evet, projenin ana klasöründe derlenmiş bir .exe sürümü mevcuttur. Python yüklü olmayan 
       bilgisayarlarda doğrudan bu .exe dosyasını çalıştırarak widget'ı kullanabilirsiniz.

2. WINDOWS ENTEGRASYONU VE SİSTEM ÖZELLİKLERİ
------------------------------------------------------------------------
Soru: "Masaüstünü Göster" (Win + D) kombinasyonunu kullandığımda bu widget neden kaybolmuyor?
Cevap: Uygulama, Windows'un yerel `user32` ve `ctypes` API'lerini kullanır. Widget açılırken 
       Windows'un masaüstü katmanını yöneten arka plan pencerelerine bir alt pencere (child window) 
       olarak bağlanır. Böylece sistem widget'ı duvar kağıdının bir parçası gibi görür ve gizlemez.

Soru: Pencerenin kenarları Windows 11'deki gibi oval ve yuvarlatılmış. Bunu nasıl sağladınız?
Cevap: Kod içerisinde Windows Masaüstü Pencere Yöneticisi (DWM) API'sine doğrudan erişilmektedir. 
       `dwmapi.DwmSetWindowAttribute` fonksiyonu çağrılarak donanımsal köşe yumuşatma aktif edilir.

Soru: Bu uygulama Linux veya macOS işletim sistemlerinde çalışır mı?
Cevap: Hayır. Uygulamanın masaüstüne sabitleme ve gelişmiş arayüz özellikleri tamamen Windows 
       yerel API'lerine bağımlı olduğundan yalnızca Windows işletim sistemlerinde çalışır.

3. VERİ KAYNAKLARI VE SENKRONİZASYON (RSS & JSON)
------------------------------------------------------------------------
Soru: RSS modu ile Yerel JSON modu arasındaki fark nedir?
Cevap: RSS Modu belirttiğiniz canlı web akışlarını dinler ve yeni bir söz eklendiğinde otomatik 
       güncellenir. Yerel JSON Modu ise bilgisayarınızdaki bir `.json` dosyasından belirlediğiniz 
       saniye aralığında rastgele seçimler yaparak sürekli bir akış sağlar.

Soru: RSS modunda sözlerin ne kadar sürede bir değişeceğini ayarlayabilir miyim?
Cevap: Hayır, arayüzdeki saniye ayarı yalnızca JSON modu için geçerlidir. RSS modu sabit 2 
       saniyelik periyotlarla arka planda kaynaktaki canlı güncellemeleri (yeni sözleri) takip eder.

Soru: "Gözat" diyerek seçtiğim yerel JSON dosyası orijinal konumundan siliniyor mu?
Cevap: Hayır. Seçtiğiniz dosya güvenli bir şekilde uygulamanın veri alanına 
       (`%appdata%/Mottoverse_Data/mottoverse.json`) kopyalanır ve uygulama çalışırken bu kopya 
       dosyayı referans alır. Orijinal dosyanıza dokunulmaz.

4. KULLANICI DENEYİMİ VE ARAYÜZ KONTROLLERİ
------------------------------------------------------------------------
Soru: Widget'ın yerini sabitlemek ve yanlışlıkla taşınmasını engellemek mümkün mü?
Cevap: Evet. Widget üzerinde herhangi bir yere sağ tıklayıp "📌 Sabitle" seçeneğini seçtiğinizde 
       arayüz kilitlenir. Kilitlendiğinde köşelerdeki boyutlandırma tutamaçları (◤ ve ◢) gizlenir. 
       Tekrar taşımak için sağ tıklayıp "🔓 Kilidi Kaldır" demeniz yeterlidir.

Soru: Pencereyi fareyle boyutlandırdığımda metinler neden taşmıyor veya kırpılmıyor?
Cevap: Uygulamada dinamik metin kaydırma (`wraplength`) mimarisi mevcuttur. Siz genişliği 
       değiştirdikçe metnin satır sonu sınırı otomatik güncellenir ve pencere yüksekliği içeriğin 
       uzunluğuna göre esner.

5. HATA YÖNETİMİ VE SORUN GİDERME
------------------------------------------------------------------------
Soru: RSS adresi eklerken "Birincil URL geçerli bir RSS akışı döndürmedi" hatası alıyorum. Nedir?
Cevap: Uygulamanın bağlantıyı doğrulaması için girilen linkin standart bir XML formatında olması 
       ve içinde en az bir `<item>` veya `<entry>` etiketi ile birlikte `<title>`, `<description>` 
       ve `<author>` yapılarını barındırması gerekir.

Soru: İnternet bağlantım koptuğunda veya RSS aldığım web sitesi çöktüğünde widget kapanır mı?
Cevap: Hayır. Kod mimarisinde yedekli RSS ve korumalı hata blokları yer alır. Birincil adrese 
       ulaşılamazsa otomatik olarak yedek adrese geçilir. Hiçbirine ulaşılamazsa uygulama çökmez, 
       arka planda güvenli bir şekilde beklemeye devam eder.
========================================================================

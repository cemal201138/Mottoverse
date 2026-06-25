# 🌟 MOTTOVERSE - SIKÇA SORULAN SORULAR VE CEVAPLAR (FAQ) 🌟

---

## 1. KURULUM, BAĞIMLILIKLAR VE ÇALIŞTIRMA

### Soru: Uygulamayı çalıştırmak için fazladan bir Python kütüphanesi kurmam gerekiyor mu?
**Cevap:** Hayır. Mottoverse tamamen Python'ın yerleşik kütüphanelerini (`tkinter`, `urllib`, `xml`, `ctypes`, `json`, `shutil`) kullanır. Bu sayede herhangi bir "pip install" komutu çalıştırmanıza gerek kalmadan, doğrudan kutudan çıktığı gibi çalışır.

### Soru: Python betiğini başlattığımda pencere aniden kapanıyor veya ekranda görünmüyor. Neden?
**Cevap:** Uygulamayı ilk kez çalıştırıyorsanız veya geçerli bir kayıtlı ayarınız yoksa, uygulama ana araç (widget) penceresini gizler ve ekranın ortasında "Veri Kaynağı Ayarları" penceresini açar. Eğer bu pencereyi kapatırsanız, uygulama tamamen sonlanır. Ayarları yapılandırıp kaydettiğinizde widget görünür hale gelecektir.

### Soru: Uygulamanın önceden derlenmiş bir .exe sürümü mevcut mu?
**Cevap:** Evet, projenir ana klasöründe derlenmiş bir `.exe` sürümü mevcuttur. Python yüklü olmayan Windows bilgisayarlarda, bu `.exe` dosyasını doğrudan çalıştırarak widget'ı kullanabilirsiniz.

---

## 2. WINDOWS ENTEGRASYONU VE SİSTEM ÖZELLİKLERİ

### Soru: "Masaüstünü Göster" (Win + D) kısayolunu kullandığımda bu widget neden kaybolmuyor?
**Cevap:** Uygulama, yerel Windows `user32` ve `ctypes` API'lerini kullanır. Widget açıldığında, Windows masaüstü katmanını yöneten arka plan pencerelerine (`Progman` veya `WorkerW`) bir alt pencere (child window) olarak bağlanır. Böylece sistem widget'ı duvar kağıdının bir parçası olarak görür ve gizlemez.

### Soru: Pencerenin köşeleri tıpkı Windows 11'deki gibi oval ve yuvarlatılmış. Tkinter normalde bunu desteklemez; bunu nasıl başardınız?
**Cevap:** Kod içerisinde Windows Masaüstü Pencere Yöneticisi (DWM) API'sine doğrudan erişilmektedir. `dwmapi.DwmSetWindowAttribute` fonksiyonu çağrılarak donanım hızlandırmalı pencere köşesi yuvarlatma özelliği etkinleştirilmiştir.

### Soru: Bu uygulama Linux veya macOS işletim sistemlerinde çalışır mı?
**Cevap:** Hayır. Uygulamanın masaüstüne sabitleme ve gelişmiş arayüz özellikleri tamamen yerel Windows API'lerine bağlıdır, bu nedenle yalnızca Windows işletim sistemlerinde çalışır.

---

## 3. VERİ KAYNAKLARI VE SENKRONİZASYON (RSS & JSON)

### Soru: RSS modu ile Yerel JSON modu arasındaki fark nedir?
**Cevap:** **RSS Modu**, belirttiğiniz canlı web akışlarını dinler ve yeni bir söz eklendiğinde otomatik olarak güncellenir. **Yerel JSON Modu** ise bilgisayarınızdaki yerel bir `.json` dosyasını referans alır ve tanımladığınız saniye aralığında rastgele seçimler yaparak sürekli bir akış sağlar.

### Soru: RSS modunda sözlerin ne sıklıkla değişeceğini ayarlayabilir miyim?
**Cevap:** Hayır, arayüzdeki saniye ayarı yalnızca JSON modu için geçerlidir. RSS modu, kaynaktaki canlı güncellemeleri (yeni sözleri) arka planda sabit 2 saniyelik aralıklarla izler ve yalnızca yeni bir söz yayınlandığında güncellenir.

### Soru: "Gözat" (Browse) butonuna tıklayarak seçtiğim yerel JSON dosyası orijinal konumundan silinir mi?
**Cevap:** Hayır. Seçtiğiniz dosya güvenli bir şekilde uygulamanın veri alanına (`%appdata%/Mottoverse_Data/mottoverse.json`) kopyalanır ve uygulama çalışırken bu kopyalanan dosyayı referans alır. Orijinal dosyanıza dokunulmaz.

---

## 4. KULLANICI DENEYİMİ VE ARAYÜZ KONTROLLERİ

### Soru: Widget'ın konumunu kilitlemek ve yanlışlıkla taşınmasını önlemek mümkün mü?
**Cevap:** Evet. Widget üzerinde herhangi bir yere sağ tıklayıp "**📌 Pin**" seçeneğini seçtiğinizde arayüz kilitlenir. Kilitlendikten sonra köşelerdeki yeniden boyutlandırma tutamaçları (`◤` ve `◢`) gizlenir, widget sürüklenemez veya yeniden boyutlandırılamaz. Tekrar taşımak için sağ tıklayıp "**🔓 Unlock**" demeniz yeterlidir.

### Soru: Pencereyi fareyle yeniden boyutlandırdığımda metinler neden taşmıyor veya kesilmiyor?
**Cevap:** Uygulama dinamik bir metin kaydırma (`wraplength`) mimarisine sahiptir. Genişliği değiştirdiğinizde metnin satır sonu sınırı otomatik olarak güncellenir ve pencere yüksekliği içerik uzunluğuna bağlı olarak dinamik olarak genişler.

---

## 5. HATA YÖNETİMİ VE SORUN GİDERME

### Soru: Bir RSS adresi eklerken "Primary URL did not return a valid RSS feed" hatası alıyorum. Bu ne anlama geliyor?
**Cevap:** Uygulamanın bağlantıyı doğrulayabilmesi için girilen bağlantının standart XML formatında olması ve `<title>`, `<description>`, `<author>` yapılarının yanı sıra en az bir `<item>` veya `<entry>` etiketi içermesi gerekir.

### Soru: İnternet bağlantım koparsa veya RSS aldığım web sitesi çökerse widget kapanır mı?
**Cevap:** Hayır. Kod mimarisi yedekli RSS ve korumalı hata blokları (`try-except`) içerir. Birincil adrese ulaşılamazsa, tanımladığınız yedek adrese otomatik olarak geçiş yapar. Hiçbirine ulaşılamazsa uygulama çökmez; arka planda güvenle bekler ve internet bağlantısı geri geldiğinde akışı çekmeye devam eder.

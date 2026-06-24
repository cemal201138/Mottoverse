# 🌟 Mottoverse - Saatlik Rastgele Söz Akışı (Desktop Widget)

❗ [English README.md file](https://github.com/cemal201138/Mottoverse/blob/main/README-gb.md) ❗

Mottoverse, Windows masaüstünüze şık ve minimalist bir şekilde entegre olan, favori RSS akışlarınızdan anlık veya saatlik olarak motivasyon sözleri/alıntılar çeken modern bir Python masaüstü widget uygulamasıdır.

Windows'un yerel API'lerini kullanarak masaüstü katmanına sabitlenir, böylece pencereleri gizlediğinizde (`Win + D`) kaybolmaz ve arka planınızın şık bir parçası haline gelir.

---

## ✨ Özellikler

* **Masaüstüne Sabitleme (Pin to Desktop):** Windows API entegrasyonu sayesinde widget duvar kağıdınızın hemen üzerinde yer alır. Diğer pencereler üzerine gelebilir ancak `Win + D` kombinasyonunda gizlenmez.
* **Modern Tokyo Night Teması:** Gözü yormayan `#1a1b26` ve `#24283b` renk paletiyle modern, minimalist arayüz.
* **Dinamik Boyutlandırma:** İçeriğin uzunluğuna göre kendi yüksekliğini otomatik ayarlar (`wraplength` korumalı). Ayrıca sol-üst ve sağ-alt tutamaçlardan manuel olarak da boyutlandırılabilir.
* **Gelişmiş Windows Özellikleri:** Destekleyen Windows sürümlerinde donanımsal pencere köşe yumuşatması (DWM API).
* **Yedekli RSS Sistemi:** Birincil RSS kaynağınızda sorun oluşursa otomatik olarak yedek akışa geçiş yapar.
* **Kilitlenebilir Arayüz:** Yanlışlıkla yerini değiştirmemek için widget'ı masaüstünde kilitleyebilir, tutamaçları gizleyebilirsiniz.
* **Akıllı JSON Konfigürasyonu:** Kaydettiğiniz URL'ler otomatik olarak kullanıcının `AppData/Roaming/Rss_Soz` klasöründe saklanır, her açılışta tekrar girmeniz gerekmez.

---

## 🛠️ Kurulum ve Çalıştırma

### Gereksinimler
Uygulama yerleşik Python kütüphanelerini (`tkinter`, `urllib`, `xml`, `ctypes`) kullanır. Windows API'leri içerdiğinden **yalnızca Windows** işletim sistemlerinde tam performansla çalışır. Ekstra bir `pip install` kurulumuna **ihtiyaç yoktur**.

### Çalıştırma
1. Bu depoyu bilgisayarınıza indirin veya kopyalayın:
   ```bash
   git clone [https://github.com/KULLANICI_ADINIZ/mottoverse.git](https://github.com/KULLANICI_ADINIZ/mottoverse.git)
   cd mottoverse

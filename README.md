# 🌟 Mottoverse - Saatlik Rastgele Söz Akışı (Desktop Widget)

❗ [English README.md file](https://github.com/cemal201138/Mottoverse/blob/main/README-gb.md) ❗

Mottoverse, Windows masaüstünüze şık ve minimalist bir şekilde entegre olan, favori RSS akışlarınızdan anlık veya saatlik olarak motivasyon sözleri/alıntılar çeken modern bir Python masaüstü widget uygulamasıdır.

Windows'un yerel API'lerini kullanarak masaüstü katmanına sabitlenir, böylece pencereleri gizlediğinizde (Win + D) kaybolmaz ve arka planınızın şık bir parçası haline gelir.

---

## ✨ Özellikler

* **Masaüstüne Sabitleme (Pin to Desktop):** Windows API entegrasyonu sayesinde widget duvar kağıdınızın hemen üzerinde yer alır. Diğer pencereler üzerine gelebilir ancak Win + D kombinasyonunda gizlenmez.
* **Modern Tokyo Night Teması:** Gözü yormayan #1a1b26 ve #24283b renk paletiyle modern, minimalist arayüz.
* **Dinamik Boyutlandırma:** İçeriğin uzunluğuna göre kendi yüksekliğini otomatik ayarlar (wraplength korumalı). Ayrıca sol-üst ve sağ-alt tutamaçlardan manuel olarak da boyutlandırılabilir.
* **Gelişmiş Windows Özellikleri:** Destekleyen Windows sürümlerinde donanımsal pencere köşe yumuşatması (DWM API).
* **Yedekli RSS Sistemi:** Birincil RSS kaynağınızda sorun oluşursa otomatik olarak yedek akışa geçiş yapar.
* **Kilitlenebilir Arayüz:** Yanlışlıkla yerini değiştirmemek için widget'ı masaüstünde kilitleyebilir, tutamaçları gizleyebilirsiniz.
* **Akıllı JSON Konfigürasyonu:** Kaydettiğiniz URL'ler otomatik olarak kullanıcının AppData/Roaming/Mottoverse_Data klasöründe saklanır, her açılışta tekrar girmeniz gerekmez.

---

## 🛠️ Kurulum ve Çalıştırma

### Gereksinimler
Uygulama yerleşik Python kütüphanelerini (tkinter, urllib, xml, ctypes) kullanır. Windows API'leri içerdiğinden yalnızca Windows işletim sistemlerinde tam performansla çalışır. Ekstra bir pip install kurulumuna ihtiyaç yoktur.

### Çalıştırma
1. Deponun son versiyonunu indirin ve exe dosyasını çalıştırın.

2. Örnek RSS kaynakları ve yapısı için [rss-feed](https://github.com/cemal201138/rss-feed) reposunu inceleyebilirsiniz veya direk örneği kullanabilirsiniz.

3. Python ile scripti çalıştırın:
   python main.py

---

## 🚀 Kullanım Rehberi

1. **İlk Kurulum:** Uygulamayı ilk kez başlattığınızda karşınıza RSS Kaynak Ayarları penceresi çıkacaktır. Buraya doğrulanabilir, geçerli en az bir RSS Feed URL'si girmeniz gerekir.
2. **Widget Kontrolleri:**
   * **Taşıma:** Widget'ın herhangi bir yerine basılı tutarak masaüstünde istediğiniz yere sürükleyebilirsiniz.
   * **Boyutlandırma:** Köşelerdeki ◤ ve ◢ sembollerini kullanarak widget boyutunu değiştirebilirsiniz.
3. **Sağ Tık Menüsü:** Widget üzerine sağ tıklayarak şu ayarlara erişebilirsiniz:
   * 📌 Sabitle / 🔓 Kilidi Kaldır: Widget'ın taşınmasını ve boyutlandırılmasını engeller, ekrandaki yerini sabitler.
   * ⚙️ URL Ayarları: RSS akış linklerini güncellemek veya değiştirmek için ayar penceresini tekrar açar.
   * ❌ Kapat: Uygulamayı güvenli bir şekilde kapatır.

---

## 🎨 Ekran Görüntüleri

<img width="474" height="444" alt="Screenshot 2026-06-25 120429" src="https://github.com/user-attachments/assets/8402188a-1c91-428f-845c-9b3e3adc6092" />
<img width="472" height="440" alt="Screenshot 2026-06-25 120406" src="https://github.com/user-attachments/assets/9061bbf7-0194-4e58-98c9-443ead5bd0e4" />
<img width="291" height="177" alt="Screenshot 2026-06-25 120254" src="https://github.com/user-attachments/assets/d6eace68-7af3-480e-876b-c0526f069342" />
<img width="297" height="176" alt="Screenshot 2026-06-25 120451" src="https://github.com/user-attachments/assets/d06a1d9f-fa9a-4377-98b2-b7e39f929b6c" />
<img width="293" height="180" alt="Screenshot 2026-06-25 120652" src="https://github.com/user-attachments/assets/98fcad29-c873-4a2a-ab67-6096bcef9dc8" />

---

## 📝 Lisans

Bu proje MIT lisansı altında lisanslanmıştır. İstediğiniz gibi geliştirebilir, fork'layabilir ve kendi projelerinizde kullanabilirsiniz.

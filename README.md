# Güneş Sistemi Atlası

Güneş'i ve sekiz gezegeni üç boyutlu, etkileşimli olarak anlatan tek dosyalık bir eğitim sitesi. Bir bilim müzesindeki dokunmatik ekranda ya da evdeki bir tarayıcıda çalışacak şekilde tasarlandı. Tüm metinler Türkçedir.

**Çalıştırmak için** `index.html` dosyasını güncel bir tarayıcıda açmanız yeterli. Three.js ve yazı tipleri CDN'den yüklendiği için ilk açılışta internet bağlantısı gerekir.

## Neler var?

- **3B Güneş Sistemi.** Güneş ve sekiz gezegen, JPL'nin yaklaşık yörünge elemanlarıyla seçilen tarihteki **gerçek konumlarında** gösterilir. Yörüngeler gerçek eksantriklik ve eğiklikleriyle çizilir; gezegenler gerçek eksen eğiklikleri, basıklıkları ve dönüş yönleriyle (Venüs ve Uranüs ters yönde) kendi eksenleri etrafında döner. Satürn'ün halkaları (Cassini aralığı, Encke boşluğu, F halkası) ile Jüpiter, Uranüs ve Neptün'ün soluk halkaları vardır. Arka planda 5.044 gerçek yıldız ve Samanyolu bulunur.
- **Gezegen seçimi.** Bir gezegene, etiketine ya da alttaki şeritteki küçük resmine tıklayınca kamera yumuşak bir uçuşla gezegene yaklaşır ve bilgi kartı açılır. Kartta çap, Güneş'e uzaklık, bir günün ve bir yılın uzunluğu, uydu sayısı, sıcaklık, eksen eğikliği, yüzey çekimi, Dünya ile boyut kıyası, üç ilginç bilgi ve canlı güncellenen uzaklıklar yer alır.
- **Prosedürel yüzeyler.** Hiçbir görsel ya da doku dosyası kullanılmaz. Yüzeyler açılışta GPU'da gölgelendiricilerle üretilir: Dünya'nın kıtaları, okyanus sığlıkları, çölleri, buzulları, bulutları, kasırgaları ve gece tarafındaki şehir ışıkları; Jüpiter'in kuşakları ve Büyük Kırmızı Leke; Mars'ın kutup başlıkları, Olympus Mons ve Valles Marineris; Merkür ile Ay'ın kraterleri; Satürn'ün kutup altıgeni; Neptün'ün karanlık lekesi.
- **Kontrol paneli.** Yörünge hızı kaydırıcısı (1 saniyede 1 saatten 4 aya kadar), duraklat/başlat, tarihi bugüne alma, yörünge çizgileri ve gezegen isimleri için aç/kapa düğmeleri.
- **Karşılaştırma modu.** Gezegenler çaplarıyla orantılı olarak yan yana dizilir; kenardaki dev yay Güneş'tir. Her gezegen gerçek eksen eğikliğiyle gösterilir.
- **Mini test.** 17 soruluk havuzdan rastgele seçilen 5 soru, her cevaptan sonra açıklama ve kameranın ilgili gezegene uçuşu, sonunda puan ve özet.

## Kullanım

| Hareket | Sonuç |
| --- | --- |
| Sürükle | Sahneyi döndür (Karşılaştır modunda yana kaydır) |
| Tekerlek · iki parmak | Yakınlaştır, uzaklaştır |
| Tıkla · dokun | Gök cismini seç |
| Boşluk | Animasyonu durdur ya da başlat |
| ← → | Bilgi kartında önceki ya da sonraki gök cismi |
| 0–8 | Güneş'e ve gezegenlere hızlı geçiş |
| Esc | Genel görünüme dön |

Görüntü kalitesi cihaza göre otomatik seçilir. İsterseniz adres satırına `?kalite=low`, `?kalite=mobile` ya da `?kalite=desktop` ekleyerek elle seçebilirsiniz. Çalışma sırasında kare hızı düşerse çözünürlük kendiliğinden azaltılır.

## Ölçek ve doğruluk notları

- Keşif görünümünde uzaklıklar ve boyutlar ekrana sığması için sıkıştırılmıştır (gezegen yarıçapları karekök ölçeğinde). Yörüngelerin sırası, biçimi ve yönü gerçektir. Gerçek boyut oranları Karşılaştır modunda gösterilir.
- Hızlı zaman akışında gezegenlerin kendi eksenleri etrafındaki dönüşü, titreme olmaması için görsel olarak yavaşlatılır. Yörünge hareketleri her hızda gerçek oranlarındadır.
- Açılışta Dünya'nın gece ve gündüz tarafları, Ay'ın konumu ve evresi gerçek zamana göre ayarlanır.
- Uydu sayıları 2025 itibarıyla doğrulanmış keşiflere göredir ve yeni keşiflerle değişebilir.

## Veri kaynakları

- Gezegen konumları: NASA JPL, *Approximate Positions of the Planets* (1800–2050 için yörünge elemanları).
- Fiziksel veriler: NASA gezegen bilgi sayfaları (Planetary Fact Sheet).
- Kutup yönelimleri: IAU WGCCRE raporları.
- Dünya kıyı çizgileri: [Natural Earth](https://www.naturalearthdata.com/) 1:50m kara verisi (kamu malı). HTML içine sıkıştırılmış bir kara/deniz maskesi olarak gömülüdür; renkler, dağlar, bulutlar ve ışıklar bu maskeden kodla üretilir.
- Yıldızlar: Hipparcos kataloğundaki 6. kadire kadar olan yıldızların konum, parlaklık ve renkleri ([d3-celestial](https://github.com/ofrohn/d3-celestial) veri dosyasından, BSD-3 lisansı).

## Teknik

- Tek dosya: `index.html` (HTML, CSS ve JavaScript bir arada, yaklaşık 230 KB).
- [Three.js](https://threejs.org/) r170, jsDelivr üzerinden ES modülü olarak yüklenir.
- WebGL 2 gerektirir (güncel Chrome, Edge, Firefox ve Safari; iOS 15 ve sonrası).

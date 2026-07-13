# Ergines Balsamik Takip — Telefona Kurulum

Bu klasördeki dosyalar hazır bir **PWA** (telefona kurulabilen web uygulaması). İnternet olmadan da çalışır, veriler telefonunda saklanır, hiçbir sunucuya gitmez.

## 1. Dosyaları bir yere yükle (bir kere yapılır)

Telefonun tarayıcısının bu dosyaları **https ile** açması gerekiyor (yerel dosya olarak açarsan kurulum ve offline özellikler çalışmaz). En kolay yol GitHub Pages:

1. GitHub'da yeni bir repo aç (örn. `balsamik-takip`) — daha önce `Ba-y-netimi-` reposunu açtığın hesaptan (`timurtosun94-alt`) devam edebilirsin.
2. Bu klasördeki tüm dosyaları ve klasörleri (`index.html`, `manifest.json`, `sw.js`, `icons/`, `lib/`) reponun kök dizinine yükle. `lib/` klasörü QR/barkod okuma ve PDF rapor üretimi için gerekli kütüphaneleri içerir — atlarsan o özellikler çalışmaz.
3. Repo **Settings → Pages** → Source: `main` branch, `/ (root)` → Save.
4. Birkaç dakika sonra `https://timurtosun94-alt.github.io/balsamik-takip/` adresi aktif olur.

## 2. Telefona kur

**Android (Chrome):**
1. Yukarıdaki linki Chrome'da aç.
2. Sağ üstteki ⋮ menüsüne dokun.
3. **"Ana ekrana ekle"** / **"Uygulama yükle"** seçeneğine dokun.
4. Onayla — artık ana ekranda gerçek bir uygulama gibi ikonu olacak.

**iPhone (Safari):**
1. Linki Safari'de aç (Chrome'da değil — iOS'ta kurulum sadece Safari'den çalışır).
2. Alttaki **Paylaş** ikonuna (kare + ok) dokun.
3. **"Ana Ekrana Ekle"**yi seç.
4. Onayla.

Kurulumdan sonra tarayıcı arayüzü olmadan, tam ekran, kendi ikonuyla açılır.

## 3. Kullanım (özet — ayrıntılar için docs/Kullanim-Kilavuzu.md)

- Alt menüden bir aşama seç (Hasat, Yoğunlaştırma, Fermantasyon, Fıçı, Kalite, Şişele).
- "➕ Yeni Kayıt" ile formu doldur, kaydet.
- Parti No / Fıçı No alanları, önceki aşamada girdiğin kayıtlardan otomatik listelenir — elle yazmana gerek yok, istersen kartlardaki ▦ ikonuyla o kaydın QR kodunu oluşturup 📷 butonuyla sonraki formlarda kamerayla tarayabilirsin.
- "📊 Özet" sekmesinde toplam parti, aktif fermantasyon, fıçıda bekleyen, stoktaki şişe sayısı, otomatik hatırlatmalar ve grafikler var.
- "⚙️ Ayarlar"dan rolünü seçebilir, PDF rapor oluşturabilir, verilerini JSON olarak yedekleyebilirsin.

## 4. Kamera İzni

QR tarama özelliği için tarayıcı kamera izni isteyecek — izin vermen gerekiyor. Kamera yalnızca https bağlantısında çalışır (bu yüzden 1. adımdaki barındırma şart).

## Belgeler

`docs/` klasöründe dört doküman var: **Kullanim-Kilavuzu.md** (ekran ekran kullanım), **Formul-Rehberi.md** (tüm hesaplama ve eşik değerleri), **SSS.md** (sık sorulan sorular), **Guncelleme-Notlari.md** (sürüm geçmişi).

## Önemli

- Veriler **sadece bu telefonda**, tarayıcının yerel deposunda tutulur. Telefonu değiştirirsen veya tarayıcı verilerini temizlersen, önce Ayarlar'dan yedek almadıysan veriler kaybolur.
- Birden fazla kişi/cihazdan ortak kullanmak istersen (ör. bulut senkronizasyonu), bu basit sürüm buna uygun değil — istersen bir sonraki adımda Firebase gibi bir bulut veritabanı ekleyebiliriz (daha önce Bağ Yönetimi uygulaman için de konuşulmuştu).

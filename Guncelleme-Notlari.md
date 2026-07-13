# Güncelleme Notları — Ergines Balsamik Takip

## v2.0 (bu sürüm)
Eklenenler:
- 📷 **QR kod ile barkod okuma**: Parti No / Fıçı No alanlarını kamerayla tarayarak doldurma
- ▦ **QR kod üretme**: her Hasat ve Fıçı kaydı için indirilebilir/yazdırılabilir QR kod
- 🔔 **Otomatik hatırlatmalar**: tadım zamanı (90 gün), aktarım zamanı (730 gün), düşük stok (<50 şişe), yedek alma hatırlatması (7 gün) — uygulama açıldığında Özet ekranında gösterilir
- 👤 **Rol filtresi**: Admin / Üretici / Tadım Uzmanı / Satış rolüne göre sekme görünürlüğü
- 📄 **PDF raporları**: Kalite Kontrol Raporu ve Üretim Özeti Raporu, cihazda oluşturulup indirilir
- 📈 **Grafikler**: Brix değişim çizgi grafiği, seri dağılımı pasta grafiği
- 🔄 **Otomatik yerel yedekleme**: her kayıt işleminde son 3 durumun cihazda saklanması ve geri yüklenebilmesi
- 🎨 Ayrı marka logosu (üzüm yaprağı + nehir silüeti)
- 📚 Tam dokümantasyon seti (Kullanım Kılavuzu, Formül Rehberi, SSS, bu dosya)
- Olgunlaştırma formuna "Son Aktarım Tarihi" alanı eklendi (aktarım hatırlatması için)

Bilinen sınırlar (sunucusuz, tek cihaz mimarisi gereği):
- Roller gerçek bir giriş/şifre sistemi değil, yalnızca ekran filtresi
- Hatırlatmalar yalnızca uygulama açıkken görünür, arka planda push bildirimi yok
- Veriler cihazlar arası otomatik senkronize olmaz; taşımak için elle JSON yedek gerekir

## v1.0
- İlk sürüm: 6 aşamalı üretim takibi (Hasat, Yoğunlaştırma, Fermantasyon, Olgunlaştırma, Kalite Kontrol, Şişeleme)
- Özet ekranı (4 kart)
- Elle JSON yedek alma/yükleme
- Telefona kurulabilir PWA (Android/iOS ana ekrana ekleme)

# Kullanım Kılavuzu — Ergines Balsamik Takip

## Genel Ekran Yapısı
Uygulama alt menüden 8 sekmeye ayrılır: **Özet, Hasat, Yoğunlaştırma, Fermantasyon, Fıçı (Olgunlaştırma), Kalite, Şişele, Ayarlar**. Aktif rolüne göre (bkz. Roller) bazı sekmeler gizlenebilir.

## 1. Yeni Kayıt Ekleme
1. Alt menüden ilgili aşamayı seç.
2. "➕ Yeni [Aşama] Kaydı" butonuna dokun.
3. Formu doldur. Parti No / Fıçı No gibi alanlar **ref** tipindedir: önceki aşamada girilen kayıtlardan bir açılır listeden seçilir.
4. Sağdaki 📷 ikonuna dokunarak, elle seçmek yerine bir önceki aşamada bastığın **QR kodu kamerayla tarayarak** da otomatik doldurabilirsin.
5. "Kaydet"e dokun.

## 2. QR Kod Oluşturma ve Tarama
- Her **Hasat** kaydının kartında ▦ ikonuna dokunarak o partiye ait QR kodu görebilir, PNG olarak indirip yazdırıp kasa/kaba yapıştırabilirsin (`PARTI-2026-001` gibi kodlanır).
- Her **Fıçı** kaydında aynı şekilde `FICI-F-001` formatında QR kod üretilir.
- Sonraki aşamalarda (Yoğunlaştırma, Fermantasyon, Kalite, Şişeleme) formdaki 📷 butonuna basıp bu QR'ı telefon kamerasına gösterdiğinde ilgili Parti/Fıçı otomatik seçilir.
- Kamera erişimi için tarayıcı izin isteyecektir — izin vermen gerekir. Kamera yalnızca **https** bağlantısında çalışır (yerel dosya olarak açarsan çalışmaz).

## 3. Özet Ekranı
- 4 özet kart: Toplam Parti, Aktif Fermantasyon, Fıçıda Bekleyen, Stokta Şişe.
- **🔔 Hatırlatmalar**: tadım zamanı gelen fıçılar, aktarım zamanı gelen fıçılar, azalan stok, yedek alma hatırlatması otomatik burada listelenir (bkz. Formül Rehberi).
- **📈 Brix Değişimi**: hasat kayıtlarındaki Brix değerlerinin tarihe göre çizgi grafiği.
- **🥧 Seri Dağılımı**: stokta olan şişelerin Classic/Premium/Reserve dağılımı.
- **📋 Son Kayıtlar**: tüm aşamalardan en son eklenen kayıtlar.

## 4. Roller (Ayarlar > Aktif Rol)
| Rol | Görebildiği Sekmeler |
|---|---|
| Admin | Tümü |
| Üretici | Özet, Hasat, Yoğunlaştırma, Fermantasyon, Fıçı |
| Tadım Uzmanı | Özet, Kalite |
| Satış | Özet, Şişele |

Bu bir **ekran filtresi**dir, şifre/güvenlik değildir — aynı cihazda herkes rolünü değiştirip her şeyi görebilir. Amaç, günlük kullanımda ilgisiz sekmelerin gözü yormamasıdır.

## 5. PDF Raporları (Ayarlar)
- **Kalite Kontrol Raporu**: tüm tadım kayıtlarını tarih sırasıyla PDF'e döker.
- **Üretim Özeti Raporu**: özet sayılar + tüm fıçılar + stok listesini PDF'e döker.
İkisi de cihazında oluşturulur, indirilir; paylaşmak istersen normal PDF paylaşma yollarını (Mail, WhatsApp vb.) kullanabilirsin.

## 6. Yedekleme
- **Elle yedek (Export/Import)**: Ayarlar'dan JSON dosyası indir/yükle — telefon değiştirirken veya arıza durumunda bunu kullan.
- **Otomatik yedek**: Her kayıt eklemesinde, uygulama cihazda otomatik olarak son 3 durumu saklar. Yanlışlıkla veri sildiysen "Otomatik Yedekler > Geri Yükle" ile kurtarabilirsin. Bu **telefon değişiminde işe yaramaz** — sadece aynı cihaz/tarayıcı için bir güvenlik ağıdır.
- Uygulama 7 günden fazla elle yedek almadıysan Özet ekranında hatırlatma gösterir.

## 7. Veri Nerede Saklanıyor?
Tüm veriler yalnızca bu telefonun tarayıcı deposunda (localStorage) tutulur. Başka bir cihazdan görülemez, herhangi bir sunucuya gönderilmez. Bu hem gizlilik açısından iyi hem de bir risktir: **düzenli yedek almazsan** (yukarıki madde) veri kaybı kalıcı olabilir.

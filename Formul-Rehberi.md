# Formül Rehberi — Ergines Balsamik Takip

Uygulamadaki tüm otomatik hesaplamalar ve eşik değerleri aşağıda listelenmiştir. Değerleri değiştirmek istersen (ör. tadım aralığını 90 yerine 60 gün yapmak), `index.html` dosyasının başındaki sabitleri düzenlemen yeterli.

## Özet Kartları
| Kart | Hesaplama |
|---|---|
| Toplam Parti | Hasat kayıtlarının sayısı |
| Aktif Fermantasyon | Fermantasyon_Tipi = "Alkol" olan kayıt sayısı |
| Fıçıda Bekleyen | Olgunlaştırma (fıçı) kayıtlarının sayısı |
| Stokta Şişe | Stok_Durumu = "Stokta" olan şişeleme kayıtlarındaki Şişe Sayısı toplamı |

## Hatırlatma Eşikleri (kaynak kodda `const` olarak tanımlı)
| Hatırlatma | Eşik | Hesaplama mantığı |
|---|---|---|
| Tadım zamanı | 90 gün (`TADIM_INTERVAL_DAYS`) | O fıçı için en son Kalite Kontrol tarihinden (yoksa Dolum Tarihi'nden) bugüne kadar geçen gün ≥ 90 ise uyarı |
| Aktarım zamanı | 730 gün (`AKTARIM_INTERVAL_DAYS`) | Son Aktarım Tarihi'nden (girilmemişse Dolum Tarihi'nden) bugüne kadar geçen gün ≥ 730 ise uyarı |
| Düşük stok | 50 şişe (`LOW_STOCK_THRESHOLD`) | Seri bazında (Classic/Premium/Reserve) stokta toplam şişe sayısı bu eşiğin altındaysa uyarı |
| Yedek hatırlatma | 7 gün | Son "Yedek Al" işleminden bu yana geçen gün ≥ 7 ise uyarı |

## QR Kod Formatı
- Hasat kaydı → `PARTI-<Parti_No>` (örn. `PARTI-2026-001`)
- Fıçı kaydı → `FICI-<Fıçı_No>` (örn. `FICI-F-001`)
Tarama sırasında bu önek otomatik ayıklanır ve ilgili forma yazılır.

## Kalite Sınıfı (öneri — uygulamada otomatik atanmıyor)
Orijinal AppSheet tasarımındaki formül referans olarak: Tadım Puanı ≥ 8 → Reserve, ≥ 6 → Premium, altı → Classic. Bu sürümde Kalite Kontrol formunda "Onay" alanı elle seçiliyor; istersen bu formülü otomatik atama olarak da ekleyebiliriz.

## Grafikler
- **Brix Değişimi**: Hasat kayıtlarındaki (Tarih, Brix) çiftleri, tarihe göre sıralanıp çizgi grafiğe dökülür.
- **Seri Dağılımı**: Stokta olan şişeleme kayıtları Seri'ye göre gruplanıp toplam adet üzerinden pasta grafiğe dökülür.

## Birim Etiketleri (kart görünümünde otomatik eklenir)
`agirlik_kg → kg`, `sira_miktari_l → L`, `sicaklik → °C`, `miktar_l → L`, `fiyat_tl → TL`, `hedef_sure_ay → ay`, `adet → adet`, `hacim_ml → ml`

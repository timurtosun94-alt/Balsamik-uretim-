# Sık Sorulan Sorular (SSS) — Ergines Balsamik Takip

**Kamera açılmıyor / "Kameraya erişilemedi" hatası alıyorum.**
Kamera yalnızca https bağlantısında çalışır. Uygulamayı dosya olarak (file://) açtıysan veya GitHub Pages yerine yerel bir kopyadan çalıştırıyorsan bu hata beklenir. Ayrıca tarayıcının kamera iznini reddetmiş olabilirsin — telefon Ayarlar > Uygulamalar > [Tarayıcı] > İzinler'den Kamera'yı kontrol et.

**QR kodu okutuyorum ama "listede bulunamadı" diyor.**
QR kod, ilgili Parti/Fıçı No'nun **daha önce o aşamada bir kayıt olarak girilmiş olmasını** varsayar. Örn. Yoğunlaştırma formunda bir Parti No'yu tarayabilmen için o Parti No'nun önce Hasat sekmesinde kayıtlı olması gerekir.

**Verilerim bir anda kayboldu.**
Ayarlar > Otomatik Yedekler'den son 3 durumdan birini geri yükleyebilirsin. Bu sadece aynı cihaz/tarayıcıda işe yarar. Tarayıcı geçmişini/verilerini temizlediysen veya farklı bir tarayıcı/telefon kullanıyorsan otomatik yedek de kaybolmuş olabilir — bu yüzden elle "Yedek Al" ile ayrıca JSON indirmen önerilir.

**Telefon değiştirdim, verilerimi nasıl taşırım?**
Eski telefonda Ayarlar > Yedek Al ile JSON dosyasını indir, yeni telefona aktar (mail, bulut depolama, kablo vb.), yeni telefonda uygulamayı açıp Ayarlar > Yedekten Yükle ile o dosyayı seç.

**Birden fazla kişi aynı verileri görebilir mi?**
Hayır — bu sürüm tamamen cihaz-içi çalışır, ortak/bulut veritabanı yok. Birden fazla kişinin aynı veriyi görmesi/düzenlemesi gerekiyorsa (ör. tadım uzmanı ile üretici farklı telefonlarda), her biri kendi telefonunda ayrı veri tutar ve senkronize olmaz. Bunu istiyorsan bir sonraki adımda bulut senkronizasyonu (ör. Firebase) eklenebilir.

**Roller gerçekten güvenlik sağlıyor mu?**
Hayır. Ayarlar'dan rolü herkes değiştirebilir; bu sadece hangi sekmelerin görüneceğini belirleyen bir kolaylık ayarıdır, şifre veya erişim kısıtlaması değildir.

**PDF raporu oluşturmuyor / boş çıkıyor.**
İlgili aşamada (Kalite Kontrol veya genel veriler) hiç kayıt yoksa rapor da neredeyse boş olur. Önce birkaç kayıt gir, sonra raporu tekrar oluştur.

**Uygulama internetsizken çalışıyor mu?**
Evet, ilk açılışta (internet varken) bir kere yüklendikten sonra tüm ekranlar ve kamera/QR/PDF özellikleri internetsiz çalışır. Servis çalışanı (service worker) gerekli dosyaları cihazda önbelleğe alır.

**Bildirimler (push notification) geliyor mu, uygulama kapalıyken de hatırlatma alır mıyım?**
Hayır. Hatırlatmalar yalnızca **uygulamayı açtığında** Özet ekranında görünür. Telefon kilitliyken veya uygulama kapalıyken bildirim göndermek bir arka uç (sunucu) gerektirir; bu basit, sunucusuz sürümde yok.

**Barkod okuma dediğimde ne kastediliyor — gerçek barkod (Code128 vb.) mu, QR mu?**
Uygulama QR kod üretir ve okur (kamera ile). Klasik çizgisel barkodlar (Code128/EAN) değil, kare QR kodları kullanılıyor — telefon kamerasıyla okumak için QR daha güvenilir ve kolay.

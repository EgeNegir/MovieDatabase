# 🎬 MovieDatabase: PostgreSQL Film ve Kullanıcı Etkileşim Sistemi

Bu proje, bir sosyal film platformu (Letterboxd benzeri) için tasarlanmış kapsamlı bir ilişkisel veritabanı yönetim sistemidir. Kullanıcı etkileşimi, film analizi ve otomatik veri yönetimi üzerine odaklanmıştır.

## 🚀 Öne Çıkan Teknik Özellikler

* **Gelişmiş Öneri Mantığı:** Kullanıcının en çok izlediği türe göre henüz izlemediği filmleri öneren `film_oner_favori_ture_gore` gibi PL/pgSQL fonksiyonları içerir.
* **Veri Bütünlüğü ve Otomasyon:** * `spam_engelleme`: Kullanıcıların aynı filme birden fazla yorum yapmasını engelleyen bir tetikleyici (trigger).
    * `clean_user_data`: Kayıt sırasında kullanıcı adlarını ve e-postalarını otomatik olarak formatlar.
* **Analitik Görünümler (Views):** * `yonetmen_karnesi`: Yönetmen performansını ve ortalama puanlarını takip eder.
    * `pasif_kullanici_alarmi`: Platformla 90 günden fazla etkileşime girmeyen kullanıcıları tespit eder.

## 🛠️ Veritabanı Şeması

Şema, normalizasyon ve performans kriterlerine göre oluşturulmuştur:
- **Temel Varlıklar:** `film`, `actor` (aktör), `director` (yönetmen), `genre` (tür), `language` (dil).
- **Kullanıcı Sistemi:** `user_account`, `subscriber` (Standart, Gold, Premium üyelik tipleri) ve `guest_user` (ziyaretçi).
- **Etkileşimler:** `review` (1-10 arası puan doğrulama sistemli yorumlar) ve `watch_history` (izleme geçmişi).


Bu proje, veritabanı şemasını, verileri ve fonksiyonları korumak amacıyla PostgreSQL Backup (yedek) formatında (.sql) yüklenmiştir.
Görüntülemek veya çaılştırmak için dosyayı indirmeniz gerekir.

# Devir notu: veri hikâyeleri sitesi (çalışma adı "16 Milyon")

Bu not, projeyi yeni bir sohbette sürdürmek için yazıldı. Yeni sohbete bu dosyayı (ya da tüm klasörü) ekleyin ve "HANDOFF.md'yi oku, kaldığımız yerden devam edelim" deyin.

## Proje
Prof. Dr. İbrahim Efe'nin İstanbul ve Türkiye'deki insanlarla ilgili verileri, Alvin Chang (The Pudding) tarzında etkileşimli, kaydırmalı hikâyelere dönüştüren sitesi. Temel mekanik: okur önce tahmin eder, sonra kayıtlarla karşılaştırır.

## Klasör yapısı
- `index.html`: ana sayfa (nokta alanı + büyük nüfus sayısı, hikâye kartları, "Nasıl çalışıyor").
- `kac-suriyeli/index.html`: ilk hikâye, "İstanbul'da her 100 kişiden kaçı Suriyeli?" (kaydırmalı canvas, tahmin kaydırıcısı, 81 il şeridi).
- `src/kac-suriyeli.template.html`: hikâyenin şablonu; `__ILLER__` yer tutucusu il verisiyle değiştirilerek `kac-suriyeli/index.html` üretilir.
- `src/anasayfa.artifact.html`: ana sayfanın önizleme (artifact) sürümü.
- `data/gecici-koruma-il-2026-10-15.csv`: GİB il tablosu (15.10.2026), sütunlar `sira,il,kayitli_suriyeli,il_nufusu,toplam,oran_yuzde`; aritmetik olarak doğrulandı.
- `.htaccess`: `src/`, `data/`, md dosyaları ve `.git` dışarıdan erişilemez.

## Veri notları
- Türkiye: 2.201.105 kayıtlı Suriyeli / 88.293.273 (%2,49). İstanbul: 387.513 / 16.141.566 (%2,40).
- GİB tablosundaki "il nüfusu" sütunu TÜİK ADNKS 2025 rakamıdır (Türkiye toplamı 86.092.168); "toplam" sütunu buna Suriyelileri ekler.
- Ana sayfadaki büyük sayı TÜİK rakamıdır: İstanbul 15.754.053. Ana sayfada kaynak gösterilmiyor (kullanıcı kararı); kaynaklar hikâye sayfalarında.

## Tasarım dili
- Renkler: zemin #ECEFF3, mürekkep #0F1626, tahmin turuncu #FF6B1A, kayıt mavi #2445F0, gri nokta #C2C9D3; koyu tema karşılıkları dosyalarda.
- Yazı tipleri: Bricolage Grotesque (başlık), Hanken Grotesk (metin).
- Motif: noktalar; her noktanın kaç kişi olduğu her zaman söylenir.

## Çalışma kuralları (kullanıcının tercihleri)
- Resmî ve kısa yanıtlar, Türkçe.
- Kod öncesi öneri ve taslak; onay gelmeden kod yazılmaz.
- Commit sonuna şu satırlar eklenir: `Co-Authored-By: Claude <noreply@anthropic.com>`.

## Yayın planı
- Yeni bir GitHub deposu (ör. brahimefe/16milyon) ve Hostinger'da yeni alan adı.
- antefilm'deki gibi: Hostinger panelinde Git → "Deploy from GitHub", kök `public_html`; main dalına her push otomatik yayına çıkar. Claude GitHub App'in yeni depoya da erişimi olmalı.

## Açık işler
1. Sitenin adı ve alan adı (adaylar: 16 Milyon, Kalabalık, Tahmin Et, Her Nokta Bir İnsan).
2. Sayfalardaki "Taslak" rozetleri yayından önce kaldırılacak mı?
3. Suriyeli hikâyesi için kullanıcıdan beklenen veriler: GİB 2011'den bugüne yıllık seri, ikamet izinleri (il bazında), yakalanan düzensiz göçmenler (yıllık).
4. Okur tahminlerinin anonim saklanması (Hostinger PHP + MySQL).
5. İngilizce sürüm.
6. Hikâye sayfasına ana sayfaya dönüş bağlantısı.
7. "Yakında" kartlarındaki konular (Boğaz geçişleri, İstanbul'un bir günü, bebek isimleri) yer tutucudur.

# Başvuru Metin Blokları (Yapıştırmaya Hazır)

## Proje Amacı (100–200)
Yazılım teslimatında yapay zekâ destekli çıktıların izlenebilir, kanıtlı ve denetlenebilir olması için bir yönetişim katmanı sağlamak. Sentinel, RAG tabanlı cevapların hangi veriler, araç çağrıları ve politikalarla üretildiğini kayıt altına alarak güvenli ve tekrarlanabilir sonuçlar sunmayı hedefler.

## Proje Açıklaması (300–500)
Güncel yazılım ekipleri kod inceleme, dokümantasyon ve olay yönetimi için LLM destekli asistanlar kullanıyor; ancak hangi verinin kullanıldığı ve risklerin nasıl kontrol edildiği belirsiz kalıyor. Sentinel, RAG iş akışlarını ajan tabanlı bir orkestrasyonla yönetir: kaynakları politikalı bir şekilde çeker, gerekli araç çağrılarını yapar, politika kontrollerini uygular ve sonuçta kanıt paketleri üretir. Bu paketler, hangi dosyaların okunduğu, hangi araçların çalıştığı ve hangi politikaların geçtiğini gösterir. Çözüm, SCM, biletleme ve CI log’ları gibi mevcut sistemlere uyumlu, konfigürasyonla yönlendirilen adaptörler üzerinden çalışır. Erken aşamada amaç; minimal kurulumla riskli kod değişikliklerini özetleyip, eksik kanıtları işaretlemek ve insan onayını kolaylaştırmaktır.

## Özgünlük (200–300)
Sentinel, RAG cevabının her adımını kanıt paketine bağlayan yönetişim odaklı bir tasarım sunar. Çoğu çözüm sadece yanıt üretir; Sentinel ise veri erişimi, araç çıktıları ve politika değerlendirmelerini aynı iz üzerinde birleştirerek denetlenebilirlik sağlar. Bağımsız çalışır, marka veya platform bağımlılığı oluşturmaz ve kuruma ait verilerin dışarı çıkmasını engelleyecek şekilde kapalı devre modda kurgulanır.

## Etki ve Sürdürülebilirlik (200–300)
Beklenen etki; kod değişikliklerinin risk özetlerinin doğrulanma süresini kısaltmak, politikaya uyumsuz cevapları erken yakalamak ve tekrar üretilebilir yanıtlarla güven kazanmak. Sürdürülebilirlik için dokümantasyon-öncelikli bir yaklaşım, modüler adaptörler ve ölçülebilir metrikler (kanıtlı yanıt oranı, onay süresi, kaçak veri olayları) kullanılır. Kurulum maliyeti düşük tutulur; genişletme için yeni veri kaynakları ve politikalar konfigürasyonla eklenebilir.

## Proje Pazar Araştırması (200–300)
Kurumsal geliştirici araçları pazarı; güvenli AI kullanımına odaklanan çözümler (kod asistanları, DLP, güvenlik tarayıcıları) ile büyüyor. Mevcut ürünler yanıt kalitesine odaklanırken, denetlenebilir kanıt üretimi sınırlı. Sentinel, denetlenebilirlik ve politika uyumu boşluğunu hedefler. İlk alıcı profili; regülasyon baskısı yüksek sektörlerdeki (finans, telekom, enerji) yazılım ekipleri. Pilotlardan gelen geribildirimler, entegrasyon kolaylığı ve kanıt kalitesine göre iterasyon sağlar.

## Ticari Potansiyel (200–300)
Hedef; lisans bazlı kurulum ve yıllık bakım modelleriyle kurumsal satış. Kısa vadede danışmanlıkla birlikte paketlenmiş PoC’lar; orta vadede self-hosted dağıtımlar. Fiyatlama; kullanıcı/entegrasyon başına katmanlı, kanıt paketi hacmine göre ayarlanabilir. Mevzuat uyumu ve denetlenebilirlik değer önerisi sayesinde güvenlik ve kalite bütçelerinden pay almayı hedefler.

## Teknik Yöntem ve Uygulanabilirlik (200–300)
Mimari; orkestratör, güvenli veri çekirdekleyici, araç katmanı, politika değerlendirme bileşeni ve kanıt paketleyiciden oluşur. Her adım izlenebilir log’lar üretir. Konfigürasyonla seçilen adaptörler (SCM, biletleme, CI log’ları) kullanılır; hassas veriler ortam dışına çıkmaz. İlk sürüm, hafif politikalar ve sınırlı araç çağrılarıyla kanıtlanabilir bir demo sağlar. Genişleme; yeni kaynak ve politikaların eklenmesiyle yapılır. Altyapı; konteyner tabanlı, gerektiğinde havuzlanmış GPU/CPU kaynaklarını kullanır, fakat minimal donanımda da çalışabilir.

## Proje Yönetimi (200–300)
Yaklaşım; belgelerle başlayan, küçük teslimatları olan iteratif sprintler. Rol kırılımı: ürün (gereksinim ve sınırlar), teknik lider (mimari ve güvenlik), uygulama ekibi (adaptörler ve politika kuralları), QA (kanıt paket doğrulama). Haftalık demo ve retro döngüsüyle ilerlenir; riskler ve mitigasyonlar kanıt paketlerinden izlenir.

## Pilot Uygulamalar
- Kod inceleme desteği: PR bazlı risk özeti, gerekli test/denetim listeleri.
- Runbook asistanı: olay yanıtında kanıtlara dayalı adım önerileri.
- Gereksinim doğrulama: doküman/issue tabanlı kanıtlı cevap üretimi.

## Ekler
- Demo Senaryosu: PR-123 örneği için kanıtlı risk özeti ve onay akışı.
- Değerlendirme Metrikleri: kanıtlı yanıt oranı, insan onay süresi, kaçak veri ihlali sayısı, politika uyum puanı.

## Demo Senaryosu (Kısa)
“PR-123 için risk ve etkilenen bileşenleri özetle; gerekli test ve kontrolleri listele.” Sentinel, PR diff ve ilgili biletlerden veri toplar, hafif statik analiz çalıştırır, politika kontrolü yapar ve kanıt paketini sunar. Eksik kanıt varsa yanıtı işaretler.

## Değerlendirme Metrikleri (Kısa)
- Kanıtlı yanıt oranı (%)
- İlk onay süresi (dakika)
- Eksik kanıt uyarısı sayısı
- Politika uyum puanı (0–100)

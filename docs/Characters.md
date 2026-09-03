# Character Database & System Requirements

Bu doküman, oyundaki NPC (Non-Playable Character) varlıklarını, sistem içi fonksiyonlarını, veri haritalamalarını (data mapping) ve hikaye tetikleyicilerini tanımlayan temel yazılım gereksinim belgesidir. 

---

## 1. Core Entities (Tanımlanmış Sistem Objeleri)
Oyunun temel döngüsüne (core loop) entegre edilmiş, iş kuralları ve durum makineleri (state machine) netleşmiş ana karakterler.

### The Mayor (Muhtar)
![The Mayor Design](./../assets/Character_sheet1.gif)
* **Sistem Fonksiyonu (Day Phase):** Ana görev (Quest) ağacı yöneticisi. Çiftlik alanını genişletme ve yeni bölgelerin kilidini açma işlemlerini onaylar.
* **Tetikleyici Zafiyet (Night Phase):** Kontrol Takıntısı ve Anksiyete.
* **Data Mapping (Gece İzi):** Farenin aydınlattığı alanlarda kesik kesik "Sarı" neon izler bırakır. İzler kasaba meydanı ve arşiv binası etrafında yoğunlaşır.
* **Durum Makinesi (Rutin):** 08:00 - 12:00 arası Meydan, 13:00 - 18:00 arası Belediye Binası.
* **User Acceptance (Kilit Açılma Şartı):** 3. seviye Hiçlik Çukuru kapatılmadan gerçek diyalog ağacı tetiklenmez.

### Honey Fairy (Bal Perisi)
![Honey Fairy Design](./../assets/Character_sheet3.gif)
* **Sistem Fonksiyonu (Day Phase):** Çiftlik yapıları inşası ve envanter/depo kapasitesi geliştirmelerinden sorumlu zanaatkar.
* **Tetikleyici Zafiyet (Night Phase):** Aşırı çalışma ve Tükenmişlik (Burnout).
* **Data Mapping (Gece İzi):** Yoğun, ağır hareket eden "Kehribar/Altın" rengi izler. İnşaat alanları çevresinde bulunur.
* **Durum Makinesi (Rutin):** 07:00 - 19:00 arası sürekli inşaat alanında veya atölyesinde devriyededir.
* **User Acceptance (Kilit Açılma Şartı):** Oyuncu ilk bina yükseltmesini talep ettiğinde aktif görev döngüsüne girer.

### Spark Fairy (Kıvılcım Perisi)
![Spark Fairy Design](./../assets/Character_sheet.gif)
* **Sistem Fonksiyonu (Day Phase):** Fırın/Taverna işletmecisi. Oyuncunun enerjisini hızla yenileyen eşyalar satar.
* **Tetikleyici Zafiyet (Night Phase):** Bastırılmış ve Kontrolsüz Öfke.
* **Data Mapping (Gece İzi):** Keskin, aniden parlayıp sönen "Kırmızı" neon izler. Tavernanın arkasındaki orman sınırında çıkar.
* **Durum Makinesi (Rutin):** 10:00 - 16:00 arası fırında, 18:00 - 01:00 arası tavernada sabit durur.
* **User Acceptance (Kilit Açılma Şartı):** Gündüz alınan ilk enerji yiyeceğinden sonraki gece döngüsünde haritada spawn olur.

### Dew Fairy (Çiy Perisi)
![Dew Fairy Design](./../assets/Character_sheet2.gif)
* **Sistem Fonksiyonu (Day Phase):** Botanikçi. Hiçlik çukurlarını kapatmak için gereken nadir şifa tohumlarını sağlar.
* **Tetikleyici Zafiyet (Night Phase):** Dış dünyaya karşı Saf Korku.
* **Data Mapping (Gece İzi):** Silik, titrek "Açık Mavi" izler. Seraların veya su kenarlarının kuytu köşelerinde saklanır.
* **Durum Makinesi (Rutin):** Sadece yağmurlu günlerde veya 06:00 - 10:00 saatleri arası serasında aktiftir.
* **User Acceptance (Kilit Açılma Şartı):** Oyuncu ilk çukuru (Tier 1) kendi kapattığında güvenini kazanır.

---

## 2. Modular Asset Pool (Product Backlog)
Tasarımı tamamlanmış ancak oyun ekonomisine veya görev ağacına henüz entegre edilmemiş sembolik veri setleri. Bu tasarımlar, ilerleyen sprintlerde sistem boşluklarını doldurmak üzere bekletilmektedir.

| Asset Kodu | Tasarım Durumu | Görsel Tema / Sembolizm | Potansiyel Zafiyet (Night Phase) | Backlog Bekleyen Sistem Fonksiyonu |
| :--- | :--- | :--- | :--- | :--- |
| **NPC_01** | Portre Hazır | Toprak tonları, yorgun bakış. | Tembellik veya Umursamazlık | İksir/Gübre üretimi (Atanmadı) |
| **NPC_02** | Portre Hazır | Prizmatik/Saydam, narin. | Kibir veya Yabancılaşma | Alet/Ekipman tamiri (Atanmadı) |
| **NPC_03** | Portre Hazır | Koyu renkler, asimetrik. | Paranoya veya Şüphe | İpucu/Sır sağlayıcısı (Atanmadı) |
| **NPC_04** | Portre Hazır | Sürekli hareketli/rüzgarlı detaylar. | Sabırsızlık | Hızlı seyahat (Fast Travel) kuryesi |
| **NPC_05** | Portre Hazır | Dağınık, yama detaylı kıyafet. | Hayal Kırıklığı | Geri dönüşüm / Hurdacı |
| **NPC_06** | Portre Hazır | Soluk ten, gizemli aura. | Derin Pişmanlık | Geçmiş kayıtlar / Hikaye anlatıcısı |
| **NPC_07** | Portre Hazır | Parlak renkli, dikkat çekici. | Kıskançlık | Kozmetik eşya satıcısı |
| **NPC_08** | Portre Hazır | Parmakları mürekkepli, gözlüklü. | Yetersizlik Hissi | Arşivci / Harita açıcı |
| **NPC_09** | Portre Hazır | Keskin hatlı, ciddi ifade. | Katı Kuralcılık | Gece devriyesi / Stealth zorluğu |
| **NPC_10** | Portre Hazır | Çok katmanlı, düğümlü detaylar. | Karmaşa / Odak Kaybı | Ticaret / Borsa (Exchange) |

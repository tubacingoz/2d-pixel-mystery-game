# Core Game Mechanics & System Economy

Bu doküman, oyunun temel döngüsünü (core loop), kaynak yönetimini (resource management) ve gündüz/gece durum makinelerinin (state machine) çalışma mantığını listeler.

## 1. Gündüz/Gece Durum Geçişleri (State Transitions)
Oyun `Day_State` ve `Night_State` olmak üzere iki temel aşamada (phase) çalışır.

*   **Day_State (06:00 - 18:00):** Çiftçilik, NPC etkileşimi ve kaynak toplama aktiftir. Renk paleti parlak ve canlıdır.
*   **Transition (18:00 - 20:00):** Uyarı fazı. Gölgeler uzar, müzik yavaşlar.
*   **Night_State (20:00 - 02:00):** Tüm NPC'ler evlerine çekilir. Zifiri karanlık başlar. Sadece oyuncunun imleci etrafında sınırlı bir görüş açısı (`Cursor_Light_Radius`) aktif olur.

## 2. Ekonomi ve Kaynak Yönetimi
Oyuncunun ilerlemesi "Stamina" ve "Zaman" kısıtlamalarına (constraints) bağlıdır.

*   **Stamina Sistemi:** Tarım faaliyetleri (çapalama, sulama) ve gece keşiflerinde koşma stamina tüketir. Stamina sıfırlanırsa oyuncu bayılır ve ertesi güne enerji cezasıyla başlar.
*   **Void Craters (Hiçlik Çukurları):** Kasaba meydanında periyodik olarak spawn olan sistem engelleri. Çukurların etrafındaki belirli bir çapta (radius) tarım yapılamaz (`Farmable_Zone = False`).
*   **Şifa Ekinleri (Healing Crops):** Çukurları kapatmak için gereken spesifik ürünler. Yetişme süreleri 2 ila 5 oyun içi gün arasında değişir.

## 3. Cursor-Driven Dedektiflik Mekaniği (Night Phase)
Gece döngüsünde geleneksel savaş (combat) yoktur, bunun yerine keşif ve stealth öne çıkar.

*   **Emotion Trails (Duygu İzleri):** Farenin aydınlatma çapı (radius) içine giren alanlarda, o gece duygusu çalınan NPC'nin bıraktığı neon izler (Particle Effects) görünür hale gelir.
*   **İz Renk Kodlaması:** 
    *   Kırmızı: Öfke (Hızlı, keskin izler)
    *   Mavi: Üzüntü (Geniş, yavaş titreyen izler)
    *   Mor: Korku (Kesik kesik, dağınık izler)
*   **Gizlilik (Stealth):** Kötü karaktere (veya onun gölgelerine) yakalanmamak için izleri takip ederken karanlık noktalarda sabit kalınmalıdır.

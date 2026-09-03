# Narrative Architecture & Branching

Bu doküman, oyunun hikaye iskeletini, NPC diyalog ağaçlarını (dialogue trees) ve ana kötünün (Antagonist) motivasyonunu tanımlar. Hikaye anlatımı, doğrudan çevresel faktörlerle (environmental storytelling) entegre çalışır.

## 1. Çekirdek Lore: "Kusursuz Sahne" (The Perfect Stage)
Kasaba dışarıdan kusursuz işleyen bir ütopya gibi görünür. Tüm periler doğuştan belirlenmiş bir "rolü" oynar.
*   **Çatışma (Conflict):** Negatif duygular (kıskançlık, öfke, tükenmişlik) bu hiyerarşide yasaktır.
*   **Sonuç:** Bastırılan bu duygular geceleri somutlaşarak kasabanın fiziksel yapısını parçalar (Hiçlik Çukurları).

## 2. Ana Kötü: Ahenk Perisi (Koro Şefi)
Sistemin yöneticisi. Kötü olmak için kötü değildir; verimlilik ve düzen adına perilerin "uyumsuz" duygularını onlardan çalarak onları hissiz işçilere dönüştürür.
*   **Hedefi:** Haritanın altında, duygulardan arındırılmış simetrik ve "kusursuz" bir yeraltı fabrikası kurmak.
*   **Yanıltıcı Rolü (Day Phase):** Oyuncuya gündüzleri sahte bir destek sunar, çukurların sorumluluğunu "dışarıdan gelen bir canavara" atar.

## 3. Görev ve Diyalog Akış Mantığı (Logic Trees)
NPC diyalogları doğrusal değildir, ön koşullara (prerequisites) bağlı olarak değişir.

*   **State_A (Duygusu Çalınmış):** NPC monoton konuşur. Görev veremez, mağazası kapalıdır.
*   **State_B (İyileşme Aşaması):** Doğru şifa bitkisi çukura uygulandığında tetiklenir. NPC, geceye ait kopuk, birbiriyle çelişen ipuçları (Yanıltıcı Alibiler) verir.
*   **State_C (Tam İyileşme):** NPC gerçek görev ağacını açar, sisteme isyan etmeye başlar.

## 4. Ana Hikaye Akışı (Three-Act Structure)
*   **Act I (Keşif):** Oyuncu kasabaya gelir, ilk çukur açılır. Ahenk perisi oyuncuyu yanlış yönlendirir. Çiftçilik mekanikleri öğrenilir.
*   **Act II (Şüphe):** İyileşen perilerin anıları birleşmeye başlar. Oyuncu fiziksel ipuçlarını çapraz sorguya çeker. Düzenin içeriden bozulduğu anlaşılır.
*   **Act III (Yüzleşme):** Yeraltı bahçesi keşfedilir. Kusursuzluk yalanına karşı, negatif duyguların (gerçek benliğin) kabul edilmesi temasıyla final tetiklenir.

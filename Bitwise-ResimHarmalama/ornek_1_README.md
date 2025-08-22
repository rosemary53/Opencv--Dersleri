# Bitwise İşlemler ile Resim Harmanlama
Bu proje, OpenCV'nin bit düzeyinde işlemlerini (bitwise operations) kullanarak bir resimdeki logo veya nesneyi başka bir resmin üzerine başarılı bir şekilde yerleştirme sürecini adım adım açıklamaktadır.

# Proje Akışı
Aşağıdaki adımlar, bit düzeyinde işlemlerle iki resmin nasıl birleştirildiğini göstermektedir.

# Resimlerin Hazırlanması

Öncelikle, hangi resmin diğerine ekleneceğine karar verilir.

Eklenecek olan resmin boyutları alınarak, ikinci resimden bu boyutlara uygun bir alan kırpılır.

Resim kırpılırken .copy() metodu kullanılır. Bu sayede, kırpılan resimde yapılan değişikliklerin orijinal resmi etkilemesi engellenir.

# Maske Oluşturma

Maskeleme işlemini kolaylaştırmak için logo resmi gri tonlamaya çevrilir.

Ardından, elde edilen gri formatta, siyaha yakın pikseller sıfır (siyah), beyaza yakın pikseller ise 255 (beyaz) olarak ayarlanır. Bu işlem, cv2.threshold() metodu ile gerçekleştirilir.

Bu işlemin ardından, elde edilen maskenin tersi cv2.bitwise_not() ile alınarak, siyahlar beyaz, beyazlar ise siyah yapılır.

# Harmanlama Aşaması

Kırpılan resim ile maske, cv2.bitwise_and() işlemine tabi tutulur. Bu, 1 AND 0'ın 0, 1 AND 1'in 1, 0 AND 0'ın 0 olması mantığıyla, logonun yerleşeceği alanda bir delik açar.

Eklenecek resim ile ters maske de bitwise_and işlemine tabi tutularak sadece logonun kendisi izole edilir.

Son olarak, elde edilen iki sonuç cv2.add() işlemiyle birleştirilir ve toplam değişkeninde tutulur.

# Final Sonucu

Ana resmin kırpılan yerine elde edilen toplam resmi eklenir ve cv2.imshow() ile ekranda gösterilir.

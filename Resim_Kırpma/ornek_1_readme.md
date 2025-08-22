# Görüntü İşleme-7: Resim Kırpma, Kopyalama ve Kanal Değiştirme
Bu proje, bir resmin belirli bir bölümünü ile nasıl kırpacağımı, başka bir bölgeye nasıl kopyalayacağımı ve renk kanalları üzerinde nasıl oynama yapacağımı gösteriyor. OpenCV ve Matplotlib kütüphanelerini kullanarak bu işlemleri adım adım yaptım.

# Nasıl Çalışır?
Resim Okuma: cv2.imread() ile pixel.jpeg dosyasını okuyorum.

# Kırpma İşlemi: 
Resim kırparken [y1:y2, x1:x2] şeklinde aralık belirlemem gerektiğini öğrendim bence bu çok önemli. Kırpılan alanı kirpilan_resim değişkeninde tutuyorum.

# Kopyalama: 
Kırpılan resmi, resim[y1:y2, x1:x2] = kirpilan_resim komutuyla orijinal resmin başka bir yerine yerleştiriyorum. Kırpılan resim (y2-y1)x(x2-x1) : 300x300 piksel boyutunda olduğu için, hedef bölgenin de 300x300 piksel olması gerekiyor.

# Kanal Değiştirme:
Resmin tüm piksellerindeki bir renk kanalını resim[:,:,0] = 0 şeklinde sıfırlayarak renkleri değiştirdim. Dikkat: OpenCV'de renk kanalları BGR formatındadır, yani 0. kanal mavidir.

# Görselleştirme: 
Matplotlib'in subplot metodu ile hem ana resmi hem de kırpılan resmi aynı pencerede alt alta gösteriyorum yani 2 satır ve 1 sütuna ayırıyorum ilk elemanı orjinal ikinci elemanı kırpılan resim olarak ayarlıyorum.

# Önemli Notlar
Matplotlib vs. OpenCV: Matplotlib renk kanallarını RGB sırasında beklerken, OpenCV BGR sırasını kullanır. Bu nedenle, bir OpenCV resmini doğrudan Matplotlib ile gösterdiğimde renkler bozuk çıkıyor.

subplot Kullanımı: plt.subplot(satır, sütun, nereye yerleştirlecek) şeklinde kullanılır. Ekranı kaç satır ve sütuna böleceğimi, ardından da hangi bölgeye çizim yapacağımı belirtiyorum.

# Resme Kenarlık Ekleme ve Görüntüleme
Bu çalışma, OpenCV'nin cv2.copyMakeBorder() metoduyla bir resme nasıl kenarlık eklendiğini gösterir.

# Kodun Çalışma Mantığı
 cv2.copyMakeBorder() Metodu kullanılır ve dikkat edilmesi gereken parametreleri vardır:

# src: 
 Kenarlık eklenecek olan kaynak resim.

# top, bottom, left, right: 
 Resmin dört kenarına eklenecek piksel miktarını belirtir. Bu değerler, resmin toplam boyutunu artırır.

# borderType: 
 Eklenecek kenarlığın tipini belirler (örn. BORDER_REPLICATE, BORDER_BORDER_CONSTANT).

# matplotlib.pyplot ile Gösterim:

 # plt.subplot(): 
   Tek bir pencereyi birden fazla alt grafiğe bölmek için kullanılır. (satır_sayısı, sütun_sayısı, eleman_sırası) formatındadır. Bu sayede, orijinal resim ve kenarlık eklenmiş versiyonları yan yana veya alt alta karşılaştırılabilir.

 # plt.imshow(): 
   Görüntüleri belirtilen alt grafiğe yerleştirir.

 # plt.title(): 
   Her bir alt grafiğe açıklayıcı bir başlık ekler.

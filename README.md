Otonom Renk Sınıflandırma ve Kontrol Robotu

Bu proje, ROS 2 tabanlı bir robotik kolun simülasyon ortamında nesneleri renklerine göre tespit edip sınıflandırmasını sağlayan uçtan uca bir otonom sistem mimarisidir. Proje; bilgisayarlı görü, hareket planlama ve fiziksel simülasyon disiplinlerini bir araya getirmektedir.

🚀 Proje Genel Bakışı
Sistem, Gazebo ortamında bulunan farklı renklerdeki nesneleri bir kamera aracılığıyla algılar, koordinatlarını belirler ve robotik kolun bu nesneleri alıp ilgili kutulara bırakmasını sağlar.

Kullanılan Teknolojiler
ROS 2: Robot işletim sistemi (Humble/Foxy).

OpenCV: Nesne tespiti ve renk segmentasyonu.

MoveIt 2: Robotik kolun eklem hareketleri ve yörünge planlaması.

Gazebo: Fizik tabanlı 3D robotik simülasyonu.

📂 Paket Yapısı
Proje, modüler bir yapıda 4 ana paketten oluşmaktadır:

otonom_gorus: OpenCV tabanlı görüntü işleme düğümlerini içerir. Renk tespiti ve nesne konumlandırma burada yapılır.

otonom_kontrol: Robotun hareket mantığını ve MoveIt 2 entegrasyonunu yöneten kontrol düğümleridir.

otonom_baslatma: Tüm sistemi (simülasyon, kontrolcü ve görüntü işleme) tek bir komutla başlatan launch dosyalarını barındırır.

panda_description: Robotun URDF/Xacro formatındaki 3D modellerini ve görsel tanımlamalarını içerir.

# 🤖 Otonom Renk Sınıflandırma Robotu


Bu proje; bilgisayarlı görü (computer vision), dinamik hareket planlaması (motion planning) ve fizik tabanlı simülasyon süreçlerini bir araya getiren gelişmiş bir **ROS 2** otonom robotik sistem mimarisidir. 7 eksenli bir endüstriyel robotik kol, entegre kamera sensörü üzerinden aldığı görüntüleri gerçek zamanlı işleyerek nesneleri renklerine göre ayırt eder ve otonom olarak sınıflandırır.

---

## 📺 Simülasyon



https://github.com/user-attachments/assets/6bcde89f-9c5a-4aef-98ef-0162caa277cf



---

## 🚀 Öne Çıkan Özellikler

- **Gerçek Zamanlı Bilgisayarlı Görü:** OpenCV tabanlı gelişmiş renk segmentasyonu ve HSV filtreleme algoritmaları ile kesintisiz nesne takibi.
- **Dinamik Yörünge Planlama:** MoveIt 2 entegrasyonu sayesinde eklem limitleri, hız/ivme optimizasyonları ve engellerden sakınarak pürüzsüz taşıma (Pick and Place) operasyonları.
- **Modüler Dağıtık Mimari:** ROS 2'nin modern düğüm (node) yapısına uygun, birbiriyle servis ve mimari ağlar üzerinden haberleşen bağımsız paket tasarımları.
- **Endüstriyel Simülasyon:** Gerçek dünya fizik motoru kurallarına (sürtünme, yerçekimi, temas kuvvetleri) uygun Gazebo ortamı tasarımı.

---

## 📂 Yazılım Mimarisi ve Paket Yapısı

Proje, genişletilebilir ve bakımı kolay (maintainable) olacak şekilde katmanlı bir mimaride tasarlanmıştır:

* 📂 **`otonom_gorus`**: Kamera düğümünden gelen ham görüntüleri (Image Topic) dinleyen, renk maskeleme, kontur tespiti ve ağırlık merkezi hesaplama işlemlerini yürüten Python tabanlı görüntü işleme modülüdür.
* 📂 **`otonom_kontrol`**: Görüntü işleme düğümünden gelen koordinat verilerini yorumlayan, robotun kinematik hesaplamalarını (Inverse Kinematics) yaparak MoveIt 2 üzerinden `Pick and Place` görev dizilimini yöneten ana kontrolör.
* 📂 **`otonom_baslatma`**: Karmaşık ROS 2 sistemini, simülasyon dünyasını ve tüm alt düğümleri senkronize bir şekilde tek komutla ayağa kaldıran Python launch kurguları.
* 📂 **`panda_description`**: Robotik sistemin ve çalışma uzayının tüm fiziksel/görsel özelliklerini (URDF, Xacro modelleri, mesh dosyaları) barındıran donanım tanım katmanı.

---

## 🛠️ Sistem Gereksinimleri ve Kurulum

### Gereksinimler
- Ubuntu 22.04 LTS / WSL 2 (Ubuntu 22.04)
- ROS 2 Humble (veya Foxy)
- OpenCV (Python bindings)
- MoveIt 2 & Gazebo ROS Paketleri

### Adım Adım Kurulum

1. **Çalışma Alanını (Workspace) Hazırlayın:**
   ```bash
   cd ~/ros2_ws/src
   # Depoyu bu klasöre klonlayın veya dosyalarınızın burada olduğundan emin olun

### Bağımlılıkları Çözün ve Derleyin
```bash
cd ~/ros2_ws
rosdep install --from-paths src --ignore-src -r -y
colcon build --symlink-install





   
   
   

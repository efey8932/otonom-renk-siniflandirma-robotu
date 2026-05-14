# 🤖 ROS 2 Tabanlı Otonom Renk Sınıflandırma ve Kontrol Robotu

[![ROS 2](https://img.shields.io/badge/ROS%202-Humble%20%2F%20Foxy-blue?logo=ros&logoColor=white)](https://docs.ros.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green?logo=opencv&logoColor=white)](https://opencv.org/)
[![MoveIt 2](https://img.shields.io/badge/MoveIt-2-orange)](https://moveit.ros.org/)
[![Gazebo](https://img.shields.io/badge/Gazebo-Simulation-red?logo=gazebo&logoColor=white)](https://gazebosim.org/)

Bu proje; bilgisayarlı görü (computer vision), dinamik hareket planlaması (motion planning) ve fizik tabanlı simülasyon süreçlerini bir araya getiren gelişmiş bir **ROS 2** otonom robotik sistem mimarisidir. 7 eksenli bir endüstriyel robotik kol, entegre kamera sensörü üzerinden aldığı görüntüleri gerçek zamanlı işleyerek nesneleri renklerine göre ayırt eder ve otonom olarak sınıflandırır.

---

## 📺 Proje Tanıtım Videosu & Simülasyon

> **Sürükle-Bırak Alanı:** Bilgisayarındaki simülasyon video dosyasını (.mp4) tam olarak bu satırın altına sürükleyip bırakarak GitHub sunucularına yükleyebilirsin.

*(Videonuzu buraya sürükleyip bırakın)*

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

# Isik_Kontrol_Projesi---Light_Control_Project_with_Sensor
Arduino Mega ve Simulink kullanılarak gerçekleştirilen, HC-SR04 ultrasonik sensör gürültü filtrelemeli ve Anti-Windup (Clamping) mekanizmalı PID tabanlı temassız LED parlaklık kontrolü projesi.---A PID-based wireless LED brightness control project using the HC-SR04 ultrasonic sensor with noise filtering and an anti-windup (clamping) mechanism, implemented using Arduino Mega and Simulink

# Türkçe:

# Arduino & Simulink ile Temassız Işık Kontrolü (PID)

Bu proje, Arduino Mega ve Simulink mimarisi üzerinde çalışan geri beslemeli (Closed-Loop) bir temassız LED parlaklık kontrol sistemidir. Kullanıcı sensöre elini yaklaştırıp uzaklaştırarak LED parlaklığını pürüzsüz bir şekilde ayarlayabilir.

## 🛠️ Kullanılan Donanım ve Araçlar
* Arduino Mega 2560
* HC-SR04 Ultrasonik Sensör
* Standart LED & 220Ω Direnç
* MATLAB / Simulink (Discrete-Time Solver)

## 🚀 Proje Sürecinde Çözülen Mühendislik Problemleri

### 1. Sinyal İşleme ve Gürültü Engelleme (Noise Filtering)
Sensörden gelen verilerdeki mikro saniyelik sapmaları ve sivri uçları (spike) engellemek amacıyla **Median Filter (Medyan Filtresi)** kullanılmış ve temiz bir mesafe verisi elde edilmiştir.

### 2. Integrator Windup (İntegral Taşması) Çözümü
PID kontrolcünün **I (Integral)** teriminin zamanla hata biriktirerek sistemi 10-15 saniye içinde kilitlemesi problemi, **Anti-Windup (Clamping)** mekanizması aktif edilerek çözülmüştür. Bu sayede sistem sonsuz döngüde kararlı çalışmaktadır.

### 3. Örnekleme Zamanı Uyuşmazlığı (Multi-rate Sampling)
Simulink ana çözücü saati (Solver size) ile sensör örnekleme zamanının uyuşmaması sonucu oluşan Multi-rate hatası, tüm sistem frekanslarının 0.1s adım süresine senkronize edilmesiyle giderilmiştir.

# English:

# Contactless Light Control (PID) with Arduino & Simulink

This project is a closed-loop wireless LED brightness control system running on an Arduino Mega and Simulink architecture. The user can smoothly adjust the LED brightness by moving their hand closer to or farther from the sensor.

## 🛠️ Hardware and Tools Used
* Arduino Mega 2560
* HC-SR04 Ultrasonic Sensor
* Standard LED & 220Ω Resistor
* MATLAB / Simulink (Discrete-Time Solver)

## 🚀 Engineering Problems Solved During the Project

### 1. Signal Processing and Noise Filtering
A **Median Filter** was used to filter out microsecond-level deviations and spikes in the data from the sensor, resulting in clean distance data.

### 2. Integrator Windup Solution
The problem where the **I (Integral)** term of the PID controller accumulates error over time, causing the system to lock up within 10–15 seconds, was resolved by activating the **Anti-Windup (Clamping)** mechanism. As a result, the system operates stably in an infinite loop.

### 3. Multi-rate Sampling
The multi-rate error caused by a mismatch between the Simulink solver time (Solver size) and the sensor sampling rate was resolved by synchronizing all system frequencies to a 0.1-second step time.

Translated with DeepL.com (free version)



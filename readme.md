# Dokumentasi Sistem

## 1. Pinout Sensor dan Kontrol

### Sensor Gas MQ135
- **VCC**: Sambungkan ke pin 5V pada Arduino.
- **GND**: Sambungkan ke pin GND pada Arduino.
- **AOUT**: Sambungkan ke pin analog A0 pada Arduino.

### Relay dan Servo
- **Relay 1**:
  - **Pin**: Digital Pin 2
  - **Fungsi**: Mengaktifkan relay 1.
- **Relay 2**:
  - **Pin**: Digital Pin 3
  - **Fungsi**: Mengaktifkan relay 2.
- **Relay 3**:
  - **Pin**: Digital Pin 4
  - **Fungsi**: Mengaktifkan relay 3.
- **Servo**:
  - **Pin**: Digital Pin 9
  - **Fungsi**: Mengontrol posisi servo.

## 2. Pengkabelan

### MQ135 Gas Sensor
1. **VCC (Sensor)** -> **5V (Arduino)**
2. **GND (Sensor)** -> **GND (Arduino)**
3. **AOUT (Sensor)** -> **A0 (Arduino)**

### Relay
1. **Relay 1**
   - **IN** -> **Digital Pin 2 (Arduino)**
   - **VCC** -> **5V (Arduino)**
   - **GND** -> **GND (Arduino)**
   
2. **Relay 2**
   - **IN** -> **Digital Pin 3 (Arduino)**
   - **VCC** -> **5V (Arduino)**
   - **GND** -> **GND (Arduino)**

3. **Relay 3**
   - **IN** -> **Digital Pin 4 (Arduino)**
   - **VCC** -> **5V (Arduino)**
   - **GND** -> **GND (Arduino)**

### Servo
1. **Signal** -> **Digital Pin 9 (Arduino)**
2. **VCC** -> **5V (Arduino)**
3. **GND** -> **GND (Arduino)**

## 3. Algoritma Kontrol Berdasarkan Nilai PPM

### Langkah-Langkah Algoritma

1. **Baca Nilai PPM dari Sensor:**
   - Bacalah nilai analog dari pin A0.
   - Hitung konsentrasi gas dalam PPM menggunakan rumus yang telah ditentukan.

2. **Tentukan Tipe Kontrol Berdasarkan PPM:**
   - **Jika PPM CO2 < 500:**
     - **Tipe 0**:
       - Aktifkan Relay 1.
       - Servo bergerak ke 180 derajat.
   - **Jika PPM CO2 >= 500 dan < 700:**
     - **Tipe 1**:
       - Aktifkan Relay 1.
       - Servo bergerak ke 90 derajat.
   - **Jika PPM CO2 >= 700 dan < 1000:**
     - **Tipe 2**:
       - Aktifkan Relay 1 dan Relay 2.
       - Servo bergerak ke 90 derajat.
   - **Jika PPM CO2 >= 1000:**
     - **Tipe 3**:
       - Aktifkan Relay 1, Relay 2, dan Relay 3.
       - Servo bergerak ke 90 derajat.

3. **Implementasikan Kontrol:**
   - Berdasarkan tipe kontrol yang ditentukan, aktifkan relai dan posisikan servo sesuai dengan ketentuan.


# 📇 vCard Exporter for Adobe Illustrator

Bu proje, bir MySQL veritabanındaki kullanıcı bilgilerini ve fotoğraflarını alarak:

1. `data.csv` dosyasını üretir.  
2. Kullanıcı fotoğraflarını `photo/` klasörüne `.jpg` formatında kaydeder.  
3. Adobe Illustrator şablon dosyasını kullanarak her kullanıcı için:  
   - `.ai` dosyası  
   - `.jpg` görsel  
   - `.png` görsel  
   oluşturur.

---

## 🚀 Kullanım Adımları

### 1. CSV ve Fotoğrafları Oluştur (Python Script)

```bash
python3 generate_csv.py [PersonelKodu]
PersonelKodu isteğe bağlıdır.
Belirtilirse sadece o kullanıcıya ait veri işlenir.
Belirtilmezse tüm kullanıcılar alınır.
Örnekler:
Tüm kullanıcılar:

python3 generate_csv.py
Sadece IT.jpg dosyasına sahip kullanıcı:
python3 generate_csv.py IT
2. Adobe Illustrator Script'ini Çalıştır
Python scripti tamamlandıktan sonra Illustrator'da:
Menü:

Dosya > Komut Dosyaları > Diğer Komut Dosyaları...
Ardından exportvcard.jsx dosyasını seçin.
Script şu klasörlere çıktı verir:

.ai dosyaları → Export/
.jpg görselleri → Export/JPG/
.png görselleri → Export/PNG/
📁 Klasör Yapısı
project-root/
├── export_vcards.py          # CSV ve fotoğraf oluşturan Python scripti
├── exportvcard.jsx           # Illustrator otomasyon scripti
├── signature.ai              # Illustrator şablon dosyası
├── data.csv                  # Otomatik oluşur – kullanıcı verileri
├── photo/                    # Otomatik oluşur – kullanıcı fotoğrafları
├── Export/
│   ├── JPG/
│   └── PNG/
└── README.md                 # Bu dosya
⚙️ Gereksinimler
Python 3
pymysql kütüphanesi:
pip install pymysql
Adobe Illustrator (ExtendScript destekleyen sürüm)
📌 Teknik Detaylar
data.csv dosyası ; (noktalı virgül) ayracı kullanır.
Illustrator scripti aşağıdaki alanları kullanır:
@ad
@surname
@position
@mobile
@email
@photo
Olası hatalar script.log dosyasına yazılır.
👨‍💻 Geliştiren
İlker Taşkınoğlu
TuzlaHortum

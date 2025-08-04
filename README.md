
# 📇 vCard Exporter for Adobe Illustrator

Bu proje, bir MySQL veritabanındaki kullanıcı bilgilerini ve fotoğraflarını alarak:

- `data.csv` dosyasını üretir.  
- Kullanıcı fotoğraflarını `photo/` klasörüne `.jpg` formatında kaydeder.  
- Adobe Illustrator şablon dosyasıyla her kullanıcı için:
  - `.ai` dosyası
  - `.jpg` görsel
  - `.png` görsel  
  oluşturur.

---

## 🚀 Kullanım

### 1. CSV ve Fotoğrafları Oluştur (Python Script)

```bash
python3 generate_csv.py [PersonelKodu]
```

PersonelKodu opsiyoneldir.
Belirtilirse yalnızca ilgili kullanıcı işlenir. Belirtilmezse tüm kullanıcılar alınır.

Örnek:
Tüm kullanıcıları işlemek için:
```bash
python3 generate_csv.py
```

Sadece IT.jpg olan kullanıcıyı işlemek için:
```bash
python3 generate_csv.py IT
```

2. Illustrator Script'ini Çalıştır
Python scripti çalıştıktan sonra Illustrator'da:
Dosya > Komut Dosyaları > Diğer Komut Dosyaları...
Seçilecek dosya: exportvcard.jsx
Script, data.csv ve photo/ klasörünü okuyarak şu çıktıları üretir:
.ai → Export/
.jpg → Export/JPG/
.png → Export/PNG/
📁 Klasör Yapısı
project-root/
├── export_vcards.py          # CSV ve fotoğraf oluşturan Python scripti
├── exportvcard.jsx           # Illustrator otomasyon scripti
├── signature.ai              # Illustrator şablon dosyası
├── data.csv                  # Otomatik oluşur
├── photo/                    # Kullanıcı fotoğrafları
├── Export/
│   ├── JPG/
│   └── PNG/
└── README.md                 # Bu belge


⚙️ Gereksinimler
Python 3
Illustrator (ExtendScript destekleyen bir sürüm)
Python bağımlılığı:
pip install pymysql
📌 Notlar
data.csv dosyası ; (noktalı virgül) ile ayrılmıştır.

Illustrator scripti aşağıdaki alanları kullanır:
@ad
@surname
@position
@mobile
@email
@photo
Hatalar script.log dosyasına yazılır.

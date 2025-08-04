
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

2. Adobe Illustrator Script'ini Hazırla
Adobe Illustrator'ı aç.
Menüden şunu takip et:
```text
Dosya > Komut Dosyaları > Diğer Komut Dosyaları...
```

Açılan pencerede exportvcard.jsx dosyasını seç.

4. vCard'ları Otomatik Olarak Oluştur
Script çalıştığında, data.csv ve photo/ klasöründeki her satır için Illustrator şablon dosyasını kullanarak şu dosyaları otomatik olarak oluşturur:
.ai → Export/
.jpg → Export/JPG/
.png → Export/PNG/
⏳ İşlem tamamlandığında:
Tüm çıktılar Export/ alt klasörlerinde görünür.
Her kullanıcı için birer adet .ai, .jpg, .png dosyası oluşur.
Hatalar varsa script.log dosyasında listelenir.


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

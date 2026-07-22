# Haliloxo Live Studio

TikTok canlı yayın skor/lider overlay ve olay eylemleri yönetim uygulaması.

## Kurulum

1. `dist` klasöründeki `Haliloxo Live Studio Setup x.x.x.exe` dosyasını çalıştır.
2. Kurulum sihirbazı eksik bağımlılıkları otomatik yükler (Node.js/Electron uygulama içinde paketlidir).
3. Masaüstü ve Başlat Menüsü kısayolları oluşturulur.

## Otomatik Güncelleme

Program başlatıldığında GitHub Releases üzerinden yeni sürüm kontrolü yapar.  
Yeni sürüm varsa üst çubukta **Güncelle** butonu belirir. Butona basıldığında güncelleme indirilir, kurulur ve uygulama yeniden başlar.

Yeni sürüm bilgisi (düzeltilen hatalar, eklenen özellikler) **Güncel** yazısına tıklanarak açılan panelde 1 hafta boyunca görülebilir.

## Geliştirici için

### Gerekli

- Node.js (v20+)
- npm

### Çalıştır

```bash
npm install
npm start
```

### Kurulum dosyası oluştur

```bash
npm run dist
```

Çıktı `dist/` klasöründe oluşur.

### GitHub Releases üzerinden yayınla

1. `package.json` içindeki `repository` alanı zaten ayarlı:

```json
"repository": "https://github.com/haliloxox/haliloxostudio"
```

2. `CHANGELOG.md` dosyasındaki sürüm notlarını güncelle.
3. `package.json` içindeki `version` değerini artır (örneğin `1.0.1`).
4. GitHub'da **Tag** oluştur:

```bash
git tag -a v1.0.1 -m "v1.0.1"
git push origin v1.0.1
```

5. `npm run publish` komutunu çalıştır.  
   Bu komut `GITHUB_TOKEN` ortam değişkenini kullanarak kurulum dosyasını GitHub Releases'a yükler.

Ortam değişkeni ayarı (PowerShell):

```powershell
$env:GITHUB_TOKEN="ghp_xxx"
npm run publish
```

**Not:** `GITHUB_TOKEN` için GitHub'da `repo` yetkisine sahip bir Personal Access Token oluşturulmalıdır.

## Sürüm Notları

Detaylı değişiklik listesi için `CHANGELOG.md` dosyasına bak.

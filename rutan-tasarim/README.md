# RUTAN TASARIM — Decap CMS Entegreli Site

Bu site **Decap CMS** (eski adıyla Netlify CMS) ile entegredir. Site içeriğini (fiyatlar, hizmetler, yorumlar, yazılar) GitHub veya Git-Gateway üzerinden yönetebilirsin.

---

## 🚀 Hızlı Kurulum (5 dakika)

### 1️⃣ GitHub'a Yükle

```bash
git init
git add .
git commit -m "İlk sürüm — Decap CMS entegrasyonu"
git branch -M main
git remote add origin https://github.com/KULLANICI_ADIN/rutan-tasarim.git
git push -u origin main
```

### 2️⃣ Netlify'a Bağla

1. https://app.netlify.com adresine git
2. **"Add new site" → "Import an existing project"** seç
3. GitHub repo'nu seç (yukarıda oluşturduğun)
4. **Build command:** boş bırak
5. **Publish directory:** `.` (nokta)
6. **Deploy site**'a bas

### 3️⃣ Identity & Git Gateway'i Aç (ÇOK ÖNEMLİ!)

1. Netlify dashboard'da siteni aç
2. **Site settings** → **Identity** bölümüne git
3. **"Enable Identity"** butonuna bas
4. **Identity → Services** → **"Enable Git Gateway"** seçeneğini aç
5. **Identity → Registration** → **"Invite only"** seç (sadece sen girebilesin)

### 4️⃣ İlk Admin Kullanıcısı Oluştur

1. Tarayıcıda `https://rutantasarmm.netlify.app/admin` adresine git
2. **"Sign up"** ile hesap oluştur
3. **"Sign in"** ile giriş yap
4. Artık admin paneline erişebilirsin!

### 5️⃣ (Opsiyonel) E-posta Davet

Eğer yanlışlıkla "Open" registration açtıysan, Netlify Identity üzerinden kendine davet maili atabilirsin:
- Identity → **"Invite users"** → e-postanı yaz → davet linki mailine gelir

---

## 📂 Dosya Yapısı

```
rutan-tasarim/
├── index.html              # Ana sayfa (CMS içeriğini otomatik yükler)
├── admin/
│   ├── index.html          # Admin giriş sayfası
│   └── config.yml          # CMS alan tanımları
├── content/                # CMS buraya içerik yazar
│   ├── paketler/           # Fiyat paketleri (md dosyaları)
│   ├── hizmetler/          # Hizmet kartları
│   ├── neden/              # "Neden Biz" 6 maddesi
│   ├── surec/              # Süreç adımları (4 adım)
│   ├── yorumlar/           # Müşteri yorumları
│   └── ayarlar/
│       └── genel.json      # Telefon, mail, başlıklar
├── images/uploads/         # CMS'e yüklenen görseller (otomatik oluşur)
├── netlify.toml            # Netlify yapılandırması
└── package.json
```

---

## ✏️ Admin Panelinden Neler Yönetilir?

| Bölüm | Yol | Açıklama |
|-------|-----|----------|
| **Fiyat Paketleri** | `/admin/#/collections/paketler` | Yeni paket ekle, fiyatı değiştir, özellikleri düzenle |
| **Hizmetler** | `/admin/#/collections/hizmetler` | Üst bölümdeki 6 hizmet kartı |
| **Neden Biz** | `/admin/#/collections/neden` | "Neden Biz" bölümündeki 6 madde |
| **Süreç Adımları** | `/admin/#/collections/surec` | "Nasıl Çalışırız" — 4 adım |
| **Yorumlar** | `/admin/#/collections/yorumlar` | Müşteri yorumları ekle/sil/düzenle |
| **Site Ayarları** | `/admin/#/collections/ayarlar` | Telefon, e-posta, hero başlığı |

---

## 🔄 Değişiklik Nasıl Anında Yayına Girer?

1. Admin panelinden bir içerik değiştirirsin
2. **"Publish"** butonuna basarsın
3. Decap CMS otomatik olarak GitHub'a bir commit atar
4. Netlify bu commit'i algılar, **30 saniye içinde** siten yayınlanır
5. Sayfayı yenilediğinde değişikliği görürsün

---

## 🆘 Sorun Giderme

**Admin paneline giremiyorum:**
- Netlify → Identity → Git Gateway'in açık olduğundan emin ol
- Tarayıcı cache'ini temizle
- Çıkış yap, tekrar giriş yap

**Değişiklikler yansımıyor:**
- Netlify dashboard → "Deploys" sekmesinden build başarılı mı bak
- Tarayıcıda **Ctrl+Shift+R** ile hard refresh yap
- CMS publish workflow'da "Draft" mı kalmış, "Published" olmuş mu kontrol et

**Sıfırdan başlamak istersen:**
```bash
rm -rf .git
git init
git add .
git commit -m "Reset"
git push -f origin main
```

---

## 📞 Destek

RUTAN TASARIM — 0542 415 71 74

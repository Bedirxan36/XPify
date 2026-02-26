# XPify - Gamify Your Life 🎮

Modern bir WPF masaüstü uygulaması ile bilgisayar aktivitelerinizi oyunlaştırın!

## 🚀 Özellikler

### ✨ Aktivite Takibi
- Aktif pencere algılama (Win32 API)
- Otomatik kategorizasyon:
  - 💻 **Kod Yazma**: Visual Studio, VS Code, Rider → +20 XP/30dk
  - 📚 **Ders Çalışma**: PDF okuyucular, Notion, Udemy → +15 XP/30dk
  - 🎮 **Oyun**: Steam, Epic Games → -10 XP/30dk
  - ⚡ **Üretken**: Office, Browser → +10 XP/30dk

### 🎯 XP & Seviye Sistemi
- Dinamik seviye sistemi (her level %15 daha fazla XP gerektirir)
- **Level 1**: 100 XP gerekir
- **Level 2**: 115 XP gerekir
- **Level 3**: 132 XP gerekir
- Progress bar ile görsel takip

### 🏆 Ünvan Sistemi
- **Level 1-5**: Çaylak
- **Level 6-10**: Acemi Kodcu
- **Level 11-20**: Yazılım Savaşçısı
- **Level 21-35**: Kod Ustası
- **Level 36-50**: Dijital Ninja
- **Level 51-75**: Sistem Mimarı
- **Level 76-100**: Efsane Geliştirici
- **Level 100+**: XP Tanrısı

### 📊 Dashboard
- Günlük XP istatistikleri
- Kategori bazlı XP dağılımı
- Son aktiviteler listesi
- Haftalık performans grafiği
- Seviye ilerleme çubuğu

### 🔔 Bildirim Sistemi
- Seviye atladığınızda popup gelir
- 30 dakikadan fazla oyun oynarsan uyarı alırsın
- XP kazanım bildirimleri

### ⚙️ Profil Ayarları
- Kullanıcı adı değiştirme
- Avatar/Emoji seçimi (12 farklı emoji)
- Profil bilgilerini güncelleme

## 🛠️ Teknolojiler

- **.NET 10**
- **WPF** (Windows Presentation Foundation)
- **MVVM** Architecture
- **Entity Framework Core** + SQLite
- **CommunityToolkit.Mvvm** (ObservableObject, RelayCommand)
- **Win32 API** (Foreground Window Detection)

## 📁 Proje Yapısı

```
XPify/
├── Models/              # Veri modelleri
│   ├── User.cs
│   ├── Activity.cs
│   └── DailyStat.cs
├── Data/                # Veritabanı
│   └── XPifyDbContext.cs
├── Services/            # İş mantığı
│   ├── ActivityMonitorService.cs
│   ├── XPCalculationService.cs
│   └── NotificationService.cs
├── ViewModels/          # MVVM ViewModels
│   ├── MainViewModel.cs
│   └── SettingsViewModel.cs
├── Views/               # UI
│   ├── MainWindow.xaml
│   └── SettingsWindow.xaml
├── Converters/          # XAML Converters
│   ├── DurationConverter.cs
│   ├── NegativeValueConverter.cs
│   └── ProgressBarWidthConverter.cs
└── Styles/              # UI Temaları
    └── DarkTheme.xaml
```

## 🎨 Veritabanı Şeması

### Users
- Id (PK)
- Username
- Level
- TotalXP
- CurrentXP
- Title
- AvatarPath
- CreatedAt
- LastActiveAt

### Activities
- Id (PK)
- AppName
- Category
- Duration (seconds)
- EarnedXP
- Date
- UserId (FK)

### DailyStats
- Id (PK)
- Date
- TotalXP
- CodingXP
- StudyXP
- GameXP
- UserId (FK)

## 🚀 Kurulum

### Kullanıcılar İçin (Installer)
1. `XPify-Setup.exe` dosyasını indirin
2. Çift tıklayarak kurulumu başlatın
3. Kurulum sihirbazını takip edin
4. Uygulamayı başlatın!

### Geliştiriciler İçin
1. Projeyi klonlayın
2. .NET 10 SDK'nın yüklü olduğundan emin olun
3. NuGet paketlerini restore edin:
```bash
dotnet restore
```

4. Uygulamayı çalıştırın:
```bash
dotnet run --project XPify
```

## 📦 Installer Oluşturma

### Yöntem 1: Inno Setup (Önerilen - Kolay)
```powershell
cd Installer
.\build-inno.ps1
```
**Çıktı**: `Installer\bin\XPify-Setup.exe`

### Yöntem 2: WiX Toolset (MSI)
```powershell
cd Installer
.\build-installer.ps1
```
**Çıktı**: `Installer\bin\XPify-Setup.msi`

Detaylı bilgi için: `Installer/QUICK-START.md`

## 📦 Installer Oluşturma

XPify için profesyonel installer oluşturabilirsiniz!

### 🚀 Hızlı Yöntem (Inno Setup - Önerilen)
```powershell
cd Installer
.\build-inno.ps1
```
**Çıktı**: `XPify-Setup.exe` (Modern UI, Türkçe dil desteği)

### 📋 Alternatif (WiX Toolset - MSI)
```powershell
cd Installer
.\build-installer.ps1
```
**Çıktı**: `XPify-Setup.msi` (Enterprise uyumlu)

**Detaylı rehber**: `BUILD-INSTALLER.md` ve `Installer/QUICK-START.md`

---

## 📦 Gerekli NuGet Paketleri

```xml
<PackageReference Include="Microsoft.EntityFrameworkCore.Sqlite" Version="10.0.0" />
<PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="10.0.0" />
<PackageReference Include="CommunityToolkit.Mvvm" Version="8.3.0" />
<PackageReference Include="LiveCharts.Wpf" Version="0.9.7" />
<PackageReference Include="Hardcodet.NotifyIcon.Wpf" Version="1.1.0" />
```

## 🎯 Kullanım

1. Uygulamayı başlatın
2. Uygulama arka planda çalışmaya başlar
3. Aktiviteleriniz otomatik olarak izlenir
4. Dashboard'dan istatistiklerinizi görüntüleyin
5. **⚙️ Ayarlar** butonundan profil bilgilerinizi düzenleyin
6. XP kazanın ve seviye atlayın!

### 📊 Dashboard'da Görebilirsiniz:
- Bugün kazandığınız toplam XP
- Hangi kategoriden ne kadar XP kazandınız
- Son aktiviteleriniz
- Seviye ilerlemeniz
- Profil bilgileriniz (avatar, isim, level, ünvan)

## 🔧 Yapılandırma

Veritabanı dosyası şu konumda saklanır:
```
%LocalAppData%\XPify\xpify.db
```

## 🎮 XP Hesaplama Mantığı

```csharp
XP = (BaseXP * Duration) / 1800
```

- BaseXP: Kategori bazlı temel XP
- Duration: Saniye cinsinden süre
- 1800: 30 dakika (referans süre)

## 🏗️ Mimari Kararlar

### MVVM Pattern
- **Model**: Veri yapıları (User, Activity, DailyStat)
- **View**: XAML UI dosyaları
- **ViewModel**: UI mantığı ve veri bağlama

### Servisler
- **ActivityMonitorService**: Win32 API ile pencere izleme
- **XPCalculationService**: XP hesaplama ve seviye yönetimi
- **NotificationService**: Kullanıcı bildirimleri

### Async/Await
- Tüm veritabanı işlemleri asenkron
- UI thread blocking önlenir
- Smooth kullanıcı deneyimi

## 🔮 Gelecek Özellikler

- [x] Profil ayarları ve avatar sistemi
- [ ] System Tray desteği
- [ ] Windows başlangıcında otomatik başlatma
- [ ] Haftalık/aylık grafikler
- [ ] Hedef belirleme sistemi
- [ ] Başarım (achievement) sistemi
- [ ] Tema özelleştirme
- [ ] Export/Import profil

## 📝 Lisans

MIT License

## 👨‍💻 Geliştirici

XPify - Modern WPF Gamification App

---

**Not**: Bu uygulama production-ready olarak tasarlanmıştır. Tüm best practice'ler uygulanmıştır.

<p align="center">
  <img src="assets/linguaforge_logo.jpeg" alt="LinguaForge Logo" width="200"/>
</p>

<p align="center">
  <strong>LinguaForge</strong> ist eine modulare Plattform zur Entwicklung von Sprachkernprogrammen.<br>
  Ziel ist es, eine robuste, ARM64-optimierte Umgebung für die Verarbeitung, Darstellung und Auswahl von Sprachen bereitzustellen – sowohl für mobile als auch für Desktop-Anwendungen.
</p>

# flutter-arm64-lingua

Ein Flutter-Projekt, optimiert für ARM64-Architekturen unter Linux.
## 🧠 Ziel

Dieses Projekt demonstriert, wie man Flutter-Anwendungen auf ARM64-Systemen (z. B. Raspberry Pi, PineBook Pro oder native ARM64-Tablets) erfolgreich baut und ausführt — inklusive Workarounds für fehlende `gen_snapshot`-Binaries.

## ⚙️ Setup

### Voraussetzungen

- Flutter SDK (manuell installiert)
- ARM64 Linux (z. B. Ubuntu 22.04 auf ARM64)
- Git, curl, unzip, clang, cmake, ninja

### Installation

```bash
git clone https://github.com/lieberschwager/flutter-arm64-lingua.git
cd flutter-arm64-lingua
flutter pub get
```

## 🛠️ ARM64 Workaround für `gen_snapshot`

Da Flutter keine offiziellen ARM64-Binaries für `gen_snapshot` bereitstellt, wurde folgender Workaround implementiert:

- Manuelles Kompilieren von `gen_snapshot` aus dem Flutter-Engine-Quellcode
- Ersetzen der Standard-Binary im Flutter SDK:

```bash
cp /pfad/zur/kompilierten/gen_snapshot $FLUTTER_ROOT/bin/cache/artifacts/engine/linux-arm64-release/gen_snapshot
```

## 🧪 Debug & Build

### Debug-Modus

```bash
flutter run
```

### Release-Build

```bash
flutter build linux --release
```

## 📦 APK-Erstellung (optional)

Falls du das Projekt für Android ARM64 kompilieren willst:

```bash
flutter build apk --target-platform android-arm64
```

## 🗺️ Roadmap

- [ ] Automatisiertes Setup-Skript für ARM64
- [ ] Integration von Flutter Desktop auf ARM64
- [ ] Cross-Compile für x64 aus ARM64-Umgebung
- [ ] Dokumentation auf Deutsch & Englisch

## 🤝 Mitwirken

Pull Requests sind willkommen! Dieses Projekt soll anderen helfen, Flutter auf ARM64-Systemen produktiv einzusetzen.

---

Guido Lieberschwager  
Grevenbroich, Deutschland

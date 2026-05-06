# UrunApp
1. Temel paketler
sudo apt update && sudo apt upgrade -y
sudo apt install -y curl git unzip xz-utils zip libglu1-mesa clang cmake ninja-build pkg-config libgtk-3-dev
2. Flutter SDK
cd ~
mkdir -p development
cd development
git clone https://github.com/flutter/flutter.git -b stable

PATH ekle:

nano ~/.bashrc

En alta ekle:

export PATH="$PATH:$HOME/development/flutter/bin"

Kaydet, sonra:

source ~/.bashrc
flutter --version
flutter doctor
3. Android Studio

VS Code kullanacağız ama Android SDK için Android Studio gerekli:

sudo snap install android-studio --classic

Android Studio’yu aç ve şunları kur:

Android SDK
Android SDK Platform
Android SDK Command-line Tools
Android SDK Build-Tools
Android Emulator

Sonra:

flutter doctor --android-licenses
flutter doctor
4. VS Code
sudo snap install code --classic

VS Code extension’ları:

Flutter
Dart
Error Lens
GitLens
Pubspec Assist
5. Node.js
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
node -v
npm -v
6. Supabase CLI

Şimdilik global kurma, şu şekilde kullan:

npx supabase --version
7. Docker
sudo apt install -y docker.io docker-compose-v2
sudo usermod -aG docker $USER

Sonra bilgisayarı yeniden başlat.

Kontrol:

docker --version
docker compose version
8. GitHub SSH
ssh-keygen -t ed25519 -C "senin_emailin@example.com"
cat ~/.ssh/id_ed25519.pub

Çıkan key’i GitHub’a ekle.

9. VS Code’da Flutter çalıştırma testi
cd ~
flutter create test_app
cd test_app
code .

VS Code içinde:

Ctrl + Shift + P
Flutter: Select Device

Sonra:

F5

veya terminalden:

flutter run
10. Kurulum tamam kontrolü
flutter doctor
git --version
node -v
npm -v
docker --version
npx supabase --version

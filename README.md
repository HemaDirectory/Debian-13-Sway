# تثبيت Debian 13 + Sway

## 1. تثبيت Debian 13 الأساسي

1. قم بتحميل صورة Debian 13 (Netinst أو DVD).
2. أقلِع من الوسيط وابدأ التثبيت.
3. عند خطوة اختيار بيئة سطح المكتب:

   * أزل جميع الخيارات (GNOME, KDE, XFCE...)
   * أبقِ فقط:

     * **standard system utilities**
     * **SSH server** (اختياري)
4. أكمل التثبيت حتى النهاية.

يمكنك مشاهدة الشرح الكامل في هذا الفيديو [من هنا](https://youtu.be/x8clKyCeyFA?si=_FqbJrvicMhRjH6e) إذا أردت تفاصيل أكثر.


---

## 2. تسجيل الدخول بعد التثبيت

بعد الإقلاع الأول، سجّل الدخول من خلال الـ TTY.

---

## 3. تثبيت Sway

قم بتشغيل:

```bash
sudo apt update
```
```bash
sudo apt install git
```
```bash
git clone https://github.com/mmBesar/DebianSway.git
```
```bash
cd DebianSway
```
```bash
./run.sh
```
يمكنك مشاهدة الشرح الكامل في هذا الفيديو [من هنا](https://youtu.be/GCDRZSFDFxo?si=H1icdc8yZpdrNnT7) إذا أردت تفاصيل أكثر.


## 4. تثبيت متجر التطبيقات ودعم Flatpak

### تثبيت Flatpak
```bash
sudo apt install flatpak
```

### إضافة مستودع Flathub (الأهم للحصول على أغلب التطبيقات)
```bash
sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

### تثبيت متجر التطبيقات (GNOME Software مع دعم Flatpak)
```bash
sudo apt install gnome-software gnome-software-plugin-flatpak
```

> يمكن تشغيله لاحقًا عبر: `gnome-software`

---

## 5. تثبيت البرامج الأساسية

### أدوات النظام الأساسية
```bash
sudo apt install curl wget unzip tar p7zip-full htop btop neofetch git
```

### المتصفحات
```bash
sudo apt install firefox-esr chromium
```
أو عبر Flathub:
```bash
flatpak install flathub org.mozilla.firefox
flatpak install flathub com.google.Chrome
```

### التواصل
```bash
flatpak install flathub com.discordapp.Discord
flatpak install flathub org.telegram.desktop
flatpak install flathub com.spotify.Client
```

### تحرير النصوص والتطوير
```bash
sudo apt install neovim nano vim
flatpak install flathub com.visualstudio.code
```

### ضغط وإدارة الملفات
```bash
sudo apt install file-roller ark
```

### تشغيل الوسائط
```bash
sudo apt install vlc mpv
```
أو:
```bash
flatpak install flathub org.videolan.VLC
flatpak install flathub io.mpv.Mpv
```

---

## 6. إعداد الجهاز للألعاب والبرمجة

### الألعاب (Gaming)
- تثبيت تعريفات الرسوميات:
  - **NVIDIA**:
    ```bash
    sudo apt install nvidia-driver firmware-misc-nonfree
    ```
  - **AMD / Intel** (موجودة عادةً افتراضيًا):
    ```bash
    sudo apt install firmware-amd-graphics firmware-linux
    ```
- تحسين الأداء:
  ```bash
  sudo apt install gamemode mangohud
  ```
- تشغيل الألعاب:
  ```bash
  sudo apt install steam lutris wine winetricks
  ```

### البرمجة
- تثبيت الأدوات الأساسية:
  ```bash
  sudo apt install build-essential git cmake python3 python3-pip
  ```
- منصات التطوير:
  ```bash
  sudo apt install neovim vscode
  ```
- Docker (اختياري):
  ```bash
  sudo apt install docker.io docker-compose
  ```

---

### برامج إضافية:
YouTube Apps - تطبيقات صناعة المحتوى

```bash
sudo apt install gimp audacity inkscape obs-studio kdenlive
```

 تثبيت برامج الإنتاجية والكتابة المتقدمة

### OnlyOffice
(أفضل عبر Flatpak لأحدث إصدار)
```bash
flatpak install flathub org.onlyoffice.desktopeditors
```

### Obsidian
```bash
flatpak install flathub md.obsidian.Obsidian
```

### TeX Live (كامل)
> ملاحظة: هذا إصدار كبير حجمه ~4GB
```bash
sudo apt install texlive-full
```

### Xournal++
```bash
sudo apt install xournalpp
```
أو نسخة Flathub:
```bash
flatpak install flathub com.github.xournalpp.xournalpp
```

---


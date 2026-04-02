# Work-case 4

# 1. Пакет і репозиторій

# Пакет — це архів із програмою, що містить виконувані файли,
# конфігурації, залежності та метадані (версія, опис тощо).

# Репозиторій — це сховище пакетів (офіційне або стороннє),
# з якого система завантажує і оновлює програми.

# Менеджери пакетів:
# APT  - Debian/Ubuntu (.deb)
# DNF  - Fedora/RHEL (.rpm)
# YUM  - застарілий RPM-менеджер
# Pacman - Arch Linux
# Zypper - openSUSE

# --------------------------------------------------

# 2. Менеджер пакетів (APT, Ubuntu)

# оновлення списку пакетів
sudo apt update

# оновлення системи
sudo apt upgrade

# пошук пакета
apt search package_name

# інформація про пакет
apt show package_name

# встановлення
sudo apt install package_name

# список встановлених
apt list --installed

# видалення
sudo apt remove package_name

# повне видалення
sudo apt purge package_name

# очистка залежностей
sudo apt autoremove

# додавання репозиторію
sudo add-apt-repository ppa:repo/name
sudo apt update

# --------------------------------------------------

# 3. Встановлення програм

# відеоплеєр
sudo apt install vlc

# Python
sudo apt install python3 python3-pip

# Java
sudo apt install openjdk-17-jdk

# --------------------------------------------------

# 4. Встановлення через графічне середовище

# Магазини:
# Ubuntu Software / GNOME Software / KDE Discover

# Кроки:
# 1) відкрити магазин
# 2) знайти програму
# 3) натиснути "Install"
# 4) ввести пароль (якщо потрібно)
# 5) дочекатися встановлення

# Працює з:
# - системними пакетами (APT)
# - Snap
# - Flatpak

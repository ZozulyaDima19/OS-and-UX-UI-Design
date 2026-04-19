# Work-case 6

## Робота з користувачами та командними інтерпретаторами в Linux

**Виконав:** студент групи РПЗ-33
**ПІБ:** Зозуля Дмитро

---

## Мета роботи

Ознайомитися з командними інтерпретаторами Linux, навчитися встановлювати альтернативні оболонки, створювати користувачів, керувати групами та налаштовувати права доступу.

---

# 1. Встановлення командних інтерпретаторів

## Обрані командні інтерпретатори:

* bash (за замовчуванням)
* zsh
* fish

---

## Команди для встановлення

sudo apt update
sudo apt install zsh fish -y

---

## Перевірка встановлення

cat /etc/shells

📸 *Скріншот списку доступних shell*

---

## Короткий опис інтерпретаторів

**Bash (Bourne Again Shell)**
Стандартна оболонка Linux. Підтримує скрипти, змінні, цикли, умови. Використовується для адміністрування системи.

**Zsh (Z Shell)**
Розширена оболонка з автодоповненням, підсвіткою синтаксису, плагінами. Зручна для розробників.

**Fish (Friendly Interactive Shell)**
Зручний інтерпретатор з підказками в реальному часі, автодоповненням без додаткових налаштувань, простий для новачків.

---

# 2. Створення користувачів та груп

## Створення груп

sudo groupadd tech_support
sudo groupadd developers
sudo groupadd financiers
sudo groupadd founders
sudo groupadd guests

📸 *Скріншот створення груп*

---

## Створення користувачів

sudo useradd -m user1
sudo useradd -m user2
sudo useradd -m user3
sudo useradd -m user4
sudo useradd -m user5
sudo useradd -m user6
sudo useradd -m user7
sudo useradd -m user8
sudo useradd -m user9
sudo useradd -m user10

📸 *Скріншот створення користувачів*

---

## Додавання користувачів до груп

sudo usermod -aG tech_support user1
sudo usermod -aG tech_support user2

sudo usermod -aG developers user3
sudo usermod -aG developers user4

sudo usermod -aG financiers user5
sudo usermod -aG financiers user6

sudo usermod -aG founders user7
sudo usermod -aG founders user8

sudo usermod -aG guests user9
sudo usermod -aG guests user10

📸 *Скріншот розподілу по групах*

---

# 3. Налаштування командних інтерпретаторів

## Перевірка шляхів до shell

which bash
which zsh
which fish
which nologin

---

## Призначення shell для користувачів

### Technical support – bash

sudo usermod -s /bin/bash user1
sudo usermod -s /bin/bash user2

---

### Developers – zsh

sudo usermod -s /bin/zsh user3
sudo usermod -s /bin/zsh user4

---

### Financiers – без доступу

sudo usermod -s /usr/sbin/nologin user5
sudo usermod -s /usr/sbin/nologin user6

---

### Founders – fish

sudo usermod -s /usr/bin/fish user7
sudo usermod -s /usr/bin/fish user8

---

### Guests – без доступу

sudo usermod -s /usr/sbin/nologin user9
sudo usermod -s /usr/sbin/nologin user10

📸 *Скріншот налаштування shell*

---

## Перевірка

cat /etc/passwd

📸 *Скріншот перевірки shell користувачів*

---

# 4. Демонстрація роботи користувачів

## Вхід під користувачем

su - user1

📸 *Скріншот входу*

---

## Приклади команд

### Системна інформація

uname -a

📸 *Скріншот результату*

---

### Дата і час

date

📸 *Скріншот результату*

---

### Поточний каталог

pwd

📸 *Скріншот результату*

---

### Вміст каталогу

ls -la

📸 *Скріншот результату*

---

## Перевірка обмежених користувачів

su - user5

📸 *Скріншот помилки (nologin)*

---

# Висновок

Під час виконання даної роботи було розглянуто процес встановлення додаткових командних інтерпретаторів, створення користувачів та їх розподіл по групах. Було налаштовано різні оболонки для різних категорій користувачів, а також обмежено доступ для окремих груп. Отримані навички дозволяють ефективно керувати доступом користувачів у Linux системі та підвищують рівень безпеки.

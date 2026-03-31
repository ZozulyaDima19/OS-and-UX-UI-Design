# Тема: “Команди Linux для архівування та стиснення даних. Робота з текстом”

## Мета роботи:

1. Отримання практичних навиків роботи з командною оболонкою Bash.  
2. Знайомство з базовими командами для архівування та стиснення даних.  
3. Знайомство з базовими діями при роботі з текстом у терміналі.

## Матеріальне забезпечення занять:
1. ЕОМ типу IBM PC.  
2. ОС сімейства Windows та віртуальна машина Virtual Box (Oracle).  
3. ОС GNU/Linux (будь-який дистрибутив).  
4. Сайт мережевої академії Cisco netacad.com та його онлайн курси по Linux

---

## Завдання для попередньої підготовки:

### 1. Словник термінів

| Term | Definition |
|-----|-----|
| Compression | The process of reducing the size of a file using algorithms. |
| Archiving | Combining multiple files into a single file for storage or transfer. |
| Lossless Compression | A method of compression that allows the original data to be fully restored. |
| Lossy Compression | A method that reduces file size by permanently removing some data. |
| gzip | A fast compression tool that uses the DEFLATE algorithm. |
| bzip2 | A compression tool that provides better compression but works slower than gzip. |
| xz | A compression tool that achieves very high compression ratios but requires more time and memory. |

---

## Теоретичні відповіді

**Яке призначення команд tar, xz, zip, bzip2, gzip?**  
tar - архівує файли в один файл без стискання; gzip - швидко стискає файли (.gz); bzip2 - стискає краще, але повільніше (.bz2); xz - дає найменший розмір, але найповільніший (.xz); zip - архівує і стискає одночасно (.zip).

**Основні параметри та встановлення**  
tar: -c (створити), -x (розпакувати), -t (перегляд), -f (файл); gzip: -d (розпакувати), -1…-9 (рівень); bzip2: -d, -k; xz: -d, -e; zip: -r (рекурсивно). Встановлення: `sudo apt install tar gzip bzip2 xz-utils zip`.

**Приклади архівування і стискання**  
tar czvf archive.tar.gz folder  
tar cjvf archive.tar.bz2 folder  
tar cJvf archive.tar.xz folder

**Яке призначення команд cat, less, more, head, tail?**  
cat - виводить весь файл; less - перегляд з прокруткою; more - простий перегляд посторінково; head - показує початок файлу; tail - показує кінець файлу.

**Основні параметри та встановлення**  
head: -n (рядки); tail: -n, -f (слідкування); less: зручна навігація; more: базовий перегляд. Встановлення: `sudo apt install coreutils less`.

**Поясніть принципи роботи каналів, потоків та фільтрів**  
Потоки: stdin (ввід), stdout (вивід), stderr (помилки). Канали (|) передають результат однієї команди в іншу. Фільтри — команди, що обробляють дані в потоці.

**Яке призначення команди grep?**  
grep — шукає текст за шаблоном у файлах або потоках, основні параметри: -i (ігнор регістру), -r (рекурсивно), -n (номер рядка).

---

## Хід роботи

### Таблиця команд

| Назва команди | Її призначення та функціональність |
|-----|-----|
| mkdir mybackups | Створення нової директорії **mybackups** у домашньому каталозі користувача |
| tar -cvf mybackups/udev.tar /etc/udev | Команда tar використовується для об’єднання кількох файлів |
| tar -tvf mybackups/udev.tar | Перегляд вмісту архіву |
| tar -xvf mybackups/udev.tar | Розпакування архіву |
| cat mymessage | Виводить вміст файлу |
| echo "Greetings" > mymessage | Записує текст у файл |
| find ~ -name "*bash*" | Шукає файли |
| find /etc -name hosts | Шукає файл |
| tr a-z A-Z | Перетворює текст |
| ls -l /etc \| more | Перегляд по сторінках |
| cut -d: -f1 /etc/passwd | Виводить перше поле |
| more /etc/passwd | Перегляд |
| less /etc/passwd | Розширений перегляд |
| tail /etc/passwd | Останні рядки |

---

### 3. Ознайомтесь з командою tar та за її допомогою виконати у терміналі наступні дії:

- створити файл з розширенням .tar  
  `tar -cvf archive.tar file1`
![](images/1.png)

- створити файл з розширенням .tar, що складається з декількох файлів і каталогів одночасно  
  `tar -cvf archive.tar file1 dir1 dir2`
![](images/2.png)

- перегляду вмісту файлу  
  `tar -tvf archive.tar`
![](images/3.png)

- витягти вміст файлу tar  
  `tar -xvf archive.tar`
![](images/4.png)

- створити архівний файл tar, стиснений за допомогою bzip  
  `tar -cjvf archive.tar.bz2 folder`
![](images/5.png)

- витягти вміст файлу tar bzip  
  `tar -xjvf archive.tar.bz2`
![](images/6.png)

- створити архівний tar файл, стиснений за допомогою gzip  
  `tar -czvf archive.tar.gz folder`
![](images/7.png)

- витягти вміст файлу tar gzip  
  `tar -xzvf archive.tar.gz`
![](images/8.png)

---

### Перенаправлення потоків

| Команда | Що виконує команда? |
|-----|-----|
| cmd 1> file | Перенаправляє stdout у файл |
| cmd > file | stdout у файл |
| cmd 2> file | stderr у файл |
| cmd >> file | додає stdout |
| cmd &> file | stdout + stderr |
| cmd > file 2>&1 | обидва потоки у файл |
| cmd >> file 2>&1 | додає обидва |
| cmd 2>&1 > /dev/null | stdout у null, stderr у stdout |
| cmd 2> /dev/null | ігнорує помилки |
| cmd1 \| cmd2 | передає дані |
| cmd1 2>&1 \| cmd2 | передає все |

---

### Аналіз команд

| Команда | Що виконує команда? | Який потік перенаправлення? |
|-----|-----|-----|
| echo "It is a new story." > story | Запис тексту | stdout |
| date > date.txt | Запис дати | stdout |
| cat file1 file2 file3 > bigfile | Об'єднання файлів | stdout |
| ls -l >> directory | Додавання у файл | stdout |
| sort < file1_unsorted > file2_sorted | Сортування | stdin + stdout |
| find -name '*.txt' > file.txt 2> /dev/null | Пошук без помилок | stdout + stderr |
| cat file1_unsorted \| sort > file2_sorted | Сортування | pipe |
| cat myfile \| grep student \| wc -l | Підрахунок | pipe |

---

## Контрольні запитання

1. Архівування — об’єднання файлів; стиснення — зменшення розміру.  
2. 7zip, rar, compress — альтернативні програми.  
3. gzip — швидкий; bzip2 — ефективніший; xz — найкращий коефіцієнт.  
4. ZArchiver, RAR — мобільні архіватори.  
5. WinRAR, 7-Zip — популярні в Windows.  
6. Використовується для резервного копіювання, передачі даних.  
7. /dev/null — файл для видалення даних.

---

## Висновок

У ході роботи було отримано практичні навички роботи з командами архівування, стиснення та обробки тексту в Linux. Ознайомлено з потоками введення/виведення та їх перенаправленням.

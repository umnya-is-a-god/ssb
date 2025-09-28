# Настройка клиента Sing-Box на Windows

### 1.1) Установка Sing-Box (Windows 10 и 11)

Нажмите Win + X, после этого откройте командную строку с правами аминистратора:

![w1](https://github.com/user-attachments/assets/52ac24b2-101e-4a4a-b45f-740582620fb3)

Далее введите команду:

```
winget install sing-box
```

После окончания установки командную строку можно закрыть (в дальнейшем можно обновлять Sing-Box той же командой).

Если на этом этапе возникла ошибка, предупреждающая об отсутствии winget, то следуйте инструкциям ниже.

-----

### 1.2) Установка Sing-Box (для версий Windows без winget)

Скачайте Sing-Box для Windows из официального репозитория:

https://github.com/SagerNet/sing-box/releases/latest

Далее извлеките sing-box.exe из архива.

-----

### 2) Создайте .cmd или .bat файл с таким содержимым:

```
@echo off
echo Started Sing-Box
echo Do not close this window while Sing-Box is running
echo Press Ctrl + C to disconnect
echo.
if not exist "C:\1-sbconfig\" mkdir C:\1-sbconfig
curl --silent -o C:\1-sbconfig\client.json https://example.com/secret175subscr1pt10n/username-VLESS-CLIENT.json
sing-box run -c C:\1-sbconfig\client.json
```

Ссылку в предпоследней строчке замените на свою.

Для версий Windows, где нет winget, замените последнюю строчку таким образом и поменяйте путь к sing-box.exe на свой:

```
C:\actual\path\to\sing-box.exe run -c C:\1-sbconfig\client.json
```

-----

### 3) Создайте ярлык для этого .cmd или .bat файла

Далее настройте ярлык, чтобы запускать его с правами администратора:

![w2](https://github.com/user-attachments/assets/131f8d9d-494f-4c67-850e-cf7e506f867c)

![w3](https://github.com/user-attachments/assets/ec6a3c3b-e3ab-4eda-86ef-24b780b6a17f)

![w4](https://github.com/user-attachments/assets/9b9f1338-71ba-4ce1-ac6e-6d18f4987816)

Везде нажмите OK.

-----

### 4) Для подключения к прокси просто нажмите на ярлык

Не нужно закрывать появившееся окно, пока ПК подключён к прокси.

Чтобы отключиться, нажмите на окно командной строки, а далее Ctrl + C.

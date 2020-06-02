# Ubuntu 20.04 GNOME

## 1.Обновляем систему.

Либо из приложений "Обновление приложений", либо через терминал: 

	sudo apt update && sudo apt upgrade

Перезагружаемся.

## 2. Устанавливаем программы

### Из центра приложений:

- **Ubuntu Tweaks**
- **Chromium**
- **ICQ**
- **WPS Office**
- **JivoSite**

### Отдельно

- **Remmina** - Для удаленного подключения (RDP, SSH)

		$ sudo apt-add-repository ppa:remmina-ppa-team/remmina-next
		$ sudo apt update
		$ sudo apt install remmina remmina-plugin-rdp remmina-plugin-secret	

- **Zoiper** - VoIP softphone  
Качаем и устанавливаем с сайта: https://www.zoiper.com/en/voip-softphone/download/current

- **SMB Client** - для подключения сетевого диска
  
        sudo apt install --install-recommends winehq-stable

После установки клиента необходимо прописать минимальный протокол, чтобы можно было подключаться к нашему серверу samba в терминале запускаем 

    sudo nano /etc/samba/smb.conf

И прописываем строчку `client min protocol = CORE`

    [global]

    ## Browsing/Identification ###

    # Change this to the workgroup/NT-domain name your Samba server will part of
        workgroup = WORKGROUP
        client min protocol = CORE
    # server string is the equivalent of the NT Description field
        server string = %h server (Samba, Ubuntu)

## 3. Установка расширений (если необходимо)

Установку расширений лучше всего производить из браузера Firefox  

[Список](https://github.com/tohondrik/Linux/blob/master/Gnom/more_extensions.md) некоторых расширений с их описанием и ссылками.

## 4. Дополнительные действия

### Установить медиа-кодеки для воспроизведения MP3, MPEG4 и других медиа-файлов

    sudo apt install ubuntu-restricted-extras

### Полная русификация

Необходимо зайти _**Настройки/Регион и язык/Управление установленными языками**_. Система автоматичеки предложит доустановить поддержку языков.

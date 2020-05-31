# Ubuntu 20.04 GNOME

## 1.Обновляем систему.

Либо из приложений "Обновление приложений", либо через терминал: 

	sudo apt update && sudo apt upgrade

Перезагружаемся.

## 2. Устанавливаем программы

- **Ubuntu Tweaks**
- **Chromium**
- **ICQ**
- **WPS Office**
- **JivoSite** - запускаем в вебе
- **Remmina** - Для удаленного подключения

	$ sudo apt-add-repository ppa:remmina-ppa-team/remmina-next
	$ sudo apt update
	$ sudo apt install remmina remmina-plugin-rdp remmina-plugin-secret	
	
- **WineHQ**

        $ sudo dpkg --add-architecture i386 
        $ wget -O - https://dl.winehq.org/wine-builds/winehq.key | sudo apt-key add -
        $ sudo add-apt-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ focal main'
        $ sudo apt install --install-recommends winehq-stable

- **MicroSip** (Устанавливать только после WineHQ)

        https://www.microsip.org/download/MicroSIP-Lite-3.19.30.exe

- **SMB Client**
  
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

## 3. Установка расширений

    https://linuxconfig.org/how-to-install-gnome-shell-extensions-on-ubuntu-20-04-focal-fossa-linux-desktop

**Пакет расширений** 

    sudo apt install gnome-shell-extensions

**Dash to panel** - панель как в windows 10

    https://extensions.gnome.org/extension/1160/dash-to-panel/

**Arc menu** - как пуск в windows

    https://extensions.gnome.org/extension/1228/arc-menu/

**TopIconFix** - убирает второй трей от Wine

    https://extensions.gnome.org/extension/1674/topiconsfix/
    
## 4. Дополнительные действия

### Установить медиа-кодеки для воспроизведения MP3, MPEG4 и других медиа-файлов

    sudo apt install ubuntu-restricted-extras

### Полная русификация

Необходимо зайти _**Настройки/Регион и язык/Управление установленными языками**_. Система автоматичеки предложит доустановить поддержку языков.

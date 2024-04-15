# OpiZero3_FMPoland

Obraz systemu Orange PiZero3 do FM Poland


Obraz zbudowany na bazie Armbian_community_24.5.0-trunk.403_Orangepizero3_bookworm_current_6.6.26_minimal

Plik obrazu .iso nagrać programem balenaEtcher https://etcher.balena.io/ na kartę # min 16GB!!!

Wgrany najnowszy dashboard oraz pliki dźwiękowe (z obrazów od SP2ONG) 

Logowanie po SSH
login: root
password: 1234
Dashboard http://IP_hotspota
IP adres możesz znaleźć przy pomocy darmowego narzędzia: https://www.advanced-ip-scanner.com/pl/
Domyślnie obraz przygotowany do pracy ze modyfikowaną karta dźwiękową CM108. 










Eksperymentalny obraz FM POLAND Raspberry PI v 2/3/4 

Obraz o nazwie **fmpoland-rpi.img.xz** nagrać na kartę microSD (8 Gb lub większa) przy pomocy: https://etcher.balena.io/

Login do konsoli via ssh:

user: pi

hasło: fmpoland

Zalecana zmiana hasła poleceniem: **passwd**

Dostęp do dashboard:

http://hotspot-fmpl.local/

lub

http://ip_adres

IP adres możesz znaleźć przy pomocy darmowego narzędzia: https://www.advanced-ip-scanner.com/pl/

Konfiguracja via Dashboard, należy wybrać z menu "Admin" i następnie: 

W pierwszej kolejności sprawdź poprawne ustawia obsługi SQL i PTT w menu

**SQL PTT"

Po sprawdzeniu / ustawieniu  SQL / PTT dopiero wtedy możesz przejść do konfiguracji:
"SVXCnf" - konfiguracja konta FM POLAND

"NodeInfo" - Informacje o stacji

"WEBCnf" - konfiguracja Dashboard

oraz inne opcje stosownie do potrzeb

CZYTAJ uważnie informacje umieszczone w każdym oknie z serii administracyjnych
w których są istotne informacje do dostępnych ustawień

![Admin Menu](https://github.com/FM-POLAND/hotspot-rpi-image/blob/main/admin-menu.png)

Obraz ten można używać z produktami SHARI i SHARI PiHat https://kits4hams.com/shari lub HotSpotRadio https://hotspotradios.com/purchase-parts lub USB-RMI https://www.repeater-builder.com/products/usb-rim-lite.html
Można używać do z kartą dźwiekową CM108 modyfikowana lub bez modyfikacji z dowolnym radiem

Domyślnie obraz przygotowany do pracy z modyfikowaną karta dźwiękową CM108

Dostępne konfiguracje:

Konfiguracja dla zmodyfikowanej karty CM108, sterowanie SQL i PTT via gpio CM108
czyli dla hotspotów na bazie SHARI, HotsporRadios z modułami SA818: 

/etc/svxlink/svxlink-cm108-mod.conf

Konfiguracja dla niezmodyfikowanej karty CM108 i sterowanie via GPIO RPI dla SQL i PTT:

/etc/svxlink/svxlink-gpio.conf

Należy zalogować się via SSH do RPI i skopiować wybrną konfiguracje na nazwę svxlink.conf i następnie konfigurować via Dashboard z menu "Admin"

Przykład:

sudo cp /etc/svxlink/svxlink-gpio.conf /etc/svxlink/svxlink.conf

lub

sudo cp /etc/svxlink/svxlink-cm108-mod.conf /etc/svxlink/svxlink.conf

Jeśli dashboard będzie dostępny z zewnątrz (należy przemyśleć to czy jest to ci niezbędne)  to aby dostać się do menu ADMIN należy w Admin -> WebCnf w opcji REMOTEIP zamiast adresu 127.0.0.1 wpisać zdalny zaufany IP adres (ZALECANE: można skorzystać z VPN [Tailscale](https://tailscale.com/) wersja personal zawiera darmową obsługę 3 userów/100 urzadzeń). Można też dostać z publicznego adresu do strony dashboard po linkiem

http://ipadresdashboard/svxc/

po podaniu użytkownika i hasła gdzie można wyłączyć lub włączyć zdalnie odbiornik SVXLINK. Jak założyć użytkownika i dla niego hasło patrz opis na swoim hotspot w pliku /etc/svxlink/SVXControl.txt

![Raspberry](https://github.com/FM-POLAND/hotspot-rpi-image/blob/main/rpi-login.png)





**Eksperymentalny obraz używasz na własną odpowiedzialność i autor nie ponosi odpowiedzialności za wykorzystane rozwiązanie i wynikające z niego skutki.**

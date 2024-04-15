# OpiZero3_FMPoland

Obraz systemu Orange PiZero3 do FM Poland

![Zero3-img3-1](https://github.com/SP4MN/OpiZero3_FMPoland/assets/166878544/611f54d7-f2cf-4572-adec-044a27b51fa5)

Obraz zbudowany na bazie Armbian_community_24.5.0-trunk.403_Orangepizero3_bookworm_current_6.6.26_minimal

Plik obrazu .iso nagrać programem balenaEtcher https://etcher.balena.io/ na kartę **min 16GB**!!! 

Wgrany najnowszy dashboard oraz pliki dźwiękowe (z obrazów SP2ONG https://github.com/FM-POLAND/hotspot-rpi-image/releases ) 

Logowanie po SSH przez np. PuTTy https://www.putty.org/ 

**login: root**

**password: 1234**

Dashboard http://IP-hotspota 

IP adres możesz znaleźć przy pomocy darmowego narzędzia: https://www.advanced-ip-scanner.com/pl/ lub wysyłając do hotspota kod DTMF **30#**

Domyślnie obraz przygotowany do pracy ze modyfikowaną kartą dźwiękową CM108

![NEWcm108-diag](https://github.com/SP4MN/OpiZero3_FMPoland/assets/166878544/1e18b68e-740a-41d2-97f6-8ec342d9bbe3)


Konfiguracja:
1. Ustawić poprawne SQL/PTT (przez dashboard)
2. wyedytować plik svxlink.conf
 
	 **sudo nano /etc/svxlink/svxlink.conf**
   
   (w edytorze nano klawisz F3 zapisuje plik, a klawisz F2 zamyka edytor)

   W części [SimplexLogic] musisz wpisać swój znak w CALLSIGN= zamiast N0CALL

   [SimplexLogic]

   TYPE=Simplex

   RX=Rx1

   TX=Tx1

   CALLSIGN=N0CALL

   **Aby otrzymać konto na FM POLAND musisz zarejestrować się w seci https://fm-poland.pl/rejestracja-fm-poland/**

   Otrzymane dane wpisuje się w części [ReflectorLogic] w pliku konfiguracyjnym svxlink.conf.
   
  	[ReflectorLogic]

  	TYPE=Reflector

  	HOSTS=reflector.fm-poland.pl,reflector.fm-poland.noip.pl

  	HOST_PORT=5295

  	CALLSIGN="N0CALL"

  	AUTH_KEY="My_PASSWORD"

  W części [ReflectorLogic] wpisz w MONITOR_TGS jakie inne dostępne TalkGroup będzie monitorował hotspot
  
  MONITOR_TGS=112+++,260,2600

3. konfiguracja "NodeInfo" - Informacje o stacji

   **sudo nano /etc/svxlink/node_info.json**

   wpisać tu dane hotspota zgodnie z poradnikiem http://www.fm-poland.pl/plik-node_info-json/ 

5. konfiguracja "WEBCnf" - konfiguracja wyglądu Dashboard (nagłówek itp.)

   po wszystkich konfiguracjach zrestarować SVXLink
   
	**sudo systemctl restart svxlink.service**

   
   Do usłyszenia na grupie Sierra Echo 260077, 73... :-)

  
   Michał SP4MN 

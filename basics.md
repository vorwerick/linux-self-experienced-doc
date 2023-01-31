# Základy práce v černém poli

## Prolog
Stal si se poutníkem ve světě negrafického prostředí, tvá cesta bude trnitá a nebezpečná.
Pouze sobě samému můžeš dokázat svoji odvahu, nikoho jiného to nezajímá. Pusť se do učení binbeš.
Tvé kroky nechť jsou osvíceny ochranou učení a znalostí, které ti dává. 
Drž chůzi.

## 1. Adresáře

`pwd`
- příkaz pwd ti vypíše absolutní cestu ukazatele (to je tam kde se nacházíš)
- absolutní znamená že jde od rootu /home/Hege/Documents/education/bbc.mp4
- relativní cesta je že jsi již v adresáři /home/Hege a relativní cesta k souboru by byla pouze Documents/education/bbc.mp4

`cd`
- změní cestu adresář (ukazatel)
- jsi v /home/Hege dáš cd Documents/education a ocitneš se v /home/Hege/Documents/education
- cd .. udělá zpět (o složku výš)

`ls`
- zobrazí soubory a složky v adresáři
- jsme v /home/Hege/Documents/education dáš cd a vypíše se bbc.mp4
- pokud hledáš v cizím adresáři než ve kterém jsi zadáš absolutní cestu
- ls -a ti ukáže i skryté soubory a složky
- ls -lh vypíše s informacemi

## 2. Soubory

`touch`
- udělá soubor
- touch /home/Hege/Documents/jidelnicek.txt

`mkdir`
- mkdir foldername vyrobí složku

`cat`
- veme obsah souboru a vypíše ho cat filename.txt
- pokud bude potřeba výpis uložit do jiného souboru dáš cat > soubor.txt
- ten zobák dělá to že veme výstup příkazu cat a pošle ho jako vstup do souboru

`cp`
- kopírování cp filename1.txt filename2.txt
- ze stažených souborů do připravené složky cp /home/Hege/Downloads/bbc.mp4 /home/Hege/Documents/education/bbc.mp4

`mv`
- to samý jako kopírování akorát přesouvá

`rm`
- maže rm filename
- více najednou rm filename1 filename2 filename3
- složky a obsah s podložkama se maže rekurzivně jen přidáš k rm -rf
- máš /home/Hege/Documents/education/bbc.mp4 a chceš smazat celou složku Documents včetně obsahu rm -rf /home/Hege/Documents

`find`
- najde gďe máš soubor
- find KDE -name CO příklad: find /home/Hege -name Starwars-7-sila-se-probouzi-CZ-dab.mp4

`grep`
- najde řádky kde se vyskytuje hledaný výraz v souboru(textu)
- grep koprovka /home/Hege/Documents/jidelnicek.txt

`tar`
- tar je ekvivalent zipu
- pouziva se v zasade s parametrama -cvf rovnou ti to extrahuje do nové složky
- tar -cvf /home/Hege/Downloads/soubor.tar /home/user/Documents tím se ti obsah taru extrahuje do složky Documents

`nano`
- vim neumim tak píšu o nano
- nano filename.txt
- ukončení nana je ctr-x pak se tě zeptá Y/N jestli uložit

## 3. Uživatelé

`sudo`
- píšeš před příkazama na který nemáš oprávnění
- to tě vyzve k zadání hesla a tím se authorizuješ že seš bůh a že umíš
- když neumíš ruce pryč

`chmod`
- upravuje oprávnění souboru
- chmod 777 /home/Hege/Documents/jidelnicek.txt nastaví max oprávnění (read, write, execute)
- muzes uživat -rwxrwxrwx
- já nevíc použival chmod -x /home/Hege/Documents/prikaz.sh to je když nemáš oprávnění spouštět binbeš a potřebuješ jenom to

`chown`
- zmeni vlastnika souboru chown ales filename.txt

`useradd`, `userdel`, `passwd`
- novy uzivatel/smazani
- useradd ales kdyz mu chces nastavit heslo das rovnou passwd 1234
- userdel ales
- passwd je password changer

`whoami`
- aktualni user

`getent passwd`
- vypis uzivatelu z databaze hesel /etc/nsswitch.conf

`su`
- přepne uživatele

## 4. Systém

`top`
- top je ekvivalent task manageru (správce úloh) informaco o bezicich procesech a zatez stroje

`clear`
- vycisti obrazovku terminalu

`ping`
- overi dostupnost pripojeni ping google.com

`du`
- vyuziti disku du /home/Hege/Documents vypise vyuziti disku jednotlivych souboru
- du -s /home/Hege/Documents vypise celkovou velikost slozky Documents

`ssh`
- remote ovládání vzdáleného linuxu
- ssh username@address (dá se doplnit o další parametry)
- já používal třeba ssh pi@192.168.8.113 pak se tě to zeptá na heslo uživatele a seš tam
- přikazem exit vypneš

`dnf`
- instalace balíčku rpm
- update repozitáře sudo dnf update
- hledání balíčku sudo dnf search balicek
- instalace sudo dnf install balicek

`wget`
- stahování souboru z webu
- wget https://pornhub.com/bbc.mp4

`curl`
- volání http requestů

`reboot`
- restart systému

`df`
- informace o disku

`ifconfig`
- informace o síťových rozhraních
- ifconfig -a vypíše všechna síťová rozhraní
- spuštění rozhraní eth0 ifconfig eth0 up
- vypnutí rozhraní eth0 ifconfig eth0 down
- nastavení adresy rozhraní eth0 ifconfig eth0 192.168.0.1
- nastavení masky rozhraní eth0 ifconfig eth0 netmask 255.255.255.224
- nastaveni gateway rozhraní eth0 ifconfig eth0 broadcast 192.168.0.0

`history`
- vypíše seznam spuštěných příkazů v minulosti

`date`
- výpis času a datumu


## 5. Tipy

- #!/bin/bash takto začíná script v souboru
- soubor scriptu musí mít koncovku .sh
- script spouštíme ./skript.sh nebo s absolutní cestou ./home/Hege/Documents/skript.sh
- pokud neni permission nastavíme oprávnění ke spuštění sudo chmod +x skript.sh
- při psaní cesty adresáře používej TAB pro doplňování názvů souborů a složek
- ctrl-c ukončení běžícího příkazu/skriptu
- ctrl-r + text rekurzivní vyhledávání spuštěných příkazů v minulosti
- ctrl-a posune kurzor psaní na začátek
- ctrl-e posune kurzor psaní na konec
- ctrl-d zavře terminál session
- šipky nahoru a dolu pro procházení historie příkazů
- pouštění více příkazů v jednom řádku nezávsile command1; command2; command3
- pouštění více příkazů v jednom řádku s čekáním na dokončení předchozího command1 && command2 && command3

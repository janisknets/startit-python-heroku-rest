## Heroku
- Īsā versija ↓
- Padziļinātā versija →
+++
#### Īsā versija I - GIT repozitorija klonēšana
@ul
- [Atveram sākotnējo repozitoriju]()
- Nospiežam "Fork" labajā augšējā stūrī.
- Nospiežam "Refresh", ja nepieciešams.
- Klonējam repozitoriju uz sava datora - Clone or download.
- Atveram Github Desktop.
- Nospiežam "File", tad "Clone repository".
- Izvēlamies svaigi izveidoto repozitoriju.
@ulend
+++
#### Īsā versija II - Heroku izveidojam lietotni
@ul
- [Reģistrācija Heroku](https://signup.heroku.com/)
- Apstiprina konta izveidi no reģistrētā e-pasta.
- [Heroku panelī](https://dashboard.heroku.com/apps) izvēlas "Create new app".
- Izveido nosaukumu - šis nosaukums būs interneta adreses sastāvdaļa, izvēlieties kaut ko atbilstošu projektam, piemēram, "mans-chats".
- Izvēlas reģionu - Europe.
- Nospiež "Create App".
@ulend
+++
#### Īsā versija III - Sasaistām Heroku ar GIT
@ul 
- Jaunizveidotās aplikācijas tabā "Deploy" atrod sadaļu "Deployment method" un izvēlas GitHub (Connect to GitHub).
- Pievieno savu GitHub repozitoriju, pārbauda, ka pareizais repozitorijs rādās sadaļā "App connected to GitHub".
- Sadaļā "Automatic deploys" pārbauda, ka ir izvēlēts zars "master" un nospiež "Enable Automatic deploys" - tagad pēc katra commit vai merge uz *master* zaru tas tiks automātiski palaists uz Heroku servera (paiet apmēram 30-60 sekundes).
@ulend
+++
#### Īsā versija IV - Darbības pārbaude
@ul
- Tabā "Deploy" sadaļā "Manual deploy" nospiežam "Deploy" un pagaidām.
- Ja parādās ziņa "Your app was successfully deployed.", nospiežam pogu "Open App" labajā augšējā stūrī.
- Ja viss strādā - urā!
- Ja rāda kļūdu, Heroku lapā nospiežam labajā augšējā stūrī uz pogas "More" un izvēlamies "View Logs".
@ulend

---

## Padziļinātā versija

---
@snap[north]
### Nepieciešamās instalācijas
@snapend
- Python
- Pip
- Heroku

---
@snap[north]
#### Kā iegūt Python
@snapend
- [Python lejuplāde](https://www.python.org/ftp/python/3.8.0/python-3.8.0-amd64.exe)
- Izpildām instalēšanas soļus
- Pārbaudām konsolē ar
```bash
python --version
```


---
@snap[north]
#### PIP lejuplāde un instalēšana
@snapend
- Lai šis darbotos, ir jābūt strādājošam python
- [Lejuplādējam get-pip.py](https://bootstrap.pypa.io/get-pip.py)
- Atveram powershell
- Pārvietojamies uz lejuplāžu mapi
```bash
cd C:\\Users\\Janis\\Downloads
```
- Izpildām 
```bash
python get-pip.py
```
- Pārbaudām, vai viss OK
```bash
pip -V
```
- [Pamācība angļu valodā](https://www.liquidweb.com/kb/install-pip-windows/)
---
@snap[north]
#### Lejuplādējam Heroku CLI
@snapend
- [Detalizēta pamacība no Heroku](https://devcenter.heroku.com/articles/heroku-cli)
- Pārbaudām, vai ir uzinstalēts
```bash
heroku --version
```

---
@snap[north]
### Nepieciešamās bibliotēkas
@snapend
```bash
pip install flask
pip install python-dotenv
pip install gunicorn
```

---
@snap[north]
### Izveidojam Heroku lietotni
@snapend
```bash
heroku create
git clone
```
---
@snap[north]
### Heroku konfigurācija
@snapend
@ul
- @gitlink[requirements.txt](requirements.txt)
- @gitlink[runtime.txt](runtime.txt)
- @gitlink[Procfile](Procfile)
- @gitlink[Procfile.windows](Procfile.windows)
@ulend

---
@snap[north]
#### Heroku komandas lokāli I
@snapend
- Izveidojam jaunu app 
```bash
heroku create [LIETOTNES NOSAUKUMS ŠEIT]
heroku create mana-lietotne
```
- Pārbaudām
```bash
heroku apps
```
- Veicam izmaiņas mūsu pirmkodā
- Ieliekam izmaiņas git repozitorijā
```bash
git add . && git commit && git git push origin master
```
---
@snap[north]
#### Heroku komandas lokāli II
@snapend
- Aktivizējam heroku serveri 
```bash 
heroku ps:scale web=1 -a mana-lietotne
```
- Pārbaudām, vai viss strādā 
```bash
heroku open -a mana-lietotne
```
- Apskatām heroku "logus"
```bash
logs -a mana-lietotne --tail
```

---

## Paldies!

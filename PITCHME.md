## Heroku
- Īsā versija ↓
- Padziļinātā versija →
+++
#### Īsā versija I - GIT repozitorija klonēšana
@ul
- [Atveram sākotnējo repozitoriju]()
- Nospiež "Fork" labajā augšējā stūrī.
- Nospiež "Refresh", ja nepieciešams.
- Klonē repozitoriju uz sava datora - Clone or download.
- Atver GitHub Desktop.
- Nospiež "File", tad "Clone repository".
- Izvēlas tikko izveidoto repozitoriju.
@ulend
+++
#### Īsā versija II - Heroku lietotnes izveidošana
@ul
- [Reģistrācija Heroku](https://signup.heroku.com/)
- Apstiprina konta izveidi no reģistrētā e-pasta.
- [Heroku panelī](https://dashboard.heroku.com/apps) izvēlas "Create new app".
- Izveido nosaukumu - šis nosaukums būs interneta adreses sastāvdaļa, tas jāizvēlas atbilstošs projektam, piemēram, "mans-chats".
- Izvēlas reģionu - Europe.
- Nospiež "Create App".
@ulend
+++
#### Īsā versija III - Heroku sasaistīšana ar GIT
@ul 
- Jaunizveidotās lietotnes tabā "Deploy" atrod sadaļu "Deployment method" un izvēlas GitHub (Connect to GitHub).
- Pievieno savu GitHub repozitoriju, pārbauda, ka pareizais repozitorijs rādās sadaļā "App connected to GitHub".
- Sadaļā "Automatic deploys" pārbauda, ka ir izvēlēts zars "master" un nospiež "Enable Automatic deploys" - tagad pēc katra commit vai merge uz *master* zaru tas tiks automātiski palaists uz Heroku servera (pēc apmēram 30-60 sekundēm).
@ulend
+++
#### Īsā versija IV - Darbības pārbaude
@ul
- Tabā "Deploy" sadaļā "Manual deploy" nospiež "Deploy" un pagaida.
- Ja parādās ziņa "Your app was successfully deployed.", nospiež pogu "Open App" labajā augšējā stūrī.
- Ja viss strādā - urā!
- Ja rāda kļūdu, Heroku lapā labajā augšējā stūrī nozpiež uz pogas "More" un izvēlas "View Logs".
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
#### Kā iegūt Python?
@snapend
- [Python lejuplāde](https://www.python.org/ftp/python/3.8.0/python-3.8.0-amd64.exe)
- Izpilda instalēšanas soļus.
- Pārbauda konsolē ar
```bash
python --version
```


---
@snap[north]
#### PIP lejupielāde un instalēšana
@snapend
- Lai šis darbotos, ir jābūt strādājošam python.
- [Lejupielādē get-pip.py](https://bootstrap.pypa.io/get-pip.py)
- Atver powershell.
- Pārvietojas uz lejupielāžu mapi
```bash
cd C:\\Users\\Janis\\Downloads
```
- Izpilda
```bash
python get-pip.py
```
- Pārbauda, vai viss OK
```bash
pip -V
```
- [Pamācība angļu valodā](https://www.liquidweb.com/kb/install-pip-windows/)
---
@snap[north]
#### Lejupielādē Heroku CLI
@snapend
- [Detalizēta pamacība no Heroku](https://devcenter.heroku.com/articles/heroku-cli)
- Pārbauda, vai ir uzinstalēts
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
### Izveido Heroku lietotni
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
- Izveido jaunu app 
```bash
heroku create [LIETOTNES NOSAUKUMS ŠEIT]
heroku create mana-lietotne
```
- Pārbauda
```bash
heroku apps
```
- Veic izmaiņas pirmkodā.
- Ieliek izmaiņas GIT repozitorijā
```bash
git add . && git commit && git git push origin master
```
---
@snap[north]
#### Heroku komandas lokāli II
@snapend
- Aktivizē Heroku serveri 
```bash 
heroku ps:scale web=1 -a mana-lietotne
```
- Pārbauda, vai viss strādā 
```bash
heroku open -a mana-lietotne
```
- Apskata heroku "logus"
```bash
logs -a mana-lietotne --tail
```

---

## Paldies!

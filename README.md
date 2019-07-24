# Zavrsni_SCADA-WebApp
Early warning SCADA sub-system

Web aplikacija:  
Node.js  v.10.15.1 (back end)
Express.js, Socket.io, Axios, Sequelize ORM
Vue.js  v. 2.6.10 (front end)
Bootstrap,  Bootstrap-vue, pg, vue-google-charts, vuex, socket.io-client, vue-socket.io, vue-router, eslint-plugin-vue 

Baza podataka:
PostgreSQL v11.4
pgAdmin

Zavojni alat:
Visual studio code v.1.36.1

Osnovna ideja projekta:
- Na razini SCADA sustava, razviti podsustav za ranu detekciju kritične situacije u proizvodnom procesu koji se kontrolira putem PLC-a i komponenti SCADA sustava (Human Machine Interface).
- Omogućiti operateru koji nadgleda proizvodni proces, da u trenutku kritične situacije koja nije pokrivena standardnim mjerama dojave (alarm menadžment, sigurnosni preduvjeti i sl.) reagira registriranjem iste, na način da evidentira vrijeme i parametre koji su ključni za nastanak kritične situacije.
- Vršiti monitoring unesenih ključnih parametara u realnom vremenu (podaci iz PLC-a), te generirati upozorenje u slučaju da se isti približe pohranjenom modelu kritične situacije. 
- Razviti aplikaciju temeljenu na besplatnom softveru otvorenog koda (izravna komunikacija prema PLC-u).
- Podržati barem jedan tip PLC-a koji je opće prisutan na tržištu (Siemens S7 serije 300, 400, 1500).

Osnovni zahtjevi:
- Sustav ne mora biti univerzalno primjenjiv na sve grane industrije. Dovoljno je da bude primjenjiv općoj industriji (relativno spori procesi sa ciklusima čitanja do cca 600ms).
- Mogućnost pohrane podataka u zasebnu relacijsku bazu (neovisna od postojećih sustava).
- Dostupnost na razini LAN-a (ICS + corporate network).
- Besplatni razvojni alati
- Mala veličina aplikacije (footprint).
- Zaseban modul za komunikaciju prema PLC-u  
- Web aplikacija (internetski preglednik) radi lakše nadogradnje.

Izračun kritične situacije za pojedini signal(tag):
Vjerojatnost nastupa kritičnog događaja računa se putem trenda porasta/pada vrijednosti signala u zadanom vrem. Periodu(time span) za danu kritičnu situaciju, koji se računa iz razlike aktualne vrijednosti i prosječne za zadani vrem. period. 
Ukoliko se pod zadanim uvjetima, aktualna vrijednost približi kritičnoj (80% ili 120%), ostvaruju se uvjeti upozorenja (samo za promatrani signal).
Upozorenje se generira kada se ispune uvjeti za sve promatrane tagove(signale)







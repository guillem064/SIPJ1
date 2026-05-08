
# MONITORITZACIÓ, CONNEXIÓ I LLICENCIAMENT

### logger[opcions][p-prioritat][missatge]

### logger -i -s -p mail.err Aturant el sistema

### Servei.prioritat acció

### auth
### mail
### lpr
### cron
### kern
### cron
### …

### (prioritat de + petita a + gran)

### debug
### infor
### notice
### warning, warn
### err, error
### crit
### alert
### emerg, panic
 

### Entrar al sistema de procesos i fer captures

<img width="697" height="107" alt="Captura de pantalla de 2026-05-05 11-46-07" src="https://github.com/user-attachments/assets/71133529-baca-471f-aaab-c0e9d55e1f5d" />

<img width="706" height="449" alt="Captura de pantalla de 2026-05-05 11-49-09" src="https://github.com/user-attachments/assets/e3af0ead-c62e-4af9-9fcf-b639143fa356" />

### cv /var/log
### ls
### //al syslog van tots els logs

<img width="609" height="166" alt="Captura de pantalla de 2026-05-05 11-48-16" src="https://github.com/user-attachments/assets/d4507553-c37d-4cdf-b6f9-5a796c1b17f0" />

### (obrim dos terminals)
### nova 
### tail -f /var/log/syslog

<img width="738" height="436" alt="Captura de pantalla de 2026-05-05 11-56-24" src="https://github.com/user-attachments/assets/2e626e02-7df0-4567-9ec0-4e64e05276ff" />

### antiga
### logger -i -s -p mail.err Mail ha fallat

<img width="674" height="51" alt="Captura de pantalla de 2026-05-05 11-59-42" src="https://github.com/user-attachments/assets/9f93ad9c-705f-4c79-a0c9-0a97a1921536" />

### nova
### {CAPTURA del missatge de error}
<img width="687" height="54" alt="Captura de pantalla de 2026-05-05 12-00-33" src="https://github.com/user-attachments/assets/1b76ac4c-1b97-48d7-8b13-8b7c4b90e144" />


### antiga
### nano /etc/rsyslog.d/50-default.conf
### mail.* -> mail.crit

<img width="527" height="319" alt="Captura de pantalla de 2026-05-05 12-01-57" src="https://github.com/user-attachments/assets/244cb441-97ea-4fd2-942c-8073704b411e" />

### systemctl restart rsyslog
### logger -i -s -p mail.err Mail ha fallat2
### nova
### {CAPTURA del missatge de error}
<img width="676" height="36" alt="image" src="https://github.com/user-attachments/assets/c475caf4-87bc-4c3e-b780-5d7982fadb88" />


### antiga
### nano /etc/rsyslog.d/50-default.conf
### mail.crit -> mail.=crit
### systemctl restart rsyslog
### logger -i -s -p mail.err Mail ha fallat3
### systemctl restart rsyslog
### logger -i -s -p mail.err Mail ha fallat4
### systemctl restart rsyslog
### logger -i -s -p mail.err Mail ha fallat5
### cat /var/log/mail.log

<img width="670" height="137" alt="Captura de pantalla de 2026-05-05 12-02-44" src="https://github.com/user-attachments/assets/c6c8a43d-b386-42d8-932a-a00dd7e939a6" />


### nova
### {CAPTURA del missatge de error}
<img width="506" height="121" alt="Captura de pantalla de 2026-05-05 12-04-17" src="https://github.com/user-attachments/assets/e41f334d-1404-4286-ac98-7d3513a9c02b" />


### antiga
### nano /etc/rsyslog.d/50-default.conf
### *.crit 		/var/log/mireia.log

<img width="559" height="347" alt="Captura de pantalla de 2026-05-05 12-05-57" src="https://github.com/user-attachments/assets/82a97466-2207-449e-ad2b-399a4d7ed17a" />

### systemctl restart rsyslog
### logger -i -s -p cron.notice Este no
### logger -i -s -p auth.alert Este si
### cat /var/log/mireia.log
<img width="624" height="152" alt="Captura de pantalla de 2026-05-05 12-07-28" src="https://github.com/user-attachments/assets/c37221eb-e074-4b44-b10e-9e72b53a00f4" />

# SIMULAR UN SERVIDOR CENTRALITZAT DE LOGS

### Per començar canviarem els adaptadors de xarxa de les dos màquines per a que es puguin connectar fican com adaptador 1 Xarxa NAT i adaptador 2 Xarxa Interna

<img width="485" height="247" alt="Captura de pantalla de 2026-05-05 12-29-59" src="https://github.com/user-attachments/assets/27e2c5bb-ede8-4431-b1fa-8cb4fd8d15a6" />

<img width="485" height="247" alt="Captura de pantalla de 2026-05-05 12-20-55" src="https://github.com/user-attachments/assets/82511f69-b1ff-482e-ae70-070535f96822" />

### La nostra màquina server tindra la IP següent

<img width="186" height="42" alt="image" src="https://github.com/user-attachments/assets/44a7c449-2409-4816-91bf-55fe7a677e8c" />

### La nostra màquina client tindra la IP següent

<img width="183" height="34" alt="image" src="https://github.com/user-attachments/assets/b522b0e4-8138-4c96-8013-6391303fa601" />

### Fem un ping del servidor al client 

<img width="600" height="233" alt="image" src="https://github.com/user-attachments/assets/73a97ad0-e905-4414-ad8c-c701db047c9c" />

### Fem un ping del client al servidor

<img width="576" height="230" alt="image" src="https://github.com/user-attachments/assets/c1576c64-0d0f-4a51-ac2b-af2cf0d35e86" />

### Ens instal·lem el rsyslog a les dos màquines sino el tenim

<img width="518" height="32" alt="image" src="https://github.com/user-attachments/assets/d03a2e93-b671-46ea-a97f-354ebf54524c" />

<img width="522" height="26" alt="image" src="https://github.com/user-attachments/assets/ee21cece-ddf3-4cd8-8674-3726ba527674" />

## SERVIDOR

### Seguidament entrarem editant al fitxer /etc/rsyslog.conf al qual afegirem una norma per a que els logs remots vaiguen al programa directament i que després para i treurem els hashtags de les linies de module TCP i input TCP per a que ens puguin arribar els logs remots.

<img width="718" height="546" alt="image" src="https://github.com/user-attachments/assets/3b544511-e0c8-43ce-bda3-8dbe0aa93ec5" />

### Una vegada fet que puguin arribar els logs per a que puguin passar el firewall ficarem la següent comanda

<img width="433" height="58" alt="image" src="https://github.com/user-attachments/assets/f0196f9f-39cd-450f-9cda-91e9669943ac" />

### Reiniciem el servei

<img width="557" height="22" alt="image" src="https://github.com/user-attachments/assets/5f9ca655-0000-439a-86f7-a6bfaf5b3c12" />

### Ara al fer la següent comanda observem que el servidor esta escoltant el port TCP que hem habilitat i ja podrien estar entrant els Logs Remots

<img width="918" height="63" alt="image" src="https://github.com/user-attachments/assets/24ce64a6-213c-46e8-8a08-5db0339356bd" />

## CLIENT

### Entrarem al fitxer següent editant-lo i ficarem una linia per a enviar tots els logs al servidor

<img width="786" height="170" alt="image" src="https://github.com/user-attachments/assets/2fad2b40-19c1-4ca0-90b3-4b8893ffd718" />

### Ara reiniciarem el servei per a que es guardi tot i s'apliqui

<img width="583" height="27" alt="image" src="https://github.com/user-attachments/assets/2e5fad88-6bc4-4159-8edc-601bb41874ec" />

### Per acabar farem la prova de si funciona, crearem un Log (logger "Hola sóc un client") i fem un tail dels registres i hauria de sortir alli el nostre log

<img width="750" height="235" alt="image" src="https://github.com/user-attachments/assets/25030b73-aaaf-48a5-99e9-4d976a925dd1" />

## SERVIDOR

### Ara al servidor haurem d'anar al directori /var/log per a veure si s'ha creat la nostra carpeta amb els logs remots del client i com podrem veure a la captura d'abaix tenim creada la carpeta amb el nom del client (Ubuntu222)

<img width="1022" height="138" alt="image" src="https://github.com/user-attachments/assets/baf537bf-3e81-458b-8df7-dee28c855ba8" />

### Entrem a la carpeta i veurem que tenim varis fitxer creats mirarem el fitxer de root que es l'usuari amb el que hem fet el logi hauria de sortir el log dins del fitxer.

<img width="754" height="61" alt="image" src="https://github.com/user-attachments/assets/c19f5fdd-a637-4c2b-8123-d923df73152a" />

### I confirmem que si tenim el Log creat i ja tindriem el nostre servidor de logs centralitzat.

<img width="561" height="41" alt="image" src="https://github.com/user-attachments/assets/f9cf3573-cd9c-4cbf-96ec-d9b979a74e09" />


# SSH i VNC











## VNC

## SERVIDOR

### Primer instal·larem el x11vnc server al servidor

<img width="509" height="24" alt="image" src="https://github.com/user-attachments/assets/e7b9ca93-7abe-4934-8a17-64849cb44097" />

### Seguidament el que farem sera crear una carpeta per al vnc i guardar alli la contrasenya que volem ficar-li (la meva es 1234)

<img width="611" height="61" alt="image" src="https://github.com/user-attachments/assets/b265c6a0-27e6-4035-a66b-f329f45b49bb" />

### Crearem un fitxer per a fer un servei del x11vnc

<img width="599" height="26" alt="image" src="https://github.com/user-attachments/assets/ad35112d-c601-4ab3-953d-c068f4d5a3e9" />

### Dins del fitxer escriurem unes linies que serviran com a descripció del servei, que si no fiquem la contrasenya correcta es reseteji i que es pugui instal·lar a varis usuaris

<img width="769" height="233" alt="image" src="https://github.com/user-attachments/assets/7873df90-15ae-4953-a5ae-f13601e73952" />

### enable i start

<img width="1025" height="84" alt="image" src="https://github.com/user-attachments/assets/b762b098-47d3-4808-8ea7-4d5abf0a4959" />

### Actualitzem els permisos del Firewall 

<img width="378" height="63" alt="image" src="https://github.com/user-attachments/assets/10816a3a-c713-4333-917d-d164b4b14174" />

### Si tenim una màquina virtual que sigui Ubuntu 24.04 o superior haurem de desactivar el Wayland entrant al següent fitxer

<img width="502" height="26" alt="image" src="https://github.com/user-attachments/assets/7c6bc234-d918-474b-a259-8e4011fdc168" />

<img width="741" height="163" alt="image" src="https://github.com/user-attachments/assets/c98ced42-6a72-4d8f-be3a-26faa98c30e3" />

### Fem un reboot per resetejar tot i que es guardi

<img width="321" height="23" alt="image" src="https://github.com/user-attachments/assets/923c541c-4a75-494f-b175-d04aa408d5d8" />

## CLIENT 

### Al client obrirem la terminal i instal·larem un client VNC (Jo utilitzo el TigerVNC)

<img width="593" height="30" alt="image" src="https://github.com/user-attachments/assets/b128a680-d986-4296-8401-b41b62b40c4b" />

## SERVIDOR

### Ficarem aquesta comanda per obrir el el VNC 

<img width="683" height="22" alt="image" src="https://github.com/user-attachments/assets/de8611b5-641c-4d2a-99f8-eeea0a323950" />

## CLIENT

### Ara fiacrem la següent comanda per a que es pugui conectar al servidor

<img width="436" height="27" alt="image" src="https://github.com/user-attachments/assets/54adea94-fe62-4789-bd06-07431609b58e" />

<img width="416" height="172" alt="image" src="https://github.com/user-attachments/assets/74a10816-7210-4a64-b753-08727ce17e46" />

### I ja estariem conectats per VNC al servidor i veuriem la seva pantalla

<img width="1288" height="891" alt="image" src="https://github.com/user-attachments/assets/0a6164fb-3fe7-440f-8290-c1a2561cc12c" />


























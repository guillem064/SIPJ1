
MONITORITZACIÓ, CONNEXIÓ I LLICENCIAMENT

logger[opcions][p-prioritat][missatge]

logger -i -s -p mail.err Aturant el sistema

Servei.prioritat acció

auth
mail
lpr
cron
kern
cron
…

(prioritat de + petita a + gran)

debug
infor
notice
warning, warn
err, error
crit
alert
emerg, panic
 

entrar al sistema de procesos i fer captures

<img width="697" height="107" alt="Captura de pantalla de 2026-05-05 11-46-07" src="https://github.com/user-attachments/assets/71133529-baca-471f-aaab-c0e9d55e1f5d" />

<img width="706" height="449" alt="Captura de pantalla de 2026-05-05 11-49-09" src="https://github.com/user-attachments/assets/e3af0ead-c62e-4af9-9fcf-b639143fa356" />

cv /var/log
ls
//al syslog van tots els logs

<img width="609" height="166" alt="Captura de pantalla de 2026-05-05 11-48-16" src="https://github.com/user-attachments/assets/d4507553-c37d-4cdf-b6f9-5a796c1b17f0" />

//el dmesg.1.gz se li diu la rotacio de logs ara veurem on es defineix
sudo nano /etc/logrotate.conf
cd /etc/logrotate.d/
ls
{CAPTURA}

(obrim dos terminals)
nova 
tail -f /var/log/syslog

<img width="738" height="436" alt="Captura de pantalla de 2026-05-05 11-56-24" src="https://github.com/user-attachments/assets/2e626e02-7df0-4567-9ec0-4e64e05276ff" />

antiga
logger -i -s -p mail.err Mail ha fallat

<img width="674" height="51" alt="Captura de pantalla de 2026-05-05 11-59-42" src="https://github.com/user-attachments/assets/9f93ad9c-705f-4c79-a0c9-0a97a1921536" />

nova
{CAPTURA del missatge de error}
<img width="687" height="54" alt="Captura de pantalla de 2026-05-05 12-00-33" src="https://github.com/user-attachments/assets/1b76ac4c-1b97-48d7-8b13-8b7c4b90e144" />


antiga
nano /etc/rsyslog.d/50-default.conf
mail.* -> mail.crit

<img width="527" height="319" alt="Captura de pantalla de 2026-05-05 12-01-57" src="https://github.com/user-attachments/assets/244cb441-97ea-4fd2-942c-8073704b411e" />

systemctl restart rsyslog
logger -i -s -p mail.err Mail ha fallat2

nova
{CAPTURA del missatge de error}
<img width="676" height="36" alt="image" src="https://github.com/user-attachments/assets/c475caf4-87bc-4c3e-b780-5d7982fadb88" />


antiga
nano /etc/rsyslog.d/50-default.conf
mail.crit -> mail.=crit
systemctl restart rsyslog
logger -i -s -p mail.err Mail ha fallat3
systemctl restart rsyslog
logger -i -s -p mail.err Mail ha fallat4
systemctl restart rsyslog
logger -i -s -p mail.err Mail ha fallat5
cat /var/log/mail.log

<img width="670" height="137" alt="Captura de pantalla de 2026-05-05 12-02-44" src="https://github.com/user-attachments/assets/c6c8a43d-b386-42d8-932a-a00dd7e939a6" />


nova
{CAPTURA del missatge de error}
<img width="506" height="121" alt="Captura de pantalla de 2026-05-05 12-04-17" src="https://github.com/user-attachments/assets/e41f334d-1404-4286-ac98-7d3513a9c02b" />


antiga
nano /etc/rsyslog.d/50-default.conf
*.crit 		/var/log/mireia.log

<img width="559" height="347" alt="Captura de pantalla de 2026-05-05 12-05-57" src="https://github.com/user-attachments/assets/82a97466-2207-449e-ad2b-399a4d7ed17a" />

systemctl restart rsyslog
logger -i -s -p cron.notice Este no
logger -i -s -p auth.alert Este si
cat /var/log/mireia.log
<img width="624" height="152" alt="Captura de pantalla de 2026-05-05 12-07-28" src="https://github.com/user-attachments/assets/c37221eb-e074-4b44-b10e-9e72b53a00f4" />

# SIMULAR UN SERVIDOR CENTRALITZAT DE LOGS




## Fase 1 – Preparació del sistema

### Afegir un nou disc virtual a la màquina virtual

<img width="102" height="73" alt="image" src="https://github.com/user-attachments/assets/6a054001-1eee-401c-8e20-5a7a23beb857" />

<img width="179" height="45" alt="image" src="https://github.com/user-attachments/assets/caf4aafa-2275-432e-afd8-0ea6dd2107fb" />

<img width="375" height="228" alt="image" src="https://github.com/user-attachments/assets/33167a0f-f7bb-4e9f-9354-8574fb4965b1" />

<img width="53" height="71" alt="image" src="https://github.com/user-attachments/assets/ca40ddd1-efd2-4b3c-9dca-6437fb0216a7" />

<img width="723" height="449" alt="image" src="https://github.com/user-attachments/assets/ef4c6271-e36e-40db-a737-006066bb3d38" />

<img width="723" height="449" alt="image" src="https://github.com/user-attachments/assets/5b72e4b4-2b26-4636-ab92-c6e9e96ce587" />

<img width="723" height="449" alt="image" src="https://github.com/user-attachments/assets/cc73a867-9fae-47f0-87e6-96f648e983a4" />

Cliquem a choose i ja el tindriem creat i seleccionat per a la màquina virtual

<img width="918" height="422" alt="image" src="https://github.com/user-attachments/assets/a8c2c7ef-404d-4441-8fb7-9991b9286c9b" />

### Iniciar Windows i obrir Gestió de discs
### Inicialitzar el disc, crear dues particions: una anomenada Dades i una en FAT32 anomenada Portable
### Assignar lletres i comprovar amb diskpart la configuració

## Fase 2 – Quotes i usuaris
### Activar quotes de disc a la partició Dades (NTFS)
### Establir límit de 300 MB per usuari, amb notificació d’advertència
### Crear dos usuaris locals: alumne1 i alumne2
### Afegir-los a un grup nou anomenat Limitats
### Provar la còpia de fitxers dins Dades per veure com actuen les quotes (superar límit)

## Fase 3 – Script de còpia i automatització
### Afegir tercer disc virtual, formatar-lo en NTFS com a Backups
### Crear carpeta CòpiesUsuaris dins Backups
### Crear un script .bat que copiï C:\Users\%USERNAME% a E:\CòpiesUsuaris\%USERNAME%
### Obre gpedit.msc → Configuració d’usuari → Scripts → Inici de sessió
### Assigna l’script perquè s’executi automàticament quan alumne1 o alumne2 inicien sessió

## Fase 4 – Verificació i documentació
### Inicia sessió amb alumne1, comprova que l’script fa la còpia a Backups i que la quota de Dades bloqueja si supera el límit, així com comprovacions que tot el que has configurat funciona correctament

## Fase 5 – Gestió de processos i serveis
### Llistar processos actius
#### Inicia sessió com alumne1
#### Obre la consola (cmd) com a usuari
#### Executa: tasklist
#### Copia el resultat a un fitxer: tasklist > C:\Users\%USERNAME%\processos_inici.txt
#### Observa processos típics: explorer.exe, SearchIndexer.exe, OneDrive.exe, etc.
### Identificar processos prescindibles
#### Busca processos no essencials per a l’usuari, com: OneDrive.exe, Teams.exe, SkypeApp.exe
#### Fes una taula amb:
#### Nom del procés
#### Memòria usada
#### Justificació per eliminar-lo
### Eliminar processos manualment
#### Encara dins de la consola, executa: taskkill /IM OneDrive.exe /F
#### Comprova amb tasklist si ha desaparegut
#### Fes una captura abans i després
### Automatitzar-ho a l’inici de sessió
#### Modifica l’script d’inici de sessió afegint: taskkill /IM OneDrive.exe /F taskkill /IM Teams.exe /F
#### Reengega sessió com alumne2 i comprova que aquests processos no es llencen o es tanquen
### Documentació
#### Afegeix fitxer de tasklist i taula justificativa a la doc amb MkDocs
#### Explica què passa si mates un procés crític com explorer.exe (prova controlada)
#### Comenta com aquesta gestió pot millorar el rendiment de màquines virtuals o amb pocs recursos

## Fase 6 – Gestió de permisos (ACLs)
#### Què són les ACLs i com funcionen a Windows A Windows, cada fitxer i carpeta té una llista de control d'accés (ACL, Access Control List). Aquesta llista defineix qui pot fer què amb aquell recurs.
#### Cada entrada d'una ACL es diu ACE (Access Control Entry) i indica:
#### Quina identitat (usuari o grup) està afectada
#### Quins permisos té (lectura, escriptura, execució, control total, etc.)
#### Els permisos ACL són molt més detallats que els permisos "normals" de compartició en xarxa, perquè:

## Fase 1 – Preparació del sistema

### Afegir un nou disc virtual a la màquina virtual

<img width="102" height="73" alt="image" src="https://github.com/user-attachments/assets/6a054001-1eee-401c-8e20-5a7a23beb857" />

<img width="179" height="45" alt="image" src="https://github.com/user-attachments/assets/caf4aafa-2275-432e-afd8-0ea6dd2107fb" />

<img width="375" height="228" alt="image" src="https://github.com/user-attachments/assets/33167a0f-f7bb-4e9f-9354-8574fb4965b1" />

<img width="53" height="71" alt="image" src="https://github.com/user-attachments/assets/ca40ddd1-efd2-4b3c-9dca-6437fb0216a7" />

<img width="723" height="449" alt="image" src="https://github.com/user-attachments/assets/ef4c6271-e36e-40db-a737-006066bb3d38" />

<img width="723" height="449" alt="image" src="https://github.com/user-attachments/assets/5b72e4b4-2b26-4636-ab92-c6e9e96ce587" />

<img width="723" height="449" alt="image" src="https://github.com/user-attachments/assets/cc73a867-9fae-47f0-87e6-96f648e983a4" />

#### Cliquem a choose i ja el tindriem creat i seleccionat per a la màquina virtual

<img width="918" height="422" alt="image" src="https://github.com/user-attachments/assets/a8c2c7ef-404d-4441-8fb7-9991b9286c9b" />

<img width="279" height="133" alt="image" src="https://github.com/user-attachments/assets/d1beb286-02aa-4011-a67a-2a8780b1a5e2" />

### Iniciar Windows i obrir Gestió de discs

<img width="356" height="377" alt="image" src="https://github.com/user-attachments/assets/88f5cffd-cbda-4a9c-aab2-d0dcf99ff239" />

<img width="206" height="46" alt="image" src="https://github.com/user-attachments/assets/141ebe1a-347f-42be-a661-92f5e76d011d" />

<img width="585" height="610" alt="image" src="https://github.com/user-attachments/assets/58f43f8b-f751-4155-9c13-1eef6c87ff9b" />

### Inicialitzar el disc, crear dues particions: una anomenada Dades i una en FAT32 anomenada Portable

<img width="539" height="106" alt="image" src="https://github.com/user-attachments/assets/331f05d3-5b1b-4df6-b36a-65e683b88a64" />

<img width="501" height="392" alt="image" src="https://github.com/user-attachments/assets/21d2eac1-3729-449e-9cef-a3675859b695" />

<img width="501" height="392" alt="image" src="https://github.com/user-attachments/assets/026a3cae-f108-4196-8b21-8b302f28add1" />

<img width="501" height="392" alt="image" src="https://github.com/user-attachments/assets/fa7a284d-86cf-439a-802c-f2cadda6a436" />

<img width="501" height="392" alt="image" src="https://github.com/user-attachments/assets/8ecd4fae-59a4-4d8a-858e-19007c74b5d6" />

<img width="501" height="392" alt="image" src="https://github.com/user-attachments/assets/736b6523-95f6-458e-add3-a27d22a36178" />

<img width="571" height="109" alt="image" src="https://github.com/user-attachments/assets/3fb88683-20dc-4733-900e-884054ddd63c" />

#### Ara anem a fer l'altra partició

<img width="632" height="106" alt="image" src="https://github.com/user-attachments/assets/a64e5e99-3eba-487b-b385-1a03b883f347" />

<img width="501" height="394" alt="image" src="https://github.com/user-attachments/assets/8809e189-e37c-4f44-95dc-b86ad6fddf43" />

<img width="501" height="394" alt="image" src="https://github.com/user-attachments/assets/5b0a1958-aaec-445b-a4f7-d58aeac816f1" />

<img width="501" height="394" alt="image" src="https://github.com/user-attachments/assets/c1c84f6d-9439-42d1-91c9-bae280e7ada5" />

<img width="501" height="394" alt="image" src="https://github.com/user-attachments/assets/7be242b2-3d8a-49b9-9bda-ca71e4b559e2" />

<img width="501" height="394" alt="image" src="https://github.com/user-attachments/assets/81c444e6-a12b-41d3-80bc-a0c2452b82e6" />

#### Ja tindriem les 2 particions fetes amb les lletres asignades i amb el nom corresponent

<img width="569" height="100" alt="image" src="https://github.com/user-attachments/assets/a9f8d6b8-0a9e-4c24-a15d-1d18b3b249d2" />

### Assignar lletres i comprovar amb diskpart la configuració

#### Premem Windows + R i posem diskpart i li donem a enter o aceptar per a obrir la terminal de diskpart

<img width="407" height="220" alt="image" src="https://github.com/user-attachments/assets/8e4aabcb-6b61-4929-b02d-22bafb85016d" />

#### Amb list disk podem veure la llista dels discos que tenim a la màquina virtual.

<img width="420" height="119" alt="image" src="https://github.com/user-attachments/assets/a6ccf4ef-7ea1-4a45-9a20-b42c970c0e55" />

#### Seleccionem el disc recentment creat per a veure la seva configuració

<img width="356" height="71" alt="image" src="https://github.com/user-attachments/assets/591e167c-1d18-48ca-87ea-a66b8374a7d2" />

#### Amb list partition veiem les particions del disc seleccionat anteriorment

<img width="485" height="113" alt="image" src="https://github.com/user-attachments/assets/b42245b4-8918-47a4-a6ec-db15c212eb6d" />

#### Per finalitzar amb el list volume podem veure les caracteristiques de tots els volums que tenim a la nostra màquina virtual

<img width="677" height="147" alt="image" src="https://github.com/user-attachments/assets/0774da68-63d1-4f03-a721-e940e62d5328" />

## Fase 2 – Quotes i usuaris

### Activar quotes de disc a la partició Dades (NTFS)

<img width="410" height="399" alt="image" src="https://github.com/user-attachments/assets/f71ad42f-4625-4526-92de-03c1676ae28b" />

<img width="365" height="392" alt="image" src="https://github.com/user-attachments/assets/b0aa8474-92de-4bd0-a0b4-e78ffdfded20" />

<img width="365" height="392" alt="image" src="https://github.com/user-attachments/assets/99bbaa8f-4e16-4d61-9fae-46a4c5ddc8d6" />

### Establir límit de 300 MB per usuari, amb notificació d’advertència

<img width="360" height="451" alt="image" src="https://github.com/user-attachments/assets/bbbdc21b-fede-46fe-ae04-9a63ce64f327" />

<img width="260" height="39" alt="image" src="https://github.com/user-attachments/assets/4448b106-3590-440a-a5eb-2ff0a20b0256" />

### Crear dos usuaris locals: alumne1 i alumne2

#### Executem la terminal com administradors

<img width="292" height="270" alt="image" src="https://github.com/user-attachments/assets/6e3fd360-39d7-4548-b739-fd6c14684115" />

#### Amb aquestes dues comandes creem els dos usuaris nous

<img width="400" height="119" alt="image" src="https://github.com/user-attachments/assets/1ca24952-179c-4d8c-a61d-b154b2e6ba34" />

#### Amb aquesta altra comanda podem veure els usuaris que tenim i les seves caracteristiques

<img width="516" height="168" alt="image" src="https://github.com/user-attachments/assets/d898c4d0-0b98-4cc7-a194-14df75320f6d" />

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

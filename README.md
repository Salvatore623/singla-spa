# Creazione del Progetto

creazione progetto todo introduzione ai Microfrontend (MFE) con single-spa.

![Image1](./img/img1.png)

## Tipologie di MFE

Durante l'inizializzazione del progetto, il framework ci propone 3 diverse tipologie di MFE:

![Image2](./img/img2.png)

### Single-spa Application/Parcel

Quando si parla di 'Application', ci si riferisce a un MFE inteso come una pagina (ad esempio Home, Profilo). Il 'Parcel', d'altra parte, è un tipo specifico di 'Application' che rappresenta un componente (come una navbar o una tabella).

### In-browser utility module

Questo MFE è condiviso tra i vari MFE e viene utilizzato per condividere codice (come ad esempio css globale o una funzione che formatta le date). È raccomandato dal framework per essere utilizzato come service per le chiamate AJAX.

### Single-spa Root-config

MFE orchestratore, all'interno del Root-config registriamo tutti i nostri MFE, gestiamo il routing, durante l'inizializzazione ci chiederà se generare un single spa layout, ovvero un file dove gestire il layout, in questo file possiamo inserire dei MFE parcel, ad esempio una navbar che è condivisa tra tutti i MFE in modo da inserirla una singola volta. Il Root-config può gestire anche lo stato globale dell'applicazione.

## Composizione del Progetto

![Image3](./img/img3.png)

Il progetto è composto da 4 MFE:
1. root-config (MFE orchestratore).
2. todo-page (MFE pagina).
3. todo-table (MFE Parcel).
4. utility-app (MFE di utilità).

## Avvio dei MFE

Il MFE todo-table (Parcel) così come gli altri due MFE (todo-page, utility-app) non sono ancora registrati nel MFE orchestratore e per questo non è possibile testarli nel flusso dell'applicazione. Per avviarli in modo indipendente, è possibile eseguire il comando `npm run start:standalone`.

<img src="./img/img4.png" alt="Description of the image" style="width: 750px;">

## Verifica dell'Avvio

Se tutto funziona correttamente, dovremmo vedere a schermo "@org/nomeprogetto is mounted!". Questo codice si trova nel file root-component.js del nostro MFE ed è il file root (App.js in React) del nostro MFE.

<div style="display: flex">
    <img src="./img/img5.png" alt="Description of image 1" style="width: 500px; height: auto;">
    <img src="./img/img6.png" alt="Description of image 2" style="width: 500px; height: auto;">
</div>

## Note

In caso di errori di sintassi eliminare il file `.eslintrc`. <br>
plant è il nome della org inserita in fase di inizializzazione del mfe, single-spa genera i file con organizzazione seguito dal nome del progetto.

### Plant-root-config.js

![Image7](")

passiamo al mfe root-config (orchestratore), questo mfe all'interno della cartella src presenta 3 file, index.ejs, plant-root-config.js, microfrontend-layout.html. <br>
INDEX.EJS: in questo file registreremo i mfe, per comodità inserisco nello script di start del package.json di utility.app, todo-page e todo-table una porta differente scelta da me.

---

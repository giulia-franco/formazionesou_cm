# STEP 2

## build di container

### file contenuti

- /rocky --> folder che contiene il dockerfile per buildare l'immagine rocky
- /ubuntu --> folder che contiene il dockerfile per buildare l'immagine ubuntu
- build-playbook.yml --> playbook crea i due container con le immagini buildate

### descrizione

Utilizzando la vm creata nello step 1, aggiungiamo un secondo playbook (build-playbook.yml).
Il playbook contiene i task per la creazione dei due container con le immagini precedentemente buildate e pushate su Docker-hub e effettui il forword delle porte.

# formazionesou_cm

## STEP 1 (docker registry)

### File contenuti

- Vagrantfile --> Un Vagrantfile è un file di configurazione che definisce e automatizza la creazione e gestione di ambienti virtuali con Vagrant.
- container-playbook.yml --> questo playbook deve configurare un docker registry

### Descrizione

Il vagrant file crea una vm Rocky linux, il provision della vm viene eseguito con ansible, tramite un playbook (container-playbook.yml).
Il playbook contine i task per l'installazione e avvio di docker e per la creazione di un docker registry.  

## STEP 2 (build di container)

### File contenuti

- /rocky --> folder che contiene il dockerfile per buildare l'immagine rocky
- /ubuntu --> folder che contiene il dockerfile per buildare l'immagine ubuntu
- build-playbook.yml --> playbook crea i due container con le immagini buildate

### Descrizione

Utilizzando la vm creata nello step 1, aggiungiamo un secondo playbook (build-playbook.yml).
Il playbook contiene i task per la creazione dei due container con le immagini precedentemente buildate.

## STEP 3 (creazione ruoli)

### File contenuti

- /rocky --> folder che contiene il dockerfile per buildare l'immagine rocky
- /ubuntu --> folder che contiene il dockerfile per buildare l'immagine ubuntu
- Vagrantfile --> Un Vagrantfile è un file di configurazione che definisce e automatizza la creazione e gestione di ambienti virtuali con Vagrant.
- container-playbook.yml --> questo playbook deve svolgere i diversi ruoli.
- /roles --> questa folder contiene altre cartelle che a loro volta contengono i playbook con i ruoli
  - /preparazionevm/tasks --> contiene il file main.yml che contiene i task per la configurazione della vm.
  - /containers/tasks --> contine il file main.yml che contiene i task per la creazione del registri e dei due container (sia con docker che con podman).
  - /push/tasks --> contiene il file main.yml che contiene i task per il build e push delle immagini.

### Descrizione

il vagrant file crea una vm Rocky linux, il provision della vm viene eseguito con ansible tramite un playbook (playbook.yml), in questo primo playbook vengono stabiliti i ruoli.
nella cartella /roles sono contenute le sub-folder con i playbook (main.ymnl) che identificano ogni ruolo

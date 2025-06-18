# STEP 3

## Creazione ruoli

### File contenuti

- /rocky --> folder che contiene il dockerfile per buildare l'immagine rocky.
- /ubuntu --> folder che contiene il dockerfile per buildare l'immagine ubuntu.
- Vagrantfile --> Un Vagrantfile è un file di configurazione che definisce e automatizza la creazione e gestione di ambienti virtuali con Vagrant.
- container-playbook.yml --> questo playbook deve svolgere i diversi ruoli.
- /roles --> questa folder contiene altre cartelle che a loro volta contengono i playbook con i ruoli
  - /preparazionevm/tasks --> contiene il file main.yml che contiene i task per la configurazione della vm.
  - /containers/tasks --> contine il file main.yml che contiene i task per la creazione del registri e dei due container (sia con docker che con podman).
  - /push/tasks --> contiene il file main.yml che contiene i task per il build e push delle immagini.

### Descrizione

Il vagrant file crea una vm Rocky linux, il provision della vm viene eseguito con ansible tramite un playbook (playbook.yml), in questo primo playbook vengono stabiliti i ruoli.
Nella cartella /roles sono contenute le sub-folder con i playbook (main.ymnl) che identificano ogni ruolo.
Il playbook deve contenere ruoli che funzionino sia con Docker che con Podman.x‡

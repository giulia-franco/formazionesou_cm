# STEP 1

## Docker registry

### file contenuti

- Vagrantfile --> Un Vagrantfile è un file di configurazione che definisce e automatizza la creazione e gestione di ambienti virtuali con Vagrant.
- container-playbook.yml --> questo playbook deve configurare un docker registry

### Descrizione

Il vagrant file crea una vm Rocky linux, il provision della vm viene eseguito con ansible, tramite un playbook (container-playbook.yml).
Il playbook contine i task per l'installazione e avvio di docker e per la creazione di un docker registry.

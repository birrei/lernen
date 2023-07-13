
## Erstellen von virtuellen Linux-Computern in Azure mit Ansible 

Quelle: 
https://learn.microsoft.com/de-de/azure/developer/ansible/vm-configure?tabs=ansible

In diesem Artikel  
1. Konfigurieren Ihrer Umgebung  
2. Erstellen eines SSH-Schlüsselpaars  
3. Implementieren des Ansible-Playbooks  
4. Ausführen des Playbooks  
5. Überprüfen der Ergebnisse  
6. Herstellen einer Verbindung mit der VM  

## Erstellen eines SSH-Schlüsselpaars
Führen Sie den folgenden Befehl aus. Geben Sie bei entsprechender Aufforderung die zu erstellenden Dateien im folgenden Verzeichnis an: /home/azureuser/.ssh/authorized_keys. 

```
ssh-keygen -m PEM -t rsa -b 4096
```
detailerkläerung: 
https://learn.microsoft.com/en-us/azure/virtual-machines/linux/create-ssh-keys-detailed


birgit@Azure:~/testvm$ ssh-keygen -m PEM -t rsa -b 4096
Generating public/private rsa key pair.
Enter file in which to save the key (/home/birgit/.ssh/id_rsa): 



Übung: 
Ordner: testvm 
rg: testvm20230711

Detailerkläerung SSH-Schlüssel erstellen: 
https://learn.microsoft.com/en-us/azure/virtual-machines/linux/create-ssh-keys-detailed



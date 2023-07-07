# Ansible 
## Aufgabe: Konfigurieren von Ansible mithilfe von Azure Cloud Shell
Link: 
[Konfigurieren von Ansible mithilfe von Azure Cloud Shell](https://learn.microsoft.com/de-de/azure/developer/ansible/getting-started-cloud-shell?tabs=ansible)  

Legen Sie die AZURE_SUBSCRIPTION_ID wie folgt fest, indem Sie Ihre Azure-Abonnement-ID verwenden:  
```
az account list
```

Testen der Ansible-Installation 
https://learn.microsoft.com/de-de/azure/developer/ansible/getting-started-cloud-shell?tabs=ansible

öffne cloud shell  
erzeuge  datei create_rg.yml  
```
code create_rg.yml
```
```
---
- hosts: localhost
  connection: local
  tasks:
    - name: Creating resource group - "{{ name }}"
      azure_rm_resourcegroup:
        name: "{{ name }}"
        location: "{{ location }}"
      register: rg
    - debug:
        var: rg
```


```
ansible-playbook create_rg.yml --extra-vars "name=rg_test_bir_20230702 location=westeurope"
```

----
Links:  
[Matrix der Ansible-Module und -Versionen](https://learn.microsoft.com/de-de/azure/developer/ansible/module-version-matrix)

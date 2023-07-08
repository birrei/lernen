# Ansible 
## Aufgabe: Konfigurieren von Ansible mithilfe von Azure Cloud Shell
Link: 
[Konfigurieren von Ansible mithilfe von Azure Cloud Shell](https://learn.microsoft.com/de-de/azure/developer/ansible/getting-started-cloud-shell?tabs=ansible)  

Legen Sie die AZURE_SUBSCRIPTION_ID wie folgt fest, indem Sie Ihre Azure-Abonnement-ID verwenden:  
```
az account list
..
export AZURE_SUBSCRIPTION_ID=<your-subscription-id>
```
Testen der Ansible-Installation: öffne cloud shell  
erzeuge  datei create_rg.yml  
```
code create_rg.yml
```
Inhalt: 
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
create_rg.yml ausführen: 

```
ansible-playbook create_rg.yml --extra-vars "name=rg_test_bir_20230702 location=westeurope"
```
Ausgabe: 
```
PLAY [localhost] ***********************************************************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************************************
ok: [localhost]

TASK [Creating resource group - "rg_test_bir_20230702"] ********************************************************************************************************************
changed: [localhost]

TASK [debug] ***************************************************************************************************************************************************************
ok: [localhost] => {
    "rg": {
        "changed": true,
        "contains_resources": false,
        "failed": false,
        "state": {
            "id": "/subscriptions/1b126c51-b177-4730-912b-e35388898428/resourceGroups/rg_test_bir_20230702",
            "location": "westeurope",
            "name": "rg_test_bir_20230702",
            "provisioning_state": "Succeeded",
            "tags": null
        }
    }
}

PLAY RECAP *****************************************************************************************************************************************************************
localhost                  : ok=3    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0  
```

----
Links:  
[Matrix der Ansible-Module und -Versionen](https://learn.microsoft.com/de-de/azure/developer/ansible/module-version-matrix)

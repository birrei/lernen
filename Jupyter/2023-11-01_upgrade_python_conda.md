# Udpate auf Python 3.9

```
python --version 
```
3.7.6 

```
conda update python
```

...

```
==> WARNING: A newer version of conda exists. <==
  current version: 4.8.2
  latest version: 23.9.0

Please update conda by running

    $ conda update -n base -c defaults conda
```

Mache das ... 

Funktioniert nicht: 
```
(base) C:\Users\birgi>conda update conda
Collecting package metadata (current_repodata.json): done
Solving environment: done


==> WARNING: A newer version of conda exists. <==
  current version: 4.8.2
  latest version: 23.9.0

Please update conda by running

    $ conda update -n base -c defaults conda

# All requested packages already installed.

```

Fortsetzung Recherche 
Google: "conda update problem" 

Hier wird das gleiche Problem geschildert: 
https://github.com/conda/conda/issues/9469

U.a. gibt es in diesem Beietrag. 
https://github.com/conda/conda/issues/9469#issuecomment-1503302008


diese Empfehlung: 
```
conda update -n base -c defaults conda --repodata-fn=repodata.json
```
Test: 
```
conda --version
```
22.9.0

Nachfolgender Versuch "conda install python=3.9" endet in "Examining conflict for ... ". Abgebrochen, da das sich - lt. Berichten -  anschickt, mehrere Stunden zu dauern ..  

Eine Alternative wäre es , ein neues environment zu erstellen - ich dachte, das ist etwas, was man braucht, wenn man mit verschiedenen Projekten arbeitet, ich möchte jedoch ja nur lernen, und dafür eine aktuelle Umgebung haben. Entschließe mich, komplett ganz neu zu installieren. 

Deinstallieren: 

https://docs.anaconda.com/free/anaconda/install/uninstall/

```
conda install anaconda-clean
anaconda-clean --yes
```
es wurde angelegt: 
C:\Users\birgi\.anaconda_backup

Ich hätte wohl auch einfach den Ordnder löschen anaconda3 löschen können ... 

Neuinstallation: 
https://docs.anaconda.com/free/anaconda/install/windows/

mit aktuellem Windows-Installer
Anaconda3-2023.09-0-Windows-x86_64.exe

(...)  

```
conda --version  
conda 23.7.4

python --version  
Python 3.11.5
```

OK. 

Nachträge: 

Beim öffnen von Jupyter Notebook wird nun oben dieser Hinweis angezeigt:   
"UPDATE Read [https://jupyter-notebook.readthedocs.io/en/latest/migrate_to_notebook7.html](the migration plan) to Notebook 7 to learn about the new features and the actions to take if you are using extensions - Please note that updating to Notebook 7 might break some of your extensions." 




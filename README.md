# T-SEC-902

## Network analysis

Voir dans le dossier suspicious/suspicious.txt -> resultats de l'analyse
- Ce que j'ai trouvé
- Ce que j'ai testé
- Les IPs suspectes -> J'ai trouvé que l'IP 10.0.2.4 a eu une forte activité sur le réseau

## RAM analysis

- Découverte de volatility3
- Utilisation sur le dump mémoire
- Découverte des differents plugins disponibles
- Pour l'instant :
  - infos globales du système
  - liste des processus lors du dump
  - Scan réseau pour trouver les connexions actives
  - et autre chose mais pas encore compris ce que ça fait

## Ce qu'il reste à faire

- Mettre dans docker l'executable
- L'executer et voir ce que je peux en tirer
- Potentiellement retro-engineer ce que je peux
- Obfuscation ?

# Command lines utilisées

```sh
python3 tool/volatility3/vol.py -f memdump.mem windows.pslist > txt_results_ram/results_ram_list.txt
python3 tool/volatility3/vol.py -f memdump.mem windows.info > txt_results_ram/results_ram_info.txt
python3 tool/volatility3/vol.py -f memdump.mem windows.malware.malfind > txt_results_ram/results_ram_mal.txt
python3 tool/volatility3/vol.py -f memdump.mem windows.pstree > txt_results_ram/results_ram_tree.txt
python3 tool/volatility3/vol.py -f memdump.mem windows.netscan > txt_results_ram/results_ram_netscan.txt
python3 tool/volatility3/vol.py -f memdump.mem windows.cmdline > txt_results_ram/results_ram_cmdline.txt
```

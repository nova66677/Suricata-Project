🛡️ Projet : Détection d'attaques réseau avec Suricata

🎯 Objectifs

    Installer, configurer et maîtriser Suricata en tant qu'IDS/IPS.

    Détecter des attaques dans un environnement simulé (via des PCAPs ou des scans Metasploit/Nmap).

    Créer des règles personnalisées.

    Visualiser les alertes et les logs générés.

    Automatiser l'analyse avec un script Python (en bonus).


    les règles de détections seront placées dans le repertoire rules
    Les résultats des scans seront dans le reportoire analysis
    Les attaques réseaux seront placées dans pcaps
    Le répertoire scripts contiendra les scripts d'analyse de logs


## A définir :
    - Quelles attaques tests ?


Listes des attaques : 
    - Scans NMAP
        - SYN scan "bourrins" ==> ok
        - SSH brute force (hydra / medusa) => plusieurs règles car ip peut changer (vpn / tor) ==> ok
        - HTTP -> XSS et SQLi
        - ICMP (Ping flood)
        - PCAP contenant payload connus (reverse_tcp non-chiffré)

Analyse des logs (eve.json) : Utiliser 'jq' pour filtrer les protocoles qui nous intéressent
    - ex: jq 'select(.event_type == "http") | .http.http_user_agent' pour filter le traffic HTTP et lister les User-Agent détectés

## Evaluation des règles : 
    - Mesurer les faux positifs et les faux négatifs
    - Mesurer perfs en faisant varier le nombre d'attaques / min
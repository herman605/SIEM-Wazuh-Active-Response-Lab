#  Ingénierie SIEM : Wazuh & Active Response

## Objectif du Laboratoire
Ce projet documente la mise en place d'une infrastructure de détection et de réponse automatisée (Active Response) via le SIEM Wazuh. L'objectif principal est de sécuriser un point d'accès SSH contre les attaques par force brute en identifiant les angles morts des décodeurs par défaut et en déployant des règles de corrélation XML sur mesure.

##  Contexte Opérationnel (SOC)
Dans ce laboratoire, le travail de l'analyste s'articule autour de quatre piliers :
1. **Audit :** Évaluation des mécanismes de détection par défaut face à une attaque soutenue.
2. **Ingénierie de Détection :** Création d'une règle XML personnalisée exploitant la corrélation temporelle et spatiale.
3. **Tests de Résilience :** Contournement des sécurités internes et validation de la chaîne d'alerte via l'injection de journaux contrefaits (*Log Spoofing*).
4. **Automatisation (Blue Team) :** Déclenchement d'une isolation réseau locale ciblée.

#Architecture de Défense
* **Le Cerveau (Manager) :** Serveur Wazuh assurant la détection, la corrélation et l'ordonnancement.
* **Le Bras Armé (Agent) :** Machine cible Linux chargée de l'exécution du blocage réseau (`firewall-drop`).
 
## Arborescence du Projet
* `/config` : Configuration de l'Active Response (`ossec.conf`).
* `/rules` : Règles XML de corrélation sur mesure (`local_rules.xml`).
* `/scripts` : Commandes d'investigation avancées et scripts de *Log Spoofing*.
* `/assets` : Preuves d'exécution, analyses de logs et Dashboard.

# MiniLab Cisco Packet Tracer

## Objectif

Ce projet consiste à mettre en place une infrastructure réseau simulée sous Cisco Packet Tracer comprenant :

- 1 routeur Cisco 1941
- 3 switchs Cisco 2960
- 3 points d'accès Wi-Fi
- 6 PC fixes
- 3 ordinateurs portables
- 3 téléphones IP Cisco 7960

L'objectif est de configurer plusieurs VLAN, mettre en place un serveur DHCP centralisé et permettre la communication entre les différents réseaux.

---

## Topologie

Le réseau est composé de trois zones (bureaux) interconnectées via des liens trunk vers un routeur Cisco 1941 configuré en Router-on-a-Stick.

Chaque zone contient :

- 1 switch
- 1 point d'accès Wi-Fi
- 2 PC fixes
- 1 ordinateur portable
- 1 téléphone IP

---

## VLAN utilisés

| VLAN | Usage | Réseau |
|--------|--------|--------|
| VLAN 1 | VoIP | 192.168.0.0/24 |
| VLAN 10 | Wi-Fi | 192.168.10.0/24 |
| VLAN 20 | PC fixes | 192.168.20.0/24 |
| VLAN 30 | Administration | 192.168.30.0/24 |

---

## Configuration DHCP

Le routeur Cisco 1941 assure le service DHCP pour tous les VLAN.

### VLAN 1 - VoIP

- Réseau : 192.168.0.0/24
- Passerelle : 192.168.0.1
- Plage DHCP : 192.168.0.10 - 192.168.0.50

### VLAN 10 - Wi-Fi

- Réseau : 192.168.10.0/24
- Passerelle : 192.168.10.1
- Plage DHCP : 192.168.10.10 - 192.168.10.50

### VLAN 20 - PC fixes

- Réseau : 192.168.20.0/24
- Passerelle : 192.168.20.1
- Plage DHCP : 192.168.20.10 - 192.168.20.50

### VLAN 30 - Administration

- Réseau : 192.168.30.0/24
- Passerelle : 192.168.30.1
- Plage DHCP : 192.168.30.10 - 192.168.30.50

---

## Méthodologie

### Étape 1 : Création de la topologie

Ajout des équipements et câblage des différents bureaux.

### Étape 2 : Création des VLAN

Configuration des VLAN sur les trois switchs :

- VLAN 1 : VoIP
- VLAN 10 : Wi-Fi
- VLAN 20 : PC fixes
- VLAN 30 : Administration

### Étape 3 : Configuration des ports

| Ports | Fonction |
|---------|---------|
| Fa0/1 | Trunk |
| Fa0/2 - Fa0/3 | Téléphones IP |
| Fa0/4 - Fa0/5 | Points d'accès |
| Fa0/6 - Fa0/7 | PC fixes |
| Fa0/8 | Administration |
| Fa0/9 | Trunk inter-switch |

### Étape 4 : Configuration du routeur

Mise en place du Router-on-a-Stick avec les sous-interfaces :

- G0/0.1
- G0/0.10
- G0/0.20
- G0/0.30

### Étape 5 : Configuration DHCP

Création des pools DHCP pour chaque VLAN.

### Étape 6 : Tests

- Vérification des VLAN
- Vérification des trunks
- Attribution DHCP
- Ping entre VLAN
- Communication entre les trois zones

---

## Organisation du dépôt

### Fichier principal

- `minilab.pkt` : projet Packet Tracer complet

### Configurations

- `Router.ptd` : configuration du routeur Cisco 1941

### Zone 1

- Switch 1
- Point d'accès PA1
- PC0
- PC1
- Laptop0
- Téléphone IP

### Zone 2

- Switch 2
- Point d'accès PA2
- PC2
- PC3
- Laptop1
- Téléphone IP

### Zone 3

- Switch 3
- Point d'accès PA3
- PC4
- PC5
- Laptop2
- Téléphone IP

---

## Auteur

BRAYAN LOIC
BTS SIO / Bachelor Cybersécurité

Projet réalisé avec Cisco Packet Tracer.

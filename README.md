# 💾 copyNAS - Copie automatique vers NAS

![Bash](https://img.shields.io/badge/Bash-5%2B-informational?style=for-the-badge)
![Linux](https://img.shields.io/badge/Linux-Debian%2FUbuntu-orange?style=for-the-badge)
![Licence](https://img.shields.io/badge/Licence-MIT-green?style=for-the-badge)

Script Bash de copie automatique de fichiers ou répertoires vers un NAS (Network Attached Storage). Utilise `rsync` pour une synchronisation efficace et incrémentale.

---

## Fonctionnalités

- Copie/synchronisation vers un NAS via `rsync`
- Transfert incrémental (seuls les fichiers modifiés sont copiés)
- Journalisation des opérations
- Automatisable via cron

---

## Prérequis

- Bash 5+
- `rsync` installé : `sudo apt install rsync`
- Accès réseau au NAS (SSH ou SMB)

---

## Installation

```bash
git clone https://github.com/Axolotty/copyNAS.git
cd copyNAS
chmod +x copy.sh
```

---

## Configuration

Ouvrir `copy.sh` et modifier les variables :

```bash
SOURCE="/home/user/documents"         # Répertoire source
DEST="user@192.168.1.10:/backup"      # Destination NAS (SSH)
# ou pour un montage local :
# DEST="/mnt/nas/backup"
LOG="/var/log/copynas.log"
```

---

## Utilisation

### Lancement manuel

```bash
./copy.sh
```

### Automatisation via cron

Synchronisation quotidienne à minuit :

```
0 0 * * * /chemin/vers/copy.sh >> /var/log/copynas.log 2>&1
```

---

## Fichiers du projet

| Fichier | Description |
|---------|-------------|
| `copy.sh` | Script principal de copie/synchronisation |

---

## Licence

MIT © Axolotty

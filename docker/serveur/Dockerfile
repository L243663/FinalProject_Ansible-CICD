FROM ubuntu:22.04

# Installer SSH
RUN apt-get update && apt-get install -y openssh-server

# Créer l'utilisateur "ansible" (mdp: ansible)
RUN useradd -m ansible && echo "ansible:ansible" | chpasswd

# Préparer sshd : créer /run/sshd et générer les clés hôte
RUN mkdir -p /run/sshd && ssh-keygen -A

# Exposer le port SSH
EXPOSE 22

# Démarrer sshd au premier plan (logs visibles)
CMD ["/usr/sbin/sshd","-D","-e"]

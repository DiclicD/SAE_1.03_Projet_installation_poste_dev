# Installation de Debian sur VirtualBox

Ce document décrit les étapes nécessaires pour installer Debian sur une machine virtuelle à l'aide de VirtualBox.

## Prérequis

- Un ordinateur avec VirtualBox installé. Vous pouvez télécharger VirtualBox depuis le [site officiel de VirtualBox](https://www.virtualbox.org/).
- Une image ISO de Debian. Téléchargez la version souhaitée depuis le [site officiel de Debian](https://www.debian.org/distrib/).

## Étapes d'installation

1. **Créer une nouvelle machine virtuelle**
    - Ouvrez VirtualBox et cliquez sur **Nouvelle**.
    - Donnez un nom à votre machine virtuelle (par exemple, "Debian").
    - Sélectionnez le type : **Linux** et la version : **Debian (64-bit)**.
    - Cliquez sur **Suivant**.

2. **Configurer la mémoire**
    - Allouez de la mémoire vive (RAM) à votre machine virtuelle. Un minimum de 1024 Mo est recommandé.
    - Cliquez sur **Suivant**.

3. **Configurer le disque dur**
    - Sélectionnez **Créer un disque dur virtuel maintenant** et cliquez sur **Créer**.
    - Choisissez le type de fichier de disque dur (VDI recommandé) et cliquez sur **Suivant**.
    - Sélectionnez **Allocation dynamique** ou **Taille fixe** en fonction de vos besoins.
    - Définissez la taille du disque virtuel (au moins 20 Go) et cliquez sur **Créer**.

4. **Configurer les paramètres de la machine virtuelle**
    - Sélectionnez la machine virtuelle et cliquez sur **Configuration**.
    - Allez dans l'onglet **Stockage** et sous **Contrôleur : IDE**, cliquez sur l'icône du CD. Ensuite, cliquez sur **Choisir un fichier de disque** pour sélectionner l'image ISO de Debian que vous avez téléchargée.
    - (Optionnel) Allez dans l'onglet **Réseau** et configurez le réseau en mode **Accès par pont** pour un accès Internet.

5. **Démarrer l'installation**
    - Sélectionnez la machine virtuelle et cliquez sur **Démarrer**.
    - Choisissez "Install" ou "Graphical Install" pour démarrer le processus d'installation.

6. **Configuration du réseau**
    - Si une connexion Internet est disponible, configurez le réseau (DHCP recommandé).

7. **Partitionnement du disque**
    - Sélectionnez le type de partitionnement :
        - **Guidé** : L'installation automatique partitionnera le disque.
        - **Manuel** : Pour une configuration personnalisée.

8. **Installation des paquets**
    - Sélectionnez les logiciels à installer. Il est recommandé de cocher l'option "Standard system utilities" et "SSH server" si vous souhaitez accéder à votre machine à distance.

9. **Installation du gestionnaire de démarrage**
    - Choisissez d'installer GRUB pour gérer le démarrage du système.

10. **Finalisation de l'installation**
    - Une fois l'installation terminée, retirez l'image ISO de Debian (allez dans **Configuration** -> **Stockage** et supprimez l'ISO du lecteur) et redémarrez la machine virtuelle.

11. **Configuration initiale**
    - Lors du premier démarrage, configurez les paramètres de votre système (date, heure, utilisateur, etc.).

## Résolution de problèmes

- Si vous avez oublié votre mot de passe, vous pouvez le réinitialiser via GRUB :
    1. Au démarrage, appuyez sur `Shift` pour afficher le menu GRUB.
    2. Sélectionnez le mode de récupération et démarrez.
    3. Accédez à la ligne de commande et utilisez `passwd nom_utilisateur` pour changer le mot de passe.

## Vérification de l'installation

Après l'installation, vous pouvez vérifier la version de Debian avec la commande suivante :
```bash
lsb_release -a

```

# Installation d'Edi (IntelliJ IDEA et Git) et Hébergement sur GitHub

Ce document décrit les étapes nécessaires pour installer IntelliJ IDEA, Git, et configurer un projet sur GitHub.

## Prérequis

- Un ordinateur avec une connexion Internet.
- Java Development Kit (JDK) installé (si nécessaire pour IntelliJ). Téléchargez-le depuis le [site officiel de Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) ou [AdoptOpenJDK](https://adoptopenjdk.net/).

## Étapes d'installation

### 1. Installation d'IntelliJ IDEA

1. **Téléchargement**
   - Allez sur le [site officiel d'IntelliJ IDEA](https://www.jetbrains.com/idea/download/) et téléchargez la version Community (gratuite) ou Ultimate.

2. **Installation**
   - Exécutez le fichier d'installation téléchargé.
   - Suivez les instructions de l'assistant d'installation.
   - Au besoin, sélectionnez les options d'installation supplémentaires (comme les plugins ou les configurations d'environnement).

3. **Configuration initiale**
   - Lancez IntelliJ IDEA.
   - Configurez les paramètres initiaux selon vos préférences (thème, plugins, etc.).

### 2. Installation de Git

1. **Téléchargement**
   - Allez sur le [site officiel de Git](https://git-scm.com/downloads) et téléchargez l'installateur pour votre système d'exploitation.

2. **Installation**
   - Exécutez le fichier d'installation et suivez les instructions.
   - Vous pouvez laisser les options par défaut ou les personnaliser selon vos besoins.

3. **Vérification de l'installation**
   - Ouvrez un terminal (ou Git Bash) et exécutez :
     ```bash
     git --version
     ```

### 3. Configuration de Git

1. **Configurer votre nom et votre adresse e-mail**
   - Exécutez les commandes suivantes dans le terminal :
     ```bash
     git config --global user.name "Votre Nom"
     git config --global user.email "votre.email@example.com"
     ```

2. **Configurer l'éditeur par défaut (facultatif)**
   - Si vous utilisez IntelliJ IDEA, vous pouvez le définir comme éditeur par défaut avec :
     ```bash
     git config --global core.editor "path/to/idea"
     ```

### 4. Création d'un dépôt Git et hébergement sur GitHub

1. **Créer un compte GitHub**
   - Inscrivez-vous sur [GitHub](https://github.com/) si vous n'avez pas de compte.

2. **Créer un nouveau dépôt sur GitHub**
   - Cliquez sur le bouton **New** sur la page d'accueil de GitHub.
   - Donnez un nom à votre dépôt et choisissez la visibilité (public ou privé).
   - Cliquez sur **Create repository**.

3. **Initialiser un dépôt local**
   - Dans votre terminal, naviguez vers le répertoire de votre projet et exécutez :
     ```bash
     git init
     ```

4. **Ajouter des fichiers et valider**
   - Ajoutez des fichiers au dépôt avec :
     ```bash
     git add .
     ```
   - Effectuez une première validation :
     ```bash
     git commit -m "Initial commit"
     ```

5. **Lier le dépôt local à GitHub**
   - Ajoutez l'URL de votre dépôt GitHub en tant que dépôt distant :
     ```bash
     git remote add origin https://github.com/votre_utilisateur/votre_depot.git
     ```

6. **Pousser les modifications vers GitHub**
   - Envoyez vos modifications au dépôt distant :
     ```bash
     git push -u origin master
     ```

## Vérification de l'installation

Après l'installation et la configuration, vous pouvez vérifier que tout fonctionne correctement en exécutant des commandes Git dans IntelliJ IDEA ou dans le terminal.

Pour plus d'informations sur l'utilisation d'IntelliJ IDEA et de Git, consultez la documentation officielle :
- [IntelliJ IDEA Documentation](https://www.jetbrains.com/idea/documentation/)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Documentation](https://docs.github.com/en)

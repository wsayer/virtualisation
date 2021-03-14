# Installation VirtualBox

Télécharger la nouvelle version sur le site : 
* https://www.virtualbox.org/

Etre root pour exécuter la commande d'installation suivante :

\# dpkg -i virtualbox-6.1_6.1.10-138449~Debian~buster_amd64.deb

Erreurs de dépendances ont été rencontrées lors de l'installation :

```
dpkg: des problèmes de dépendances empêchent la configuration de virtualbox-6.1 :
 virtualbox-6.1 dépend de psmisc ; cependant :
  Le paquet psmisc n'est pas installé.
 virtualbox-6.1 dépend de libcurl4 (>= 7.16.2) ; cependant :
  Le paquet libcurl4 n'est pas installé.
 virtualbox-6.1 dépend de libqt5core5a (>= 5.11.0~rc1) ; cependant :
  Le paquet libqt5core5a n'est pas installé.
 virtualbox-6.1 dépend de libqt5gui5 (>= 5.4.0) ; cependant :
  Le paquet libqt5gui5 n'est pas installé.
 virtualbox-6.1 dépend de libqt5opengl5 (>= 5.0.2) ; cependant :
  Le paquet libqt5opengl5 n'est pas installé.
 virtualbox-6.1 dépend de libqt5printsupport5 (>= 5.0.2) ; cependant :
  Le paquet libqt5printsupport5 n'est pas installé.
 virtualbox-6.1 dépend de libqt5widgets5 (>= 5.11.0~rc1) ; cependant :
  Le paquet libqt5widgets5 n'est pas installé.
 virtualbox-6.1 dépend de libqt5x11extras5 (>= 5.6.0) ; cependant :
  Le paquet libqt5x11extras5 n'est pas installé.

dpkg: erreur de traitement du paquet virtualbox-6.1 (--install) :
 problèmes de dépendances - laissé non configuré
Traitement des actions différées (« triggers ») pour systemd (241-7~deb10u1) ...
Traitement des actions différées (« triggers ») pour desktop-file-utils (0.23-4) ...
Traitement des actions différées (« triggers ») pour mime-support (3.62) ...
Traitement des actions différées (« triggers ») pour hicolor-icon-theme (0.17-2) ...
Traitement des actions différées (« triggers ») pour shared-mime-info (1.10-1) ...
Des erreurs ont été rencontrées pendant l'exécution :
 virtualbox-6.1
```

A l'exécution de virtualbox, voici l'information que nous avons :

\# /usr/bin/virtualbox

```
WARNING: The vboxdrv kernel module is not loaded. Either there is no module
         available for the current kernel (4.19.0-6-amd64) or it failed to
         load. Please recompile the kernel module and install it by

           sudo /sbin/vboxconfig

         You will not be able to start VMs until this problem is fixed.
/usr/lib/virtualbox/VirtualBox: error while loading shared libraries: libQt5Core.so.5: cannot open shared object file: No such file or directory
```

Cette erreur décrit l'absence de la librairie libQt5 qu'il faut installer : 

\# apt-get update

\# apt-get install libqt5gui5

Si vous avez des erreurs au moment de l'installation de **libqt5gui5**, alors exécuter la ligne de commande suivante :

\# apt --fix-broken install

Exécutez virtualbox via l'interface graphique **Applications / Système** ou via la ligne de commande suivante :

\# /usr/bin/virtualbox &

Ensuite, télécharger l'extension **Oracle VM VirtualBox Extension Pack**.

Dans le Gestionnaire de fichier, double cliquez sur l'extension **Oracle_VM_VirtualBox_Extension_Pack-6.1.10.vbox-extpack** qui exécutera l'application **Virtualbox** et vous n'aurez plus qu'à installer cette extension.

Vous pouvez également utiliser la ligne de commande pour exécuter l'installation de l'extension :

\# /usr/bin/virtualbox Oracle_VM_VirtualBox_Extension_Pack-6.1.10.vbox-extpack

Avant de créer une VM, veuillez installer les applications **gcc** et **linux-headers-amd64** :
\# apt-get install gcc

\# apt-get install linux-headers-amd64

\# apt-get install build-essential linux-headers-$(uname -r)

\# /sbin/vboxconfig 

Vous pouvez à présent exécuter Virtualbox et créer une machine virtuelle et procéder à son installation.




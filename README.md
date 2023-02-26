

 Ports group, VM Kernel


Vmotion vcernter et ses fonctionnalités
Caractéristiques de choi des disques

### RDS 
* Remote Desktop Services (RDS) est une plateforme de virtualisation qui offre des options de déploiement flexibles pour la prestation d’applications virtualisées et l’accès sécurisé aux postes de travail mobiles et distants. Il peut être déployé sur Windows Server 2016 pour une utilisation sur site, Microsoft Azure pour les déploiements cloud, et à travers diverses solutions partenaires. RDS offre une virtualisation de session ou une infrastructure de bureau virtuel (VDI) ou une combinaison des deux, selon les besoins de l’utilisateur. Dans ces environnements de virtualisation, les administrateurs peuvent publier des ordinateurs de bureau ou des applications RemoteApps individuelles.
* Pour un déploiement RDS, il faut au minimum 1 hôte de session de Bureau à distance
* **RD Broker** :gère les connexions entrantes de bureau à distance aux fermes de serveurs RD Session Host. RD Connection Broker gère les connexions aux deux collections de postes de travail complets et collections d’applications distantes
* **RD Web Interface** :  permet aux utilisateurs d’accéder à l’infrastructure de bureau à distance de votre organisation au moyen d’un navigateur Web compatible. 
* **RD Session Host Server** : contient les applications basées sur session et les ordinateurs de bureau que vous partagez avec les utilisateurs. Les utilisateurs accèdent à ces postes de travail et applications via l’un des clients Remote Desktop fonctionnant sous Windows, MacOS, iOS et Android. 
* **Une collection RDS** contient les applications et les ordinateurs de bureau que vous souhaitez mettre à la disposition des utilisateurs. Après avoir créé la collection, publiez-la pour que les utilisateurs puissent y accéder. L'utilisation de **plusieurs collections RDS** permet aux administrateurs de gérer les ressources informatiques de manière efficace, d'isoler les environnements et de personnaliser les paramètres pour différents groupes d'utilisateurs. Cela permet également de contrôler l'accès des utilisateurs aux différentes applications et bureaux virtuels. **Un hôte de session RD ne peut pas être membre de plus d’une collection.** Si vous souhaitez créer plusieurs collections, alors plus de serveurs hôtes de session sont nécessaires.
* Avantages :
    * **Rapide et abordable** : RDS est déjà inclus avec Windows Server® ; les utilisateurs doivent simplement s'assurer qu'ils ont les bonnes licences, et ils peuvent commencer immédiatement.
    * **Flexibilité au niveau des périphériques** : les employés peuvent accéder aux applications à partir de n'importe quel appareil : ordinateurs, tablettes et téléphones Windows®, Apple® ou Android®. Pour en apprendre davantage voyez ce document Microsoft.
    * **Flexibilité de déploiement** : les utilisateurs peuvent déployer des hôtes basés sur des sessions pour une solution plus légère et plus rentable, ou profiter de fonctionnalités avancées à l'aide d'un modèle de déploiement VDI1.
    * **Haute disponibilité** : les rôles RDS sont simples à configurer et aident à prendre en charge la haute disponibilité afin que les utilisateurs puissent se connecter sans interruptions.
    * **Graphiques haut de gamme** : les utilisateurs peuvent attacher des GPU à leur serveur hôte ou mapper un GPU à une machine virtuelle pour offrir une meilleure expérience aux utilisateurs expérimentés.
    * **Aide à maintenir le contrôle** : RDS permet aux utilisateurs de maintenir une sécurité et un contrôle centralisés de leurs données avec de puissants outils de gestion et des scripts d'automatisation. Les applications et les données restent sous contrôle et le risque de perte ou de vol de données en raison d'appareils perdus, volés ou endommagés ou de cybercriminalité est considérablement réduit.

### Hyperviseurs

* Un hyperviseur est une plate-forme de virtualisation qui permet à plusieurs systèmes d’exploitation de travailler sur une même machine physique en même temps.

### Hyperviseur type 1 

* Un hyperviseur de type 1 est un système d’exploitation permettant de virtualiser des ordinateurs invités, des conteneurs, etc. Nous pouvons notamment noter ESXi, un OS d’hyperviseur développé par VMware, ou Proxmox. Ils peuvent être représentés de la façon suivante, par rapport à une architecture classique.

* Un hyperviseur de Type 1, ou natif, voire "bare metal" (littéralement "métal nu"), est un logiciel qui s’exécute directement sur une plateforme matérielle ; cette plateforme est alors considérée comme outil de contrôle de système d’exploitation. Un système d’exploitation secondaire peut, de ce fait, être exécuté au-dessus du matériel. L’hyperviseur type 1 est un noyau hôte allégé et optimisé pour ne faire tourner initialement que des noyaux de systèmes d’exploitation invités adaptés et optimisés à cette architecture spécifique, ces systèmes invités ayant "conscience" d’être virtualisés. Sur des processeurs ayant les instructions de virtualisation matérielle (AMD-V et Intel VT), le système d’exploitation invité n’a plus besoin d’être modifié pour pouvoir être exécuté dans un hyperviseur de type 1.Quelques exemples de tels hyperviseurs plus récents sont Xen, Oracle VM, ESX Server de VMware.

* Avantages : 
    * De façon générale, les hyperviseurs les plus avantageux sont ceux de type 1, enlevant une couche logicielle, libérant donc davantage de ressources destinées aux machines virtuelles qu’il héberge.
    * **La performance** : n’ayant pas à gérer les limitations inhérentes posées par un système d’exploitation, ils ont de meilleures performances.
    * **La sécurité** : ces hyperviseurs sont protégés des failles et des vulnérabilités liées au système d’exploitation.
    * **La vitesse** : l’accès direct au matériel entraîne une latence moindre.
    * Noyau système léger et optimisé
    * Outils de supervision
    * Permet l’exécution d’OS natifs
    * Usage d’instructions dédiées à la virtualisation (sinon émulation).


### hyperviseur de type 2

* Un hyperviseur de type 2, beaucoup plus connu par les particuliers, est une application pouvant émuler des machines virtuelles ou des conteneurs. VirtualBox d’Oracle, VMware Fusion/Workstation en sont de bons exemples

* Un hyperviseur de Type 2 est un logiciel qui s’exécute à l’intérieur d’un autre système d’exploitation. Un système d’exploitation invité s’exécutera donc en troisième niveau au-dessus du matériel. Les systèmes d’exploitation invités n’ayant pas conscience d’être virtualisés, ils n’ont pas besoin d’être adaptés. Quelques exemples de tels hyperviseurs sont VMware Workstation, VMware Fusion, l’hyperviseur open source QEMU, les produits MicrosoftVirtual PC et Virtual Server, VirtualBox d’Oracle, de même que Parallels Workstation de SWsoft et Parallels Desktop.

###  VMware ESX

* VMware vSphere est un logiciel d’infrastructure de Cloud computing de l’éditeur VMware, c’est un hyperviseur de type 1 (Bare Metal), basé sur l’architecture VMware ESXi.VMware vSphere nécessite une configuration matérielle restreinte précisée dans le guide de comptabilité VMware. La gestion de ce serveur hôte peut se faire via plusieurs possibilités : par le navigateur Web avec une connexion directe, par une console cliente avec une connexion directe ou par un outil de gestion centralisée nommé VMware vCenter Server qui permet d’administrer l’ensemble des machines virtuelles, des hôtes physiques, de leurs ressources et des options de l’environnement (High Availability, vMotion, Storage vMotion, Distributed Resource Scheduler, Fault Tolerance) depuis une seule console.


* **Le vSwitch** est responsable de l'acheminement du trafic réseau au VMkernel, au VM Network, et au Service Console (ESX).

* **VMkernel** permet de créer des cartes réseaux virtuelles pour mieux gérer les différents Vlan. 

* **Une vm port groupe** permet de faire un parallèle avec les VLAN, qui permettent de compartimenter les ports d’un switch physique.

* **VMKERNEL** : Ce module « noyau » est le "cerveau" de VMware ESX ; il permet de gérer et de hiérarchiser l'ensemble des ressources matérielles (mémoire, processeur, disques, réseaux) en fonction de chaque serveur. De plus, c'est ce noyau qui est chargé de toute la gestion des ressources physiques pour ESX.

* **Un datastore** est une entité de stockage virtuel gérable créée par les hôtes VMware ESX/ES0Xi, généralement utilisée comme dépôt pour les fichiers de machines virtuelles, y compris les fichiers journaux, les scripts, les fichiers de configuration, les disques virtuels, etc.

* **NFS (Network Filesystem Storage)** : Il s’agit d’un stockage connecté au réseau ( Network attadched storage ) qui peut être partagé sur un cluster dans vSphere. Il permet à un utilisateur sur un ordinateur client d’accéder à des fichiers sur un réseau similaire au stockage local. Les volumes NFS sont créés à la fin du stockage, puis vous devez les ajouter sur ESXi en tant que datastore.
    * Avantages :
        * Processus de montage du systeme de fichier transparent
        * Compatible avec linux, w, mac
        * même fichiers accessibles par +sieurs clients
        * les machines partagent les mm appli
        * centralisation des données -6> administration + facile

* **SCSI** : permet de virtualiser un disque dur, apparaissent sur une machine virtuelle comme différents types de contrôleurs basés sur des blocs

* **NTP** est un protocole de synchronisation de temps réseau à faible coût et tolérant les pannes, utilisé pour aligner les horloges informatiques sur l’heure UTC. ESXi dispose d’une capacité NTP intégrée, y compris un port de l’implémentation de référence et les API du noyau nécessaires pour le supporter.

**Le cloisonnement** : chaque système d’exploitation a un fonctionnement indépendant, et ne peut interférer avec les autres en aucune manière.
**La transparence** : le fait de fonctionner en mode virtualisé ne change rien au fonctionnement du système d’exploitation et a fortiori des applications. La transparence implique la compatibilité : toutes les applications peuvent tourner sur un système virtualisé, et leur fonctionnement n’est en rien modifié.

### Raids 

* 0 : Stripping : données écrites à travers tous les lecteurs + rapide mais perte d'un disque = perte des données

* 1 : Mirroring : données du disque primaire sont dupliquées dans un autre = sauvegarde si un disque tombe en panne

* 01 : 0+1 = par ex 2 raid 0 ( un mirrorer ) donc ça cré un raid 1 

* 10/1+0 : Le raid 0 est partagé entre les 2 matrices raid 1

* 5 : compromis entre la tolérance de pannes, la rapidité et le coût.

Fonctionne avec un disque de parité. a + b = c, c stocké sur le disque de parité. Si on perd une donnée, on peut faire c - a = b, par exemple.



### vCenter 

vCenter est un composant de vSphere de VMware. Il est conçu pour offrir des capacités de gestion de serveur avancées à travers une plateforme centralisée. Il offre également une meilleure visibilité dans les environnements cloud hybrides, tout en automatisant et en fournissant une infrastructure virtuelle. De plus, vCenter vous permet de gérer les hôtes ESXi, ainsi que les machines virtuelles.

ESXi et vCenter sont deux composants différents de vSphere. vCenter est un logiciel avancé de gestion de serveur généralement déployé comme une machine virtuelle Linux préconfigurée, tandis que ESXi est un hyperviseur virtualisé qui est installé uniquement sur les machines physiques. Ces deux éléments font partie de la solution vSphere.

Il existe deux options pour déployer un serveur vCenter. Il peut être installé sur un serveur Windows physique ou virtuel, ou peut être déployé au moyen d’une appliance Linux OVA dans l’environnement virtuel lui-même.

* **vSphere vMotion** : SvMotion permet une migration à chaud sans interruption de service des charges de travail d’un serveur à un autre ( migration d'une vm vers un autre Datastore sans interruption )
    * Migrations à chaud : 
        * Optimiser automatiquement les machines virtuelles au sein de pools de ressources
        * Effectuer une maintenance matérielle sans planifier d’interruption de service ni gêner le fonctionnement de l’entreprise
        * Déplacer des machines virtuelles de serveurs défaillants ou peu performants
    * Automatiser et planifier les migrations
        * Migrer plusieurs machines virtuelles exécutant tout système d’exploitation sur tout type de matériel et de stockage pris en charge par vSphere, combiné à une piste d’audit
        * Identifier le placement optimal d’une machine virtuelle en quelques secondes


* **HA** : (Haute disponibilité) c’est la capacité d'un système à être fiable et disponible à tout moment, malgré les défaillances des composantes du système. ( fonctionnalité de vmotion, c'est le principe du **failover** : si un esx tombe, les vm sont migées ves un autre esx)

* **DRS**: (Dynamic Resource Schedulin) permet d'optimiser l'utilisation des ressources en répartissant les charges de travail virtuelles sur des hôtes esx.

* **Un cluster** est un groupe de serveurs ou de nœuds de calcul qui travaillent ensemble pour effectuer des tâches plus complexes et augmenter la disponibilité et la tolérance aux pannes d'un système.

* **DPM** : La fonction Distributed Power Management (DPM) de vSphere permet à un cluster DRS de réduire sa consommation d'énergie en activant et désactivant des hôtes sur la base de l'utilisation des ressources de cluster.

* **Fault tolerance** : Reprodui l'image d'une vm sur un autre hôte périodiquement, réduis le temps d'indisponibilité 

* Il existe plusieurs options pour gérer un vCenter:
    * vSphere Client: c'est l'interface graphique de base pour gérer vCenter et les hôtes ESXi.
    * vSphere Web Client: une version web de l'interface de gestion de vCenter qui peut être utilisée à partir d'un navigateur web.
    * vSphere HTML5 Web Client: une version plus moderne de l'interface de gestion de vCenter qui utilise HTML5 et peut être utilisée à partir d'un navigateur web.
    * PowerCLI: une interface de ligne de commande basée sur PowerShell pour automatiser les tâches de gestion de vCenter.
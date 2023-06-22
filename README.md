Commandes 

//start un new project
dotnet new webapi -o TodoApi
cd TodoApi

//ajout du package
dotnet add package Microsoft.EntityFrameworkCore.InMemory
code -r ../TodoApi

//run du project
dotnet run

//droits certificat HTTPS
dotnet dev-certs https --trust


# Cas concret d'étude pour ce cours
Nous allons prendre en exemple le cas d'une société qui vend des véhicules en ligne.

# Premiere grande famille de design pattern : Les patterns de construction
Autre site pour la définition des design patterns : https://goprod.bouhours.net/?page=pattern&pat_id=10 
### Le pattern Abstract Factory
![Alt text](/resources/pattern.png)

Le but étant de fabriquer des objets regroupés en famile sans avoir a connaitre les classes cibles destinées a la fabrication de ces objets 

# Diagramme UML
![Alt text](/resources/pattern2.png)

On créer une instance de FabriqueVéhicule() qui implémentera les interfaces des autres méthodes

### Le pattern Builder
![Alt text](/resources/pattern3.png)

Le but étant d'abstraire la construction d'objets complexes de leur implémentation de sorte qu'un client puisse créer des objets complexes sans avoir a se préocupper des différences d'implémentation

###  Le pattern Factory Method
![Alt text](/resources/pattern4.png)

Le but étant d'introduire une méthode abstraite de création d'objet en la reportant aux sous-classes concretes la création effective

###  Le pattern Singleton
![Alt text](/resources/pattern4.png)

Le but étant d'avoir une classe instanciée une seule fois dans le projet et de fournir une méthode de classe qui permet de fournir cette instance unique

### Le pattern Prototype
![Alt text](/resources/pattern5.png)

Le but étant d'avoir une instance d'un prototype (objet existant) d'une classe. Ces prototypes sont "clonables"

# Deuxième grande famille de design pattern : Les patterns de structuration
L’objectif des patterns de structuration est de faciliter l’indépendance de l’interface d’un objet ou d’un
ensemble d’objets vis-à-vis de son implantation. Dans le cas d’un ensemble d’objets, il s’agit aussi de
rendre cette interface indépendante de la hiérarchie des classes et de la composition des objets.
En fournissant les interfaces, les patterns de structuration encapsulent la composition des objets,
augmentant le niveau d’abstraction du système à l’image des patterns de création qui encapsulent la
création des objets. Les patterns de structuration mettent en avant les interfaces.
L’encapsulation de la composition est réalisée non pas en structurant l’objet lui-même mais en transférant
cette structuration à un second objet. Celui-ci est intimement lié au premier objet. Ce transfert de
structuration signifie que le premier objet détient l’interface vis-à-vis des clients et gère la relation avec le
second objet qui lui gère la composition et n’a aucune interface avec les clients externes.

### Le pattern Adapter
![Alt text](/resources/pattern6.png)

Le but étant d'adapter l'interface d'une classe afin qu'elle puisse intéragir avec un client. En temps normal, les classes ne pourraient pas fonctionner ensemble en raison d'incompatibilité

### Le pattern Decorator
![Alt text](/resources/pattern7.png)

Le but étant d'ajouter des fonctionnalisés supplémentaires a un objet pour étendre les fonctionnalités sans modifier son interface

-Notre application souhaite ajouter dynamiquement des fonctionnalités a un objet sans modifier son interface, autrement dit sans avoir a modifier les clients de cet objet

-une application doit gerer des fonctionnalités qui peuvent etre retirées dynamiquement

-l'utilisation de l'heritage n'est pas une option car la hierarchie d'objets est deja trop complexe

### Le pattern Bridge
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

Exemple de singleton:

```
    public class Vendeur
    {
        private static Vendeur _instance = null;

        private Vendeur() {
        }

        public static Vendeur Instance()
        {
            if (_instance == null)
                _instance = new Vendeur();
            return _instance;
        }
    }
    static void Main(string[] args)
    {
        Vendeur vendeur1 = Vendeur.Instance();
        Vendeur vendeur2 = Vendeur.Instance();

        vendeur1.sales = 10;
        if(vendeur2.sales == vendeur1.sales)
            Console.WriteLine("Singleton fonctionnel");
        else
            Console.WriteLine("Singleton non fonctionnel");
    }
```

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
Version 1
![Alt text](/resources/pattern8.png)
Version 2
![Alt text](/resources/pattern8-2.png)

Le but étant de  dé-coupler le comportement de l'interface de l'implémentation de l'objet.

### Le pattern Composite
Version 1
![Alt text](/resources/pattern9.png)

Version 2
![Alt text](/resources/pattern9-2.png)

le but étant d'organiser les objets en arborescence pour les traiter comme des entités individuelles.

### Le pattern Decorator
Version 1
![Alt text](/resources/pattern10.png)

Version 2
![Alt text](/resources/pattern10-2.png)
le but étant d'ajouter de manière dynamique des fonctionnalités supplémentaires à un objet sans avoir à modifier son interface


# Troisième grande famille de design pattern : Les patterns de comportement
Les patrons comportementaux s’occupent des algorithmes et de la répartition des responsabilités entre les objets.

### Le pattern Chain Of Responsability
![Alt text](/resources/pattern11.png)

Version 1
![Alt text](/resources/pattern11-1.png)

Version 2
![Alt text](/resources/pattern11-2.png)

Le but étant de traiter une demande de manière hiérarchique. Chaque élément peut traiter la demande ou de la transmettre a l'élément suivant de la chaîne.

### Le pattern Command

Il permet de transformer une requête en objet

### Le pattern Iterator

Version 1
![Alt text](/resources/pattern12.png)

Version 2
![Alt text](/resources/pattern12-2.png)

Le but étant d'accéder aux éléments d'une liste, d'un tableau ou d'une autre collection un par un, sans se soucier de la façon dont ils sont organisés en interne

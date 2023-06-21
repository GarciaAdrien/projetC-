
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


Description des patterns
-nom
-description
-exemple de code sous forme de diagramme UML
la structure standard (abstraite)
-un exemple de code


# Cas concret d'étude pour ce cours
Nous allons prendre en exemple le cas d'une société qui vend des véhicules en ligne.

# Premiere grande famille de design pattern : Les patterns de construction
Autre site pour la définition des design patterns : https://goprod.bouhours.net/?page=pattern&pat_id=10 
### Le pattern Abstract Factory
![Alt text](resources/patterns.png)
Le but étant de fabriquer des objets regroupés en famile sans avoir a connaitre les classes cibles destinées a la fabrication de ces objets 

# Diagramme UML
![Alt text](resources/patterns2.png)
On créer une instance de FabriqueVéhicule() qui implémentera les interfaces des autres méthodes

### Le pattern Builder
![Alt text](resources/patterns3.png)
Le but étant d'abstraire la construction d'objets complexes de leur implémentation de sorte qu'un client puisse créer des objets complexes sans avoir a se préocupper des différences d'implémentation

###  Le pattern Factory Method
![Alt text](resources/patterns4.png)
Le but étant d'introduire une méthode abstraite de création d'objet en la reportant aux sous-classes concretes la création effective

###  Le pattern Singleton
![Alt text](resources/patterns4.png)
Le but étant d'avoir une classe instanciée une seule fois dans le projet et de fournir une méthode de classe qui permet de fournir cette instance unique

### Le pattern Prototype
![Alt text](resources/patterns5.png)
Le but étant d'avoir une instance d'un prototype (objet existant) d'une classe. Ces prototypes sont "clonables"
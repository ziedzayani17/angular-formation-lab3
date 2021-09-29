# LAB 3
## _Les points à voir :_

- Création et utilisation des services
- Injection des services

<br/>

## _prérequis :_

- Récuperer le code du LAB2 (https://github.com/ziedzayani17/angular-formation-lab2.git)
<br/>
<br/>

### 1. Créer une interface *IMovieService* avec une méthode *getMovies()*

<br/>
<br/>
  
### 2.a. Créer une classe *MockMovieService* qui implémente l'interface *IMovieService*

<br/>
<br/>

### 2.b créer le service avec angular cli *ng generate service services/movie*

### 3. Implémenter la méthode *getMovies()* pour retourner la liste des films statique existe déja dans le composant

<br/>
<br/>

### 4.a. Ajouter ce service dans le mécanisme d'injection d'Angular avec le décorateur *@Injectable({ providedIn: 'root' })* en cas de création manuelle

<br/>
<br/>

### 4.b. Ajouter ce service dans le mécanisme d'injection d'Angular avec l'ajout du service dans *providers: []*


>Enregistrer ce service, soit en l’ajoutant aux providers d’un composant, ou aux
>providers du module, ou, à partir d’Angular 6.0, en utilisant providedIn dans @Injectable() comme
>ci-dessus.
>root indique que le service disponible via toute l'application
>

>On peut manipuler la déclaration du provider pour utiliser un vrai *MovieService* ou un mock *MockMovieService* 
```js
providers: [
// we provide a true service
{ provide: MovieService, useClass: MockMovieService }
]
//ou
providers: [
// we provide a fake service
{ provide: MovieService, useClass: MovieService }
]
```

### 5. Injecter le service dans le composant *MoviesComponent*

### 6. Injection manuelle 
>on peut récuperer l'injecteur dans le code et jouer avec;
>
```js
import { Injector } from ‘@angular/core’;

const injector = Injector.create({providers: [{provide: MockMovieService, deps: []}]});
this.movies = injector.get(MockMovieService).getMovies();
```






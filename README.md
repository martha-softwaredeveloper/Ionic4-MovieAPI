# Ionic 4 - Movie App 
[How to Build Your First Ionic 4 App with API Calls](https://youtu.be/3QPbBJgNF94)

<img src="" width="500"/>

## App Configuration
ionic start movieApp blank --type=angular
ionic g page pages/movies
ionic g page pages/movieDetails
ionic g service services/movie

0. Delete the default home page
1. At app.module.ts, import HttpClientModule
2. At app-routing.module.ts, remove home, set redirect to movies page and add :id to movies details page

## Build Movie Service with APIs
1. At movie.service.ts:
 a) create and set url and apikey variables
 b) Create a enum for search type
 c) Import httpclient and add to constructor
 d) Create searchData func and getDetails func to return only the search results
 e) Import map from rxjs/operator 

 2. At movies.page.ts
  a) Create variables
  b) Create searchChanged func to get service's results
  c) 2 Approaches to get data out of the returned observable: Subscribe or ngFor directive with a sync pipe

3. At movies.page.html
 a) Create ion list and item to display results
 b) Add router link to item for details page
 c) Add ion searchbar and ion select
    1. ngModel updates the variables' value in movies.page.ts
    2. ionChange can call searchChanged func to pass latest event
 Enhancements:
 d) remove padding
 e) Add avatar image at start slot
 f) Add icons for type at end slot

## Build Movie Details page
1. At movie-details.page.ts:
  a) Import ActivedRouted and add it to constructor. This is used to grab id passed at URL path at ngOnInit
  b) Import movie service
  c) At ngOnInit, get results from getDetails func
  d) Create a openWebsite func

2. At movie-details.page.html
 a) Add movie's genre in ion title page but with a optional (?)
 b) Add a back button with defaultHref="/" to go to root
 c) Add ion card component with *ngIf="information" to display card if information exists, also to remove console errors
 d) Add movie's cover with customed css

 ## Author
 Simon Grimm
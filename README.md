### Angular-Design-Patterns-Imlementation


This Project will cover the following Industry-level Design Patterns for Angular Development.

1 VsCode Tooling for Angular

	-----> Angular Language Service
	-----> Angular Sinppets
	-----> npm Intellisense


2 RxJs Subscription

	How you multiple observable subscription.
	 note subscribe is like calling to events() it also means memory leaks so
	 to avoid memory leask (as some client open the client side that is
	 application components for like 2 months and the compoenent is alive
	 which mean ngOnInIt(){} is alive and you does not unsubscrieb the events
	 and hence you are getting data and it is staring bulking around
	 what you need to do is to unsubscribe for example
	 
	 
	 declare a variable like
	 variable: Subscription;
	 
	 ngOnInIt(){
	 this.variable.sbscribe(()=>{});
	 }
	 
	 ngOnDestroy(){
	 this.variable.unsubscribe();
	 }

	Or use SubSInk using npm install subsink.
	
	
	Note:
	Any subscription that we have created should be unsucsrcibe() by us
	and Any subscription created by angular for example using http calls
	that is destroy by angular itself as it use rxjs methods.
	
	
	
	How to share data across your app???
	
	1 A service(any injectable class with methods)  can does this job.
	
	Before using it please add Redux Devtools from chrome extensions
	2 Now in React there is a package called Redux, in Vue.js its called
	  Vuex and in Angular its called NgRx. Ngrx is a group of Angular 		libraries for reactive extensions. Ngrx/Store implements the Redux pattern 		using the well-known RxJS observables of Angular 2.
	  
	  
	NgRx has following methods
	
	Actions
	Effects
	Reducers
	Dispatchers
	Selectors
	
3 NgRx version 8 and @ngrx/data





4 Preloading Strategies




5 API strategies





6 Angular Debugging





7 Compound Debugging

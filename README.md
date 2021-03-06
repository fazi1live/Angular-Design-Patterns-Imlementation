<p align="center">
  <img src="https://angular.io/assets/images/logos/angular/angular.svg" alt="angular-logo" width="120px" height="120px"/>

  # Angular-Design-Patterns-Imlementation

  <br>
  <i>Angular is a development platform for building mobile and desktop web applications
    <br> using Typescript/JavaScript and other languages.</i>
  <br>
</p>

---

### Angular LifeCycle Hooks
<img src="https://codecraft.tv/courses/angular/components/lifecycle-hooks/images/lifecycle-hooks.png" width="500" height="500">

#### There are Two Types of Angular LifeCycle Hooks.
These are the hooks for components or directives, in call order:<br>

:heavy_check_mark:constructor()<br>
:heavy_check_mark:OnInit<br>
:heavy_check_mark:DoCheck<br>
:heavy_check_mark:OnChanges<br>
:heavy_check_mark:OnDestroy<br>
And these are the hooks for a component’s children components:<br>

:heavy_check_mark:AfterContentInit<br>
:heavy_check_mark:AfterContentChecked<br>
:heavy_check_mark:AfterViewInit<br>
:heavy_check_mark:AfterViewChecked<br

<br>

#### Hirerchary of Angular LifeCycle Hooks
:arrow_forward: How Angular Life Cycle Hooks Works??
Once the Angular Application Boostrap and The Appcomponent is called it then start initialzing the compoenents. Once the Component is initialized first
thing is called 

1 Constructor() // This is not Angular Life-Cycle its the Basic Concept of OOP after that<br>
2 ngOnChanges() // This Life-Cycle is called before the ngOnInIt() and this is called when any particual input values chanes coming from another component<br> 
3 ngOnInIt() // This life cycle is called only one time when component is initialized.<br>
4 ngDoCheck() // This life cycle is called only one time when component is initialized(one Time) and then keep on called after ngonchanges() or our component rerenderd<br>
:child: Component's Children Component 4(a) ngAfterContentInit() // As this LifeCycle is for component's children component so it mean when you want to send the content (not input variables) from parent to child and when they go from parent to child and initilize then this hook will be called.<br><br>
:key: Here is the snippet: <br>
:white_haired_man: Parrent Component<br>
```Html
<app-child *ngIf="_ShowChild" [IncomingValueForChild]="_ParentData"><br>
    <p #child >child</p><br> //Here I am sending the content that is p tag to the child without using input decorator here ngAfterContentInIt(LifeCycle) will triggered
</app-child><br>
:baby:Child Component<br>
<ng-content> </ng-content><br> // ng-content selector will help you to render the content coming from parent to child and once it render then ngAfterContentInIt() will call<br>

```
In :white_haired_man: Parent Component I have used a template reference varible and pass it to child let me first show you the snippet then explain it.<br>
```Html
<p #child >child</p><br> //Parent

@ContentChild('child') _Child:any;<br> //Child Component.ts<br>
ngOnInit(): void {<br>
    console.log('COntent intiliazed',this._Child);//Undefined this._Child <br>
    }<br>
    ngOnChanges(changes: SimpleChanges): void { <br>
    console.log('COntent intiliazed',this._Child);//Undefined this._Child <br>
    }<br>
    ngAfterContentInit(): void {<br>
      console.log('COntent intiliazed',this._Child);<br>
  }<br>

```
  In the Above Snippet I deliberately called #Child reference variable in the following lifeCycle hooks and proved it that it is called only when the content from parent to child fully rendered or in ngAfterContentInIt()<br>
<br>
:child: Component's Children Component 4(b) ngAfterContencChecked() // This LifeCycle will called after ngAfterContentInIt(one Time) and then after every ngDoCheck(LifeCycle)<br>

:child: Component's Children Component 4(b) ngAfterContencChecked() // This LifeCycle will called after ngAfterContentInIt(one Time) and then after every ngDoCheck(LifeCycle)<br>
:child: Component's Children Component 4(b) ngAfterContencChecked() // This LifeCycle will called after ngAfterContentInIt(one Time) and then after every ngDoCheck(LifeCycle)<br>
5 ngOnDestroy() // This life cycle is called when the component is no longer exist/visible on DOM. ngOnDestroy() is very helpful<br>
to handle memory leaks for example subscribe() events or some other data manipulation it should be unsubscribe() or clear() in ngOnDestroy() to avoid<br>
memory leaks. A Code Example has given in the child component. 

---

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


[![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=fazi1live)](https://github.com/fazi1live/github-readme-stats)

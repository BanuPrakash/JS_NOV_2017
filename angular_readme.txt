
Angular 2/4/5
-------------

 MVC Framework for building web applications on client side

 RWD (Responsive Web Design ) and SPA (Single Page Application)

 RWD --> CSS3 libraries like Fondation/ Bootstrap

 SPA challenges:

 1) Dependecy Injection of Modules
 2) Data binding
 		a) One-way binding
 		b) Two-way binding
 3) Routing

 	http://adobe.com/products
 	http://adobe.com/locations
 	http://adobe.com/products/adobecc

 4) Cache

 Angular 1.x 		Angular 2+ 				React 				Vue

 --------------------------

 	Angular uses webpack to compile "TS" and create bundles

 	Angular is written in TypeScript (TSC compiles "ts" to "js")

 	TypeScript

 		class Person {
 			name:string;
 			age: number;

 			getName(): string {

 			}
 		}
---------------------------

	

	Angular Building blocks:

	a) Module
	b) Component
	c) Templates
	d) Service
	e) pipes
	f) directives

-----------------------------------------
	1) Install angular command line interface:
	npm i -g @angular/cli

	2) create angular application

		ng new customerapp

	3) cd customerapp
	  npm install

	4) We need VisualStudio Code

		Module needs to include all components, services, pipes, other dependent modules


	Generate customers component

		ng g c customers


		ng g c customers/customersCard
		ng g c customers/customersGrid



		<html>
			<app-root></app-root>
		</html>

		AppComponent HTML
				<app-customers></app-customers>

		CustomersComponent
				<app-customers-card></app-customers-card>
				<app-customers-grid></app-customers-grid>



		1) interploation [Expressions] 
			{{state}}
		2) [property] 
		3) (event)
		4) [(ngModel)]  for two-way binding

		ng g c customers/customerEdit

		ng g service common/data

		npm i -g json-server

 $ json-server --watch customers_orders.json --static . --port 3000

 Routing

 	a) in app-component.html include
 		<router-outlet></router-outlet>
 		This is a placeholder for components based on "Route"

 		Create <a routerLink=""> in HTML 

 	b) app.module
 		congiure
 			Routes
 		and 
 			in imports
 		import : [
 			RouterModule.forRoot(appRoutes)
 		]

----------------

	ng build --prod --aot

	
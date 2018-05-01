# EmberJS-Defining-Routes
The router matches the current URL with routes responsible for displaying template, loading data and setting up an application state.

Run this command

ember generate route routedemo

The following example shows how to define a route for displaying data. Open the .hbs file created under app/templates/. Here, we have 
created the file as routedemo.hbs with the following code −

<h2>My Books</h2>
<ul>
   <li>Java</li>
   <li>jQuery</li>
   <li>JavaScript</li>
</ul>
Open the router.js file to define URL mappings −

import Ember from 'ember';                    
//Access to Ember.js library as variable Ember
import config from './config/environment';
//It provides access to app's configuration data as variable config 

//The const declares read only variable
const Router = Ember.Router.extend ({
   location: config.locationType,
   rootURL: config.rootURL
});

//Defines URL mappings that takes parameter as an object to create the routes
Router.map(function() {
   this.route('routedemo');
});

export default Router;
Create the application.hbs file and add the following code −

//link-to is a handlebar helper used for creating links
{{#link-to 'routedemo'}}BookDetails{{/link-to}}
{{outlet}} //It is a general helper, where content from other pages will 
appear inside this section

Only routedemo.hbs,router.js and application.hbs files are included in this repository

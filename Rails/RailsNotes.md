You can run rails app on custom port like 8080,run
rails s -p 8080

It uses **CamelCase** for classes but **underscores** for filenames.

CamelCase means using uppercase within identifiers that consist of more than one word to help you make out the individual words.


*   To create rails app
        rails new <app name>
        
*   To start the web server
        rails s
    The default home page is at http://localhost:3000





### Scaffolding 
 
 Scaffolding generates code that allow us to perform CRUD operation in database. To create scaffolding
        
    rails scaffold example  <column>:<datatype>
    
Scaffolding's great, but some applications are so simple that you'll sometimes be better off building your app manually.
        

### Migration

It is a script that alters the structure of the underlying database.

    rake db:migrate

You can make changes to your table structure using a migration. To generate a migration that adds a column to a table, use the following command.

    rails migrate Add[column_name]To[table] <column>:<datatype>


### MVC architecture

1.  The model code manage how data is written and read read to your database. 

2.  The view is the part of application that is presented to the user(presentation layer).

3. The controller decides how the user **interacts** with the system, controlling what data is accessed from the model, and which parts of the view will present it.



# Create App Manually #
=======================

### Model

Models have **singular names** - so it's "user" not "users"

    rails g model [model_name] <column>:<datatype>
    
It'll generate two scripts within **app** and **db/migration** directory. 

To create a table for you in the database

    rake db:migrate
    
### Controller

Controllers have **plural names** - so it's "users" not "user"

     rails g controller [users] action1 action2 action3...
     
That command will generate a class file for your controller at                    **app/controllers/users_controller.rb**


 ### View
 
 The view is created with a page template. **Embedded Ruby(ERb)** creates web pages from template and this is part of the standard Ruby library.
 
### Routing

Routes tell Rails what code to run when a request is received for a URL

They are defined in **config/routes.rb**

```
    map.connect '/ads/:id', :controller=>'ads', :action=>'show'
    map.connect '/ads/', :controller=>'ads', :action=>'index'
    
```

### Retrieve data from db

finder method

#### Particular ID

To get the value of the parameter

params[:id]


To retrieve it from DB using finder method

@ad=Ad.find(params[:id])

The data from the record is converted into an **object** with attributes(like field in record).


#### All Records

@ad=Ad.find(:all)

The data is returned as an object called an array

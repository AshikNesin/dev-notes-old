### Read all elements within array using for loop

```erb
    for element_name in @my_array
        
        # Do something with element
        
     end
```

### Scriplets & Expression tags

A scriplet is a tag containing a piece of Ruby code and they are surrounded by <%.....%>

Whereas Expression tags are surrounded by <%= ..... %>

### Layout

A layout defines a STANDARD look for whole set of page templates.

A super-template

```
    <html>
    <head>
        <title><%= controller.action_name %></title>
        <%= stylesheet_link_tag 'default.css' %>
    <head>
    <body>
        <%= yield %>
    </body>
    </html>
 ```
 
### Create Forms
 
 You need a **form** to submit data and an action **method** to save it.
 
 
View(new.erb.html)
=====
 
```
     <% form_for(@user,:url=>{:action=>'create'}) do |f| %> 
     <%= f.text_field	:name %>	
     <%= f.text_area	:bio %>	
     <%= f.submit "Submit" %>
     <% end %>
     
```

The form object (@user) needs to be created in the controller before it can used in the form else it'll be assigned to **nil** by default.


Controller(users_controller.rb)
==========

```

	def new
	   @user=User.new
	end
```

#### Storing data to db
1. Rails sends the form data to the controller using the **params[...]** hash.

2. The controller can read the raw form data by looking at **params[:user]**. It then sends this value to User.new(...) to construct a new User object.

3. The User object that is returned by User.new(...) has attributes that match the value in the form fields.

```erb
	def create 
		@user = User.new(params[:user])
		@user.save
	end
```

When **save** is called on the model object, Rails inspects the attributes and generates a **SQL insert** stmt to update the db.

### Redirection

Redirect let the controller specify which view is displayed.

``` redirect_to "/view_name/#{@user.id} ```

### Updating Record


```erb

    def edit
        @user=User.find(params[:id])
    end
    
	def update 
		@user = User.find(params[:id])
        @user.update_attributes(params[:user])
	end
```

    map.connect 'users/:id/edit', :controller=>'users', :action=>'edit'
    
    map.connect 'users/:id/update', :controller=>'users', :action=>'update'

### Delete Record

```erb
    
    def destroy
        @user=User.find(params[:id])
        @user.destroy
        redirect_to '/users/'
    end
```

    map.connect 'users/:id/delete', :controller=>'users', :action=>'delete'


### Restricting access to a function

HTTP Authentication
===================

```
    class UserController < ApplicationController
        
        before_filter :check_logged_in, :only=>[:edit,:update]
        ....
        
    private
        def checked_logged_in
            authenticate_or_request_with_http_basic("NAME_OF_DOMAIN") do |username, password|
            username == "admin" && password == "hello_world"
            end
        end
        
      end # End of the class
            
```

### NOTES ###
=============

    @example.save saves a model object.
    
    @example.update_attributers update a model object.
    
    redirect_to lets the controller send the browser to a different URL.
    
    http_authentication makes adding security easy.
    
    params[...] is a **hash** which is like an array indexed by **name**
    
    **nil** is a special default object that means "no value"
    
    Inside Rails, calling methods on a nil onject causes errors
    
    "#{" and "}" can insert expressions into strings like "1+1 = #{1+1}"
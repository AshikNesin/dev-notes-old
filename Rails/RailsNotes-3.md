### Search Form

If you need a form that doesn't match a model object, use `form_tag` instead of `form_for`
 
`params[:field_name]` will give you the value of the field called `:field_name` in a non-model form
 
You can use `_tag` fields with a `form_tag` form.

```html

    <span style="text-align:right">
    <% form_tag "users/find" do %>
        <%= text_field_tag :search_string %>
        <%= submit_tag "Search" %>
    <% end %>
    <span>

```

```
    def find
        puts params[:search_string]
    end
```

### Finder

There is a finder for every attribute

`find_all_by_username(...)`

`find_all_by_email(...)`

The finder return an array of all matching objects.

Then we can use for loop to display it.

```
    <% for user in @users %>
        
        # Do something with user
        
        <%= link_to 'Show', user %>
        
        <%= link_to 'Edit', user %>
        
        <%= link_to 'Destroy', user,:confirm=>'Are you sure ?',:method => :delete %>
     
     <% end %>
     
```


### Search by username or email

```@users=User.find(:all,:conditions=>["username=? OR email=?",params[:username],params[:email]]) ```

find(:all,:conditions=>[....]) allows to specify the SQL used to select records form the database.

`form_tag` generates simple forms that are not bound to model objects.

Last Read => 206
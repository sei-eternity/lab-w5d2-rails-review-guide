## Form_for Method

Creates a form that allows the user to create or update the attributes of a specific model object.

The method can be used in several slightly different ways, depending on how much you wish to rely on Rails to infer automatically from the model how the form should be constructed.


```
<%= form_for :person do |f| %>
  First name: <%= f.text_field :first_name %><br />
  Last name : <%= f.text_field :last_name %><br />
  Biography : <%= f.text_area :biography %><br />
  Admin?    : <%= f.check_box :admin %><br />
  <%= f.submit %>
<% end %>
```

The variable f yielded to the block is a FormBuilder object that incorporates the knowledge about the model object represented by :person passed to form_for. Methods defined on the FormBuilder are used to generate fields bound to this model.



```
<%= f.text_field :first_name %>
```
Will expand to

```
<%= text_field :person, :first_name %>
```

## Resource-oriented style
 Further simplification is possible if the record passed to form_for is a resource, i.e. it corresponds to a set of RESTful routes, e.g. defined using the resources method in config/routes.rb. In this case Rails will simply infer the appropriate URL from the record itself. For example:
 ```
 <%= form_for @post do |f| %>
  ...
<% end %>
 ```
 is then equivalent to something like:

```
<%= form_for @post, as: :post, url: post_path(@post), method: :patch, html: { class: "edit_post", id: "edit_post_45" } do |f| %>
  ...
<% end %>
```
And for new recod

```
<%= form_for(Post.new) do |f| %>
  ...
<% end %>
```
```
<%= form_for @post, as: :post, url: posts_path, html: { class: "new_post", id: "new_post" } do |f| %>
  ...
<% end %>
```


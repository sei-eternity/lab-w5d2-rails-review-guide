# Associations
Association is a connection between two Active Record models.

## Types of Associations
Rails supports six types of associations:

- belongs_to
- has_one
- has_many
- has_many :through
- has_one :through
- has_and_belongs_to_many

## One to Many
A one-to-many association is the most common used relation. This association indicates that each instance of the model A can have zero or more instances of another model B and model B belongs to only one model A.

```Ruby
class ClassRoom < ApplicationRecord  
    has_many :students 
end 
````

```Ruby
class Student < ApplicationRecord
    belongs_to :class_room
end
```


the Studentd model contains one reference to the Classroom model in form of a foreign key

## References
[Active Record Associations - Ruby on Rails Guides](https://guides.rubyonrails.org/association_basics.html)
[Everything There Is to Know About Associations in Rails](https://dev.to/neshaz/everything-there-is-to-know-about-associations-in-rails-52ii)
## MVC Chart
[MVC chart](https://docs.google.com/spreadsheets/d/1EZoL2nEekHDspvy8riKYpSQfhslVTEHD4C4FHtsulRY/edit#gid=0)
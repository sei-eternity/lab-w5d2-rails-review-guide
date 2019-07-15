![Rails Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Ruby_On_Rails_Logo.svg/1200px-Ruby_On_Rails_Logo.svg.png)
# What are Rails partials
Partial templates - usually just called "partials" - are another device for breaking the rendering process into more manageable chunks. With a partial, you can move the code for rendering a particular piece of a response to its own file.
# Why do we use them?
1. Keeps your view clean and systematic, DRY Philosphy .
2. The ability to reuse some of the component amongst various view. Usually developer create a kind of shared/common folder where partial sits and are used amongst various view.
3. Easy to conditionally load partials using Rails’ “if” or “unless” statements
4. It is beneficial where a template needs to iterate over a collection and render a sub template for each of the elements.
5. Your different partials can also have different layouts.
6. Separating your view into partials can also help in in proper fragment caching (Fragment Caching) of some portion of you webpage. Better management.
<br>
## Resources
- [Rails Guides](https://guides.rubyonrails.org/layouts_and_rendering.html#using-partials)
- [Why Use Rails Partials](https://stackoverflow.com/questions/17453972/what-is-the-use-of-partials-in-rails)
Collapse




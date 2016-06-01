# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Inside an Ember Application Router you specify the paths for all the routes that the application will use.  Inside Ember routes you specify models hooks that will be used to get data for individual routes.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to '/campus/boston'}}Boston{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The second route is dynamic and nests the product id within products.
    The second route is an example of a masking path.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    You would create/add to a model for movies.  Something like:

    import Ember from 'ember';

    export default Ember.Route.extend({
      model: function(){
        return [
          {
          id: 123
          },
        ]
      }
    });
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    By creating a reference to the model.
    ```

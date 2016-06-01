# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Router: maps URL and determines which route is loaded
    Route: maps which Model gets loaded
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    <a>{{#link-to "campus.boston"}}Link to Boston{{/link-to}}</a>
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
    In the first route definition, the 'product' route is nested inside the 'products' route.
    In the second route definition, the 'product' route is defined outside the 'products' but is a subdirectory of the 'products'.

    I'm not sure if it is functionally any different.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    in the model, you have to pass [params.movie_id -1]
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    if i wanted to access the titles, then:

    {{#each model as |movie|}}
      <p>{{movie.name}}</p>
    {{/each}}

    model: function(params){
    return [
      {
        id: 1,
        name: 'movie1',
      },
      {
        id: 2,
        name: 'movie2',
      },
      {
        id: 3,
        name: 'movie3',
      },
    ]
  }
    ```

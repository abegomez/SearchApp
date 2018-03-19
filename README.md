# search-project

> A search app

Challenge - Build a search app.
Can be as simple as Google, one input with a list of results, but creativity will get you farther.
Here is our ODN search app as an example: http://odn.voyagersearch.com/navigo/search

Required - Keyword Filtering
Our search engine uses Solr. When performing a keyword search with ODN, you can see the
Solr request in the Chrome Dev Tools. Use that Solr call as a template for your app.
The q parameter allows you to filter by keyword. You can supply the other parameters in your
call, it's not important to know what they are for here, but some are required.

Frameworks
Use Angular 5+, Vue, or React

Design System
Use Project Clarity, Material design, or some modern design system.

Demo
Upload your code to Github for review and a build to Github Pages so we can run it live.

Bonus Points- Faceting
If you use the ODN filters on the right, you can perform Solr
faceting.The fq parameter allows you to filter by facets. Implement faceting similar to ODN.

Use Typescript

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

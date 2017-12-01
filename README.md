**SERVER SIDE RENDERING STARTER APP NODE + REACT**

you can use this starter app / boilerplate for you node + react projects.

Read next posts:

https://medium.com/walmartlabs/the-benefits-of-server-side-rendering-over-client-side-rendering-5d07ff2cefe8

https://medium.freecodecamp.org/what-exactly-is-client-side-rendering-and-hows-it-different-from-server-side-rendering-bd5c786b340d

https://medium.com/walmartlabs/the-benefits-of-server-side-rendering-over-client-side-rendering-5d07ff2cefe8

With Server Side Rendering, we want to render some basic pages, I don’t want to
mess around with authenticating users or complex conditionals because I usually
handle that in the Single Page App (SPA) way on the client side. This pretty
much means I want to render raw html and nothing else, leave the html the way it
was, but with the react ‘root’ element filled in with the route information.

It turns out that in React 16, there are now two different methods for rendering
on the client side: render() for when you are rendering the content solely on
the client side, and hydrate() for when you are rendering on top of server-side
rendered markup.

When developers talk about client-side rendering, they’re talking about
rendering content in the browser using JavaScript. So instead of getting all of
the content from the HTML document itself, you are getting a bare-bones HTML
document with a JavaScript file that will render the rest of the site using the
browser. This is a relatively new approach to rendering websites, and it didn't
really become popular until JavaScript libraries started incorporating it into
their style of development.

We are using server side rendering for two reasons: Performance benefit for our
customers Consistent SEO performance:

Due to the benefits of SSR, when we transformed our stack to React and Nodejs,
we put a lot of time and effort in optimizing SSR performance.

One of our key metrics for measuring performance is “above the fold” render. Our
Electrode framework that we open sourced has multiple modules to improve the
performance of SSR and I blogged previously about the benefit of those modules.
When we announced Electrode and its focus on SSR, I received tons of questions
and comments asking about the benefit of SSR. This blog post focuses on the
performance benefit of using SSR — Andrew Farmer and Patrick Hund did a great
job covering the SEO benefits.

For starters, instead of having the content inside the HTML file, you have a
container div with an id of root. You also have two script elements right above
the closing body tag. One that will load the Vue.js JavaScript library and one
that will load a file called app.js. This is radically different than using
server-side rendering because the server is now only responsible for loading the
bare minus of the website. The main boilerplate. Everything else is handled by a
client-side JavaScript library, in this case, Vue.js, and custom JavaScript
code. If you were to make a request to the URL with only the code above, you
would get a blank screen. There is nothing to load since the actual content
needs to be rendered using JavaScript.

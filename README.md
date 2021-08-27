# Learn-next.js

This repo is used to learn more about next.js, Jest and tailwind css.
## Key learnings
### General benefits of next

* integrated routing system
* static site generation (SSG) and server-side rendering (SSR)
* automatic code splitting
* fast refresh

### Navigation between pages

* all pages are inside paged directory
* for naviagtion Link component from 'next/link' is used
    * wrap a tag with the Link component
    * put href to Link component
* Link component enables client-side navigation
    * page transition happens with JS => faster than default browser navigation
* next only loads the JS code which is requiered for the current page
* pages are prefetched automatically
* for links to external pages use a tag only
* classNames should be added to a tag directly, not to the Link tag

### Assets, Metadata, and CSS

* next has build in support for CSS ans Sass
* static assets are stored in the public directory
* use Image component from 'next/image'
* next has automatic image optimazation build in
* images are optimized on-demand not at build time => that ensures short build times
* images are lazy-loaded by default
* import Head component from 'next/head' for adding metadata
* next has build in support for scss
* support css modules
    * css modules automatically genereat unique class names
    * developers do not need to worry about class name collisions
    * css modules = scoped css
* global styles can be added in the file 'pages/_app.js'
    * this is the only place where global styles can be imported
    * It's not possible to import global css anywhere else

### Pre-rendering and Data Fetching

* by default next pre-renders every page
    * html for each page is generated in advance
    * this results in better SEO
* generated html also contains the minimum JS code to run the page
    * after pageload => JS is executed to make the page fully interative (**hydration**)
* Next vs plain React
    * next:
        * onpageload pre-rendered html is displayed
        * hydration takes place and components get initialized
        * app becomes interactive after that process
    * react:
        * onpageload app is not rendered
        * after hydration app is visible and becomes interactive
* next has two forms of pre-rendering: **Static Generation** and **Server-side Rendering**
    * the difference is **when** the html is generated
* Static Generation
    * html is generated at build-time
    * reused for each request
    * next supports static generation with data
    * for this use the async function 'getStaticProps'
    * getStaticProps runs at build time and inside the function you can fetch external data
    * getStaticProps functions runs on server-side
    * Static generation should be used whenever possible
* Server-side Rendering
    * html is generated on each request
    * if you cannot pre-render the page ahead of a users's request go with SSR
    * use 'getServerSideProps' instead of 'getStaticProps'
    * TTFB will be slower than getStaticProps
    * request specific params are indie context parameter
    * async function getServerSideProps(context)...
* Client-side Rendering
    * static generated parts of pages with external data loaded via JS on client-side
    * used e.g. for user dashboard pages, user-specific pages where SEO is not relevant
    * for fetching data on the client side use the SWR hook

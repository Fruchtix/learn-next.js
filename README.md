# learn-next.js

This repo is used to learn more about next.js, Jest and tailwind css.
## key learnings
### general benefits of next

* integrated routing system
* static site generation (SSG) and server-side rendering (SSR)
* automatic code splitting
* fast refresh

### navigation between pages

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
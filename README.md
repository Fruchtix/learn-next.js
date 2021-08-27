# learn-next.js

This repo is used to learn more about next.js, Jest and tailwind css.
## key learnings
### general benefits of next

* integrated routing system
* static site generation (SSG) and server-side rendering (SSR)
* automatic code splitting
* Fast refresh

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
#### Developing locally

This thing is barebones as it comes! Even so, you can't just open `index.html` in your browser

If you set up `/png-border-trimmer/index.html` and `/png-border-trimmer/jzip.min.js`
and you open the HTML file in the browser, the JS might not actually load!

Let's say you import the JS in the HTML like this:

`<script src="./jzip.min.js"></script>`

The browser is operating from a temp system path so it will hit something like this to try
and access the JS file: `file:///run/user/1000/doc/a5b4eb77/jzip.min.js`
Instead of trying to access `<yourDirectory>/png-border-trimmer/jzip.min.js`

The way to solve this is to run a webserver from that directory with `npx http-server`
or something, and view it in the browser that way.

#### Deploying

- Just throw the files on a VPS and point to the `index.html` in your webserver config!
- I'm using Nginx and Certbot on OVH Cloud.

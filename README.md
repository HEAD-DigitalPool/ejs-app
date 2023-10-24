# Boilerplate: App using EJS

### What is this?

This is a boilerplate to keep you started with running EJS (or: [Embedded JavaScript templating](https://ejs.co/)) on your computer. EJS is helpful when creating web-apps, web-servers and websites using Node.js and JavaScript.

In order to run it on your computer, you can clone this repository (after having forked it, if you want to store your progress on Github):

```sh
$ git clone https://github.com/HEAD-DigitalPool/ejs-app.git # or clone your own fork before
$ cd ejs-app
$ npm install
$ npm start
```

Your app should now be running on [localhost:5001](http://localhost:5000/).

### How does the code work?

You have two types of files: server and client files.

The server file is the `index.js` file, the client files are located in the:

```sh
views
	pages
```

 The server file is composed as the following:

```javascript
const express = require('express')
const path = require('path')

const PORT = process.env.PORT || 5001

express()
  .use(express.static(path.join(__dirname, 'public')))
  .set('views', path.join(__dirname, 'views'))
  .set('view engine', 'ejs')
  .get('/', (req, res) => res.render('pages/index'))
	// here, the template index.ejs is read when accessed "/" 
  .get('/about', (req, res) => res.render('pages/about'))
	// here, the template about.ejs is read when accessed "/about" 
	// To create new 'pages', just follow the same logic
  .listen(PORT, () => console.log(`Listening on ${ PORT }`))

```

 The client files are composed as the following:

### Deploying to Heroku

Using resources for this example app counts towards your usage. [Delete your app](https://devcenter.heroku.com/articles/heroku-cli-commands#heroku-apps-destroy) and [database](https://devcenter.heroku.com/articles/heroku-postgresql#removing-the-add-on) as soon as you are done experimenting to control costs.

By default, apps use Eco dynos if you are subscribed to Eco. Otherwise, it defaults to Basic dynos. The Eco dynos plan is shared across all Eco dynos in your account and is recommended if you plan on deploying many small apps to Heroku. Learn more about our low-cost plans [here](https://blog.heroku.com/new-low-cost-plans).

Eligible students can apply for platform credits through our new [Heroku for GitHub Students program](https://blog.heroku.com/github-student-developer-program).

```
$ heroku create
$ git push heroku main
$ heroku open
```
or

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

### Documentation

For more information about using Node.js on Heroku, see these Dev Center articles:

- [Getting Started on Heroku with Node.js](https://devcenter.heroku.com/articles/getting-started-with-nodejs)
- [Heroku Node.js Support](https://devcenter.heroku.com/articles/nodejs-support)
- [Node.js on Heroku](https://devcenter.heroku.com/categories/nodejs)
- [Best Practices for Node.js Development](https://devcenter.heroku.com/articles/node-best-practices)
- [Using WebSockets on Heroku with Node.js](https://devcenter.heroku.com/articles/node-websockets)

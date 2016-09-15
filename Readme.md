
# :crocodile: CrocodileJS

[![Slack Status][slack-image]][slack-url]
[![MIT License][license-image]][license-url]
[![Stability][stability-image]][stability-url]
[![Build Status][build-image]][build-url]
[![Coverage Status][codecov-image]][codecov-url]
[![Standard JS Style][standard-image]][standard-url]

> CrocodileJS is a Node MVC framework that lets you chew apart JavaScript.

![Crocodile Dependencies][crocodile-dependencies]

<!-- TODO: DEMO GOES HERE -->

> **Tip:** Click the crocodile :crocodile: emoji in section headers to jump back to this index.

## <a href="#crocodile-index">:crocodile:</a> [Index](#crocodile-index)
* [What is CrocodileJS?](#crocodile-what-is-crocodilejs)
  - [Features](#features)
  - [Framework Comparison](#framework-comparison)
  - [Thoughts](#thoughts)
  - [Showcase](#showcase)
  - [App Structure](#app-structure)
  - [Back-end with Koa + Async/Await](#back-end-with-koa-async--await)
  - [Front-end with jQuery + Bootstrap](#front-end-with-jquery--bootstrap)
  - [Job Scheduler](#job-scheduler)
  - [Database &amp; ORM](#database--orm)
  - [Sessions &amp; Auth](#sessions--auth)
  - [Flash Messaging](#flash-messaging)
  - [API Example](#api-example)
  - [Security](#security)
  - [Helpers](#helpers)
* [Why should I use it?](#crocodile-why-should-i-use-it)
  - [Best Practices](#best-practices)
  - [Latest Standards](#latest-standards)
  - [LiveReload Built-in](#livereload-built-in)
  - [Production Ready](#production-ready)
  - [Cross-browser Compatibility](#cross-browser-compatibility)
  - [Built-in User Group Permissioning](#built-in-user-group-permissioning)
  - [Search Engine Indexing](#search-engine-indexing)
  - [i18n Internationalization and l10n Localization)(#i18n-internationalization-and-l10n-localization)
  - [Performance](#performance)
* [How do I use it?](#crocodile-how-do-i-use-it)
  - [Requirements](#requirements)
  - [Installation](#installation)
  - [Configuration](#configuration)
    * [How does configuration work?](#how-does-configuration-work)
    * [How do I configure my app?](#how-do-i-configure-my-app)
      - [Basic Configuration](#basic-configuration)
      - [Authentication Providers](#authentication-providers)
        * [Facebook Auth](#facebook-auth)
        * [Twitter Auth](#twitter-auth)
        * [Google Auth](#google-auth)
        * [GitHub Auth](#github-auth)
        * [LinkedIn Auth](#linkedin-auth)
        * [Instagram Auth](#instagram-auth)
        * [Stripe Auth](#stripe-auth)
      - [Amazon S3 and CloudFront Asset Setup](#amazon-s3-and-cloudfront-asset-setup)
      - [Logging Configuration](#logging-configuration)
      - [Code Coverage Configuration](#code-coverage-configuration)
      - [Favicon and Touch Icon Configuration](#favicon-and-touch-icon-configuration)
  - [Development](#development)
  - [Deployment](#deployment)
  - [Advice](#advice)
  - [Tools](#tools)
* [Is there a book on CrocodileJS?](#crocodile-is-there-a-book-on-crocodilejs)
* [Can I get help?](#crocodile-can-i-get-help)
* [How do I get updates?](#crocodile-how-do-i-get-updates)
* [Who built it?](#crocodile-who-built-it)
* [Can we hire @niftylettuce?](#crocodile-can-we-hire-niftylettuce)
* [License](#crocodile-license)


## <a href="#crocodile-index">:crocodile:</a> [What is CrocodileJS?](#what-is-crocodilejs)

CrocodileJS is an application ~~framework~~ boilerplate for rapid iteration of a minimal viable product.  It is built with ES6, ES7, Babel, and Koa, and has dozens of other extremely useful packages built-in.  It is production-ready and used by several startups.

### Features

* Built for Startups, Bootstrappers, and Enterprises
* Includes an API Server, Web Server, and Job Scheduler
* GitHub Emojis Supported! :smile: :crocodile: :sparkles:
* ECMAScript 7+ Features
* Async/await ~~callback hell~~
* Koa@2.x (latest version of Koa)
* Localization Supported with i18n
* Basic Email Signup and Password Reset
* API BasicAuth Access Built-in
* 9+ Authentication Providers Supported (e.g. Google/Facebook)
* Beautiful Email Templates and Translation Support
* Extremely Secure and Well-tested
* Ready for Production and Highly Configurable
* Zero Guesswork; it uses 80+ NPM packages already hooked together

### Framework Comparison

Instead of sharing a table with irrelevant benchmarks and checklists of features that only Crocodile has, we provide a simple summary of the most comparable, popular frameworks that come to mind:

* [Hackathon Starter][hackathon-starter] doesn't do anything for your production-ready assets and it still uses ECMAScript 5.  As a "hackathon starter", it leads you to write spaghetti code for a quick hackathon &ndash; which leads you [to writing huge files][hackathon-app-file] that could be componentized.  It also doesn't use Koa.
* [Sails][sailsjs] was built in a way that is extremely confusing, as such (and not to be rude) but @niftylettuce [won the first official SailsJS hackathon][won-hackathon] and never used SailsJS again since that one time.  It locks you into their philosophy with little wiggle room due to the convoluted setup.  It also uses an [outdated version of Express][outdated-express] with no plans to upgrade.  It also doesn't use Koa.
* [Hapi.js][hapijs] simply doesn't do enough for you.  Input validation and other menial features don't allow you to ship a high-quality MVP.  It also doesn't use Koa.
* [Total.js][totaljs] was written from scratch and [is against the Node philosophy][node-philosophy]... just ([look at this file][totaljs-example]).  It also doesn't use Koa.
* ... quite really every single framework and boilerplate out there is half-baked and really not great for building stellar MVP's

There really aren't many decent Node frameworks, so only the above made the list.  GitHub is full of [pure web app boilerplates][gh-boilerplate], but they really don't do much for you.

### Thoughts

Crocodile was designed to prove the viability of an idea as quick as possible,
with sheer simplicity, and an extremely ambitious quality level.  It uses the [latest standards](#latest-standards),
[best practices](#best-practices), and is [production ready](#production-ready).

For example, Crocodile can be used to release prototypes of the following in less than 30 days:

* Enterprise Node.js Web Application for Online Ticket Booking
* Functional Web App for Online Food Ordering
* RESTful API for a React Native iOS/Android App
* HR Platform for Payroll, Billing, and Employee Benefits

> **As you can see, quite literally any type of Software-as-a-Service business can be built with CrocodileJS!  Of course, you can build something more complex or simpler than these examples with CrocodileJS.**

Crocodile is more of a "boilerplate" than a "framework".  It's often called a framework
because of keyword search popularity and the confusion between the two words.
It has a very minimal codebase, which was written with ES6/ES7 (yes, it uses
the new [Async/Await][async-await] syntax!) &ndash; and it was structured with an MVC approach (in other words it has three folders to separate your logic `src/app/models` ("M" for models), `src/app/controllers` ("C" for controllers), and `src/app/views` ("V" for views).

![SPA Framework][spa-image]

**Crocodile does not come with a single page app framework out of the box**, and does not use any special
client-side framework by default (other than jQuery, which isn't really a SPA framework) &ndash; though it can easily be changed, and you could include React, Choo, Angular, VueJS, or whatever you'd like).
The reason it does not use a SPA library, such as [React][react] or [Angular][angular],
is because most (probably?) of software as a service start-ups (and API's in general) don't need something this fancy to start (API's don't even need a SPA).
Using SPA frameworks _will_ and _have_ made proving the viability of an idea take even longer than it already should.
Instead, **Crocodile uses the extremely powerful and fast rendering template language called [Nunjucks][nunjucks]**.
In order to render it with Koa, we use [koa-nunjucks-promise][koa-nunjucks-promise].

[![Fake Grimlock][avc-chicken-image]][fake-grimlock]

Before diving into the structure and how it works, it is important to share
that Crocodile is _highly opinionated_ and **may not be for you**.  If you are not
comfortable or do not agree with the ideas shared in these articles, then perhaps
you should not read any further into Crocodile, and close this browser tab.

1. [Rapid MVP Standards][rapid-mvp] by [@niftylettuce][nifty-twitter]
2. [Frameworks don't make much sense][frameworks-dont-make-sense] by [@pkrumins][pkrumins]
3. [Do Things that Don't Scale][dont-scale] by [@paulg][pg-twitter]

### Showcase

> Did you ship a project with Crocodile?  [File an issue](/issues) and we'll include it!.

### App Structure

Crocodile is loosely-based on MVC design, and it has the following structure (`tree` output below):

<!-- generate output for every release using `tree -I "build|lib|node_modules|media|coverage"` -->

```log

```

### Back-end with Koa + Async/Await

We use Koa for the back-end, and if you previously used [Express][express], you might want to understand the differences; [see this article][koa-vs-express].

To rid of [callback hell][callback-hell], we use a new JavaScript language feature called Async/Await.

For example, here are two blocks of code that compare before and after...

> This is how one might write a Mongoose save with callbacks:

```js
// find the user that belongs to the @crocodilejs organization
// and make their user group have "admin" status
function updateUser(req, res, next) {
  Users.findOne({ org: 'crocodilejs' }, function(err, user) {
    if (err) return next(err);
    if (!user) return next(new Error('User does not exist'));
    user.group = 'admin';
    user.save(function(err, user) {
      if (err) return next(err);
      res.json(user);
    });
  });
}
```

> This is how one might write a Mongoose save with Async/Await:

```js
// find the user that belongs to the @crocodilejs organization
// and make their user group have "admin" status
static async updateUser(ctx) {
  let user = await User.findOne({ org: 'crocodilejs' });
  if (!user) return ctx.throw(Boom.badRequest('User does not exist'));
  user.group = 'admin';
  ctx.body = await user.save();
}
```

> Crocodile has custom built-in error handling &ndash; so actually you don't even need to wrap the Async/Await function with a `try {} catch (e) {}` statement &ndash; but be careful, because in other cases you might want to (e.g. when you don't want to show a specific error from a third-party API response)!

Other scenarios where Async/Await is resourceful:

* Populating database references cleanly
* Complex find, search, or querying in general
* Less indentation = more readable code
* No more callbacks = more readable code
* Less indentation = code wrapping to 80 or 100 (recommended) characters is easy

### Front-end with jQuery + Bootstrap

By default, the [latest Bootstrap version 4 alpha][bootstrap-4-alpha] is used (it uses SCSS for its CSS pre-processor).

However, you can swap out Bootstrap to another version, or entirely for something else.  You can also switch SCSS to use LESS or plain CSS.

Also included are the front-end packages jQuery and [Sweetalert2][sweetalert2].

**You don't need Bower anymore**, since you can simply import libraries through our Browserify setup!

### Job Scheduler

Job scheduling is built on top of [Agenda][agenda].  See the `src/agenda.js` file and also `src/jobs` folder for how it works and is set up.

There is one sample job scheduler built-in, which is in the `post('save')` hook for when a user is created.  The user gets a welcome email after they are created in the DB.

You can see the content and template of the email in the `src/emails/welcome` folder.  Emails are sent using [Postmark][postmarkapp] and the package [email-templates][email-templates].

However in development mode, emails are not sent using an outbound service such as Postmark App &ndash; instead they are rendered to the OS temporary directory and opened in the browser automatically for you (saving you time and preventing you from clicking "Refresh" in Gmail a dozen times, haha!).

### Database &amp; ORM

[MongoDB][mongodb] and [Mongoose][mongoose] are built in, but you can swap them out with your preferred database and ORM glue.  If you need help setting up [Postgres][pg] and [Bookshelf][bookshelf], then we suggest you to change your mind!  It will slow you down &ndash; but if you insist, we can put you in the right direction.

To ~~better~~ beautify validation error messages we use [mongoose-beautiful-unique-validation][mongoose-beautiful-unique-validation]

To enhance security and allow you to have selective JSON output from query results (e.g. never return a user's `refresh_token`, `access_token`, `hash`, or `password` fields) we use [mongoose-json-select][mongoose-json-select].

> We automatically strip the default provided tokens/hash/password fields from JSON output, don't worry!  See the default user model in `app/models/user.js` for insight.

### Sessions &amp; Auth

[Redis][redis] and [Passport][passport] are used for session storage and authentication.

Out of the box, we provide quite a few authentication methods (but only basic email/password and API token access is enabled by default &ndash; see [Authentication Providers](#authentication-providers) for more info).

Type | Description
---- | -----------
Basic | users sign up with an email address and password
API Token | an `api_token` field is populated for each user in the database after their first log-in, and this can be passed as the `user` in `user:pass` with BasicAuth headers &ndash; password is blank for simplicity).  This is very useful for API access if you are building an iOS/Android or client-side focused app.  See the [API Example](#api-example) below for more information on this and how to test it out.
Facebook | uses [passport-facebook][passport-facebook] (your users can "Log in with Facebook")
Twitter | uses [passport-twitter][passport-twitter] (your users can "Log in with Twitter")
Google | uses [passport-google-oauth][passport-google-oauth] (your users can "Log in with Google")
GitHub | uses [passport-github][passport-github] (your users can "Log in with GitHub")
LinkedIn | uses [passport-linkedin][passport-linkedin] (your users can "Log in with LinkedIn")
Instagram | uses [passport-instagram][passport-instagram] (your users can "Log in with Instagram")
Stripe | uses [passport-stripe][passport-stripe] (your users can "Log in with Stripe")

> If you need to add additional strategies, you can literally clone the Google Strategy code and use another [passport package][passport-package] for your auth provider.  Don't be afraid to [join our Slack channel][slack-url] and ask us for help!

### Flash Messaging

<img width="800" height="406" style="width:800px;height:406px;" alt="Flash Messaging" src="https://cdn.rawgit.com/crocodilejs/crocodile-node-mvc-framework/master/media/sweetalert2-screenshot.png" />

Through the use of [Sweetalert2][sweetalert2] and [koa-connect-flash][koa-connect-flash], we allow you to display to users extremely beautiful alerts.

```js
ctx.flash(level, message);
```

Combine this with [our support for international localization/translation](#i18n-internationalization-and-l10n-localization) and you get localized alerts!

The `level` parameter can be one of the following (adhering to Sweetalert2 defaults):

* `success` - Success/OK messages

  ```js
  ctx.flash('success', 'Everything worked OK');
  ```

* `info` - Informational messages

  ```js
  ctx.flash('info', 'You will never achieve greatness unless you believe in such greatness');
  ```

* `warning` - Warning messages

  ```js
  ctx.flash('warning', "Don't forget to tie your shoes before you walk forward");
  ```

* `error` - Error messages

  ```js
  ctx.flash('error', 'If you fail, then retry, and retry, and retry, until you succeed.');
  ```

* `question` - Question messages

  ```js
  ctx.flash('question', 'Who are you?');
  ```

### API Example

Using the user's `api_token` field value (which is automatically generated upon user creation, see `src/app/models/user.js`), you can pass the test of the policy `Policies.ensureApiToken`.

For example, we have one restricted route built into Crocodile, which is `GET /v1/users`.

As a test, try to sign in at <http://localhost:3000> after you've start up the web server and API server.

Go to your account page at <http://localhost:3000/my-account> and copy your API token to your clipboard.

Take this value, and run the following `curl` command using it (replace with your API token where it says `api_token` below:

```bash
curl -u "api_token:" http://localhost:3000/v1/users
```

This should output a JSON response like the following:

```json
{
  "id": "578ee8af0d1f58b77a4f9ad7",
  "updated_at": "2016-07-20T02:57:51.099Z",
  "created_at": "2016-07-20T02:57:51.000Z",
  "object": "user",
  "display_name": "Nick Baugh",
  "given_name": "Nick",
  "family_name": "Baugh",
  "google_profile_id": "105518868040745239689",
  "avatar_url": "https://lh3.googleusercontent.com/-XdUIqdMkCWA/AAAAAAAAAAI/AAAAAAAAAAA/4252rscbv5M/photo.jpg"
}
```

### Security

With respect to security, we support the following out of the box:

* [koa-helmet][koa-helmet] - defaults are used, including:
  - [dnsPrefetchControl][dns-prefetch] controls browser DNS prefetching
  - [frameguard][frameguard] to prevent clickjacking
  - [hidePoweredBy][poweredby] to remove the X-Powered-By header
  - [hsts][hsts] for HTTP Strict Transport Security
  - [ieNoOpen][ienoopen] sets X-Download-Options for IE8+
  - [noSniff][nosniff] to keep clients from sniffing the MIME type
  - [xssFilter][xssfilter] adds some small XSS protections
* [koa-ratelimit][koa-ratelimit] - prevent bots and hackers from infinitely brute-forcing routes

### Helpers

Crocodile uses the following helper libraries:

* [boom][boom] - HTTP-friendly error objects
* [chalk][chalk] - colorful output
* [chalkline][chalkline] - easily debug with a huge chalkline in your terminal
* [dotenv][dotenv] - management of dotfiles (your environment configurations)
* [frisbee][frisbee] - an API wrapper for WHATWG's fetch method (similar to [request][request]!)
* [koa-convert][koa-convert] - easily convert generator middleware functions to Async/Await
* [lodash][lodash] - the utility library
* [moment][moment] - date and time formatting and manipulation
* [underscore.string][underscore-string] - string manipulation
* [validator][validator] - string validation and sanitization


## <a href="#crocodile-index">:crocodile:</a> [Why should I use it?](#crocodile-why-should-i-use-it)

### Best Practices

* Zero-downtime, graceful reloading with automated continuous integration (see [deployment](#deployment))
* Automated test runner and code coverage setup using:
  - [chai][chai]
  - [check-chai][check-chai]
  - [dirty-chai][dirty-chai]
  - [istanbul][istanbul]
  - [jsdom][jsdom]
  - [mocha][mocha]
* Simple message alert system with [koa-connect-flash][koa-connect-flash] and [Sweetalert2][sweetalert2]
* API token without a password for an extremely simple approach to session-less, BasicAuth access
* [Stripe-inspired][stripe-inspired] API design with versioning, error handling, type description, and verbose list output with count and number of pages
* [No callback hell][callback-hell] since you can use Async/Await syntax

### Latest Standards

* Latest stable version of Node (`v6.x.x`)
* Streams for build process with Gulp
* Newest version of MongoDB and Redis (e.g. you can use [$lookup][lookup-operator] operator with MongoDB now!)
* Uses ES6/ES7 syntax (no more callbacks; you can use `await` and `async` finally!)
* Latest version of Koa `v2.x` (or commonly referred to as `@next`)

### LiveReload Built-in

Through [koa-livereload][koa-livereload] and [gulp-livereload][gulp-livereload] your assets automatically reload as you continually change and save them.

This means you can have your editor open and a browser tab opened to your app at <http://localhost:3000/> &ndash; of course you need to be running the app with `npm run livereload` (which runs `gulp watch`) &ndash; and your changes appear in real-time!  Yes, we know this is not new technology, but not many other frameworks had this built-in (at least the right way with gulp).

For example, if you make the following change to your stylesheet file and save it...

```diff
body {
-  background-color: red;
+  background-color: hotpink;
}
```

... then your background color on the browser tab will instantly change to hot pink.

### Production Ready

Crocodile comes with a robust and well-tested Gulpfile (written with Babel!), check [it out here][gulpfile].  This file will let you build a version of your project that is ready for production.

What's a Gulpfile?  You can [read about Gulp here][gulp] &ndash; but it's basically a file that has a series of build tasks defined (e.g. it's very similar to a `Makefile` or [Grunt][grunt] if you're familiar with that).

In a production environment, your app's assets will be minified, compressed, gzipped,
revision hashed, and uploaded to Amazon S3 and CloudFront for load balancing.  To do this, we use
the packages [koa-manifest-rev][koa-manifest-rev] and [gulp-rev][gulp-rev], with plugins that include:

* [babelify][babelify] - convert ES6/ES7 code to ES5
* [browserify][browserify] - you can `import` (or `require`) modules in the browser!  You no longer need to use Bower.  We looked at using Webpack when we had worked on React Native stuff, but it was too complicated and we ran into way too many problems.
* [eslint][eslint] - lints your JavaScript according to the `.eslintrc` configuration.  Feel free to swap out our `.eslintrc` for something like [eslint-config-airbnb][eslint-config-airbnb].
* [gulp-awspublish][gulp-awspublish] - publishes to AWS your assets
* [gulp-cloudfront][gulp-cloudfront] - publishes to CloudFront your assets
* [gulp-eslint][gulp-eslint] - lints your JavaScript in the build runner
* [gulp-imagemin][gulp-imagemin] - compresses your images
* [gulp-postcss][gulp-postcss] - processes your CSS
* [gulp-sourcemaps][gulp-sourcemaps] - adds sourcemaps to your code for easy debugging
* [gulp-uglify][gulp-uglify] - uglifies and minifies your JavaScript code
* [imagemin-pngquant][imagemin-pngquant] - plugin for imagemin to compress PNG's

This is the de-facto standard for hosting images, fonts, scripts, and assets in general
&ndash; and it is managed properly in Crocodile using asset revisioning.  For example, your file
named `crocodile-logo.png` will become `crocodile-logo-0775041dd4.png` in production (you don't have to worry about cache busting!).

Not only that, but your files will be linted and they come with sourcemaps too!

> To compile all the assets and source code for production:

```bash
NODE_ENV=production npm run compile
```

> To publish to Amazon S3/CloudFront all of the assets:

```bash
NODE_ENV=production npm run publish-assets
```

After running these two sets of commands, you can test things out locally by running the processes (simulate production on your own machine):

> Web:

```bash
NODE_ENV=production npm run app
```

> API:

```bash
NODE_ENV=production npm run api
```

> Job Scheduler:

```bash
NODE_ENV=production npm run agenda
```

> **NOTE**: The above commands are what you'd use in a deployment configuration.

### Cross-browser Compatibility

<img width="100" height="100" style="width:100px;height:100px;" alt="Chrome" src="https://rawgit.com/alrra/browser-logos/master/chrome/chrome.svg" />
<img width="100" height="100" style="width:100px;height:100px;" alt="Android" src="https://rawgit.com/alrra/browser-logos/master/firefox/firefox.svg" />
<img width="100" height="100" style="width:100px;height:100px;" alt="Safari" src="https://raw.githubusercontent.com/alrra/browser-logos/master/safari/safari.png" />
<img width="100" height="100" style="width:100px;height:100px;" alt="Internet Explorer" src="https://rawgit.com/alrra/browser-logos/master/internet-explorer-tile/internet-explorer-tile.svg" />
<img width="100" height="100" style="width:100px;height:100px;" alt="Opera" src="https://raw.githubusercontent.com/alrra/browser-logos/master/opera/opera.png" />
<img width="100" height="100" style="width:100px;height:100px;" alt="Android" src="https://raw.githubusercontent.com/alrra/browser-logos/master/android/android.png" />

Is this cross-browser compatible?  Yes, 100%!  What about all of your ES6/ES7 code?  Yes, 100%.

**However, if you stick with the default v4 Bootstrap CSS framework &ndash; it only supports IE9+ and iOS 7+.**

All of your code is converted to browser-friendly ES5 vanilla JavaScript (using [Browserify][browserify] and [Babelify][babelify])...so it's cross-browser compatible!

> This means both your server-side and client-side code is built to the `./lib/` folder with ES5 syntax when the Gulpfile is run with `gulp build`.
You never have to worry about passing some `--harmony` flag either to run your app.
**The idea here is that you can focus on writing clean, short bits of code &ndash; and never have to worry about how it runs**.

### Built-in User Group Permissioning

By default, all users are assigned to the "user" group.  This group is defined in the user model under `app/models/user.js` per the property `'group'``.

This approach was inspired by classic Linux-based user-group permissioning.

We've also added a default policy helper to detect whether or not a user an admin, which you can add as a middleware before your controller logic.

For example, if you want to restrict access to all `/admin` routes, you can add this simple middleware:

```js
router.all('/admin*', policies.ensureAdmin);
```

**This simple middleware is automatically added by default for you.**

If you'd like to grant yourself admin access to the `/admin` routes, then you can run this script (replace with your email address and database name):

```bash
mongo crocodile_development --eval 'printjson(db.users.update({ email: "niftylettuce@gmail.com" }, { $set: { group: "admin" }}));'
```

### Search Engine Indexing

Since we don't use a SPA, you don't have to worry about rendering SEO-friendly content!  What you see in the browser is what the search engine crawler sees.

We didn't build in structured open graph tags as a default to edit, since we figure you can customize to your own needs.

With this setup, we have climbed to #1 on Google for various keywords, easily.  Of course, you need great content and traffic.

In order to prevent duplicate content, we have added a plugin that removes trailing slashes from URL's, so `/home/` will `301` redirect to `/home` automatically.

### i18n Internationalization and l10n Localization

We built-in international localization/translation support!

See the following files for an understanding of how it works:

* `src/locales` folder (full of all the translations, if a locale is missing, it defaults to English; `en.json`)
* `src/config/locales.js` file (uncommented languages are the ones supported)
* `src/config/index.js` (see the `config.i18n.HELLO_WORLD` variable as an example &ndash; you can use the `config.i18n` object for error messages, success messages, page titles, page descriptions, and more)

If you want recommendations on services to use for this and how to integrate, then [join our Slack][slack-url] and ask us!

To translate a message, you simply use the context helper method `ctx.translate('SOME_CONFIG_KEY_MESSAGE')`.  If you need interpolation, you can pass them as such `ctx.translate('SOME_MESSAGE', 'Foo', 'Bar', 'Baz')` whereas `config.i18n.SOME_MESSAGE = 'Hello %s %s %s'` (outputs `Hello Foo Bar Baz`).

Translations of message keys in `config.i18n` are found in `locales/`.  If you wanted to translate `SOME_CONFIG_KEY_MESSAGE` in Spanish, then edit the property for the key of `"Hello %s %s %s"` in `locales/es.json`.

### Performance

For performance, you should always use the `lean()` method while writing your Mongoose queries (here's [an example article][lean-method] showing why).

You should also **never use Mongoose hooks, virtuals, or the populate method**.  Instead you should write static functions in the models, such as `User.doSomething(user, fn)`.  For insight as to how to write static methods, [see the Mongoose docs here][mongoose-static-method].

If you need to asynchronously populate or waterfall chain population of database references, we suggest to use the [$lookup operator][lookup-operator] or use Async/Await syntax to keep it clean.
For an example of how to write a `populate()` method with $lookup, [see this GitHub issue][gh-mongoose-issue].

We've also included these libraries to help with performance:

* [koa-compress][koa-compress] - compress responses with zlib
* [koa-conditional-get][koa-conditional-get] - allows conditional GET response (returns a `304` "Not Modified" header if condition matches)
* [koa-etag][koa-etag] - reduce bandwidth consumption with e-tags on responses
* [koa-response-time][koa-response-time] - adds a new response header called `X-Response-Time` with the number of milliseconds the server took to respond

Other than that, you just need to increase your server storage/bandwidth/memory/swap, add load balancing, and/or use PM2's clustering mode &ndash; and you _should_ be able to support thousands of users.  Horizontal scaling!

Check out the [deployment](#deployment) section below for how a production environment and deployment process should be configured.


## <a href="#crocodile-index">:crocodile:</a> [How do I use it?](#how-do-i-use-it)

### Requirements

**<u>You'll need to have the following installed</u>** on your operating system (we provide instructions below):

* [Node][node] `>= v6.x` (we recommend using [NVM][nvm] to manage your Node versions)
* [MongoDB][mongodb] `>= v3.x`
* [Redis][redis] `>= v3.x`

We also recommend that you install **our preferred [tools](#tools)** as well!

### Mac OS X

1. Install [Brew][brew]:

  ```bash
  /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```

2. Install [NVM][nvm]:

  ```bash
  curl -o- https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
  source ~/.bashrc
  ```

3. Install [Node][node] with NVM:

  ```bash
  nvm install stable
  nvm alias default stable
  ```

4. Install [MongoDB][mongodb] (and make sure you read the line about `launchctl` after you hit `ENTER`):

  ```bash
  brew install mongo
  ```

5. Install [Redis][redis] (and make sure you read the line about `launchctl` after you hit `ENTER`):

  ```bash
  brew install redis
  ```

### Ubuntu

1. Install [NVM][nvm]:

  ```bash
  curl -o- https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
  source ~/.bashrc
  ```

2. Install [Node][node] with NVM:

  ```bash
  nvm install stable
  nvm alias default stable
  ```

3. Install [MongoDB][mongodb]:

  ```bash
  sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
  echo "deb http://repo.mongodb.org/apt/ubuntu "$(lsb_release -sc)"/mongodb-org/3.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.0.list
  sudo apt-get update
  sudo apt-get install -y mongodb-org
  service mongod status
  ```

4. Install [Redis][redis]:

  ```bash
  sudo add-apt-repository ppa:chris-lea/redis-server
  sudo apt-get update
  sudo apt-get install redis-server
  redis-benchmark -q -n 1000 -c 10 -P 5
  source ~/.profile
  ```

### Windows

We do not support Windows, so please use [VirtualBox][virtualbox] or [Vagrant][vagrant] instead with [Ubuntu][ubuntu] or [Linux Mint][linux-mint].

### Installation

We crafted a simple command-line utility for creating new projects using Crocodile.

Simply install it, then run one of the available commands.

```bash
npm install -g crocodile
```

```bash
crocodile


          `.-::::-.`
      `-+ooooooooooo+/`
     :osso++//+ssooooos:.
    +s/.     -sssoo+ooosso-
   :o`      :yso++++o+ooyso
   /`      `:yo+++++ooosyys-
         -/++oo+++oooosy/...
     ./osss+++oo+oossosso/
     ``/oo+ssoosoossossss/
     ./+++ooossysso:.soo
    :ooooo/:-:--.    +oo-
    `--.             `.`


🐊  CrocodileJS is a Node MVC framework that lets you chew apart JavaScript - https://crocodilejs.com


  Usage:  [options] [command]


  Commands:

    chew <dir>  Create a new CrocodileJS project
    upgrade     Upgrade your existing CrocodileJS project
    issues      Open GitHub issues for CrocodileJS
    docs        Read CrocodileJS documentation on GitHub
    rock        I wonder what this does?

  Options:

    -h, --help     output usage information
    -V, --version  output the version number
```

After you run `crocodile chew <dir>` for the first time, you will need to follow these steps to get started:

1. Change directories to your newly created project directory:

  ```bash
  cd <dir>
  ```

2. Install NPM dependencies:

  ```bash
  npm install
  ```

3. Start watching assets and scripts for changes (note that this also does the required initial build of the project to the `lib` folder &ndash; which has to happen in order for you to use Crocodile):

  > Assets (also starts [LiveReload](#livereload-built-in)):

  ```bash
  npm run watch-assets
  ```

  > Scripts:

  ```bash
  npm run watch-scripts
  ```

4. Start the processes (install `nodemon` with `npm install -g nodemon`):

  > Web:

  ```bash
  nodemon lib/web
  ```

  > API:

  ```bash
  nodemon lib/api
  ```

  > Jobs:

  ```bash
  nodemon lib/agenda
  ```

5. Go to <http://localhost:3000> in your browser.

> **NOTE:** In production you won't run these same commands, see [Production Ready](#production-ready) for more info.

### Configuration

#### How does configuration work?

We have made configuration of your CrocodileJS project easy through a [dotenv][dotenv] configuration, per the [Twelve-Factors][twelve-factors].

We use the following three packages to manage configuration:

* [dotenv-extended][dotenv-extended] - allows us to craft a `.env` definition (otherwise known as a "schema") in a file named `.env.schema`
* [dotenv-mustache][dotenv-mustache] - allows us to use the [Mustache templating language][mustache] in our `.env` and `.env.defaults` confguration files
* [dotenv-parse-variables][dotenv-parse-variables] - automatically parses variable types from `process.env` (e.g. `FOO=4` will set `process.env.FOO = 4` with a `Number` variable type instead of a `String`)

Configuration is managed by the following, in order of priority:

1. Contents of the file at `src/config/index.js` (reads in `process.env` environment variables)
2. Contents of the files in directories under `src/config/environments/` (sets defaults per environment, e.g. you can pass `NODE_ENV=staging` and it will load the file at `/src/config/environments/staging.js`)
3. Environment variables used to override defaults or set required ones (e.g. `NODE_ENV=production`)
4. Environment configuration in `.env`
5. Environment configuration in `.env.defaults`

Precedence is taken by the environment configuration files, environment variables, then the `.env` file.

Basically [dotenv][dotenv] won't set an environment variable if it already detects it was passed as an environment variable.

Take a look in the [src/config][src-config] folder contents and also at the default [.env.example][dot-env-file] file.

We've provided a default file called `.env.example`, **which you will need to rename** to `.env` and customize yourself.

#### How do I configure my app?

##### Basic Configuration

1. Copy the file `.env.defaults` to `.env` (this step is automatically done for you with the `crocodile chew` CLI command)
2. Edit the `.env` file and make it your own (e.g. replace the default email address and app name)

##### Authentication Providers

Authentication is managed by `src/config/index.js` and `src/helpers/passport.js`.

###### Facebook Auth

> TODO

###### Twitter Auth

> TODO

###### Google Auth

> In order to add Google Auth to your app (so users can log in with their Google account):

1. Go to <https://console.developers.google.com> &ndash; Create a project (and fill out your project information &ndash; if you need a 120x120px default image, [you can use this one][120x120])
2. Under your newly created project, go to Credentials &ndash; Create credentials &ndash; OAuth client ID &ndash; Web application
3. Set "Authorized JavaScript origins" to `http://yourdomain.com` (replace with your domain) and also `http://localhost:3000` (for local development)
4. Set "Authorized redirect URIs" to `http://yourdomain.com/auth/google/ok` (again, replace with your domain) and also `http://localhost:3000/auth/google/ok` (again, for local development)
5. Copy and paste the newly created key pair for respective properties in your `.env` file (example below)

  ```diff
  -GOOGLE_CLIENT_ID=
  +GOOGLE_CLIENT_ID=424623312719-73vn8vb4tmh8nht96q7vdbn3mc9pd63a.apps.googleusercontent.com
  -GOOGLE_CLIENT_SECRET=
  +GOOGLE_CLIENT_SECRET=Oys6WrHleTOksqXTbEY_yi07
  ```
6. In `src/config/index.js`, set `auth.providers.google = true` to enable this authentication method.

###### GitHub Auth

> TODO

###### LinkedIn Auth

> TODO

###### Instagram Auth

> TODO

###### Stripe Auth

> TODO

##### Amazon S3 and CloudFront Asset Setup

> In order for your assets to get properly served in a production environment, you'll need to configure AWS:

1. Go to <https://console.aws.amazon.com/iam/home#security_credential> &dash; Access Keys &ndash; Create New Access Key
2. Copy and paste the newly created key pair for respective properties in your `.env` file (example below)

  ```diff
  -AWS_IAM_KEY=
  +AWS_IAM_KEY=AKIAJMH22P6W674YFC7Q
  -AWS_IAM_SECRET=
  +AWS_IAM_SECRET=9MpR1FOXwPEtPlrlU5WbHjnz2KDcKWSUcB+C5CpS
  ```

3. Enable your API by clicking on Overview and then clicking the Enable button
4. Go to <https://console.aws.amazon.com/s3/home> &ndash; Create Bucket
5. Create a bucket and copy/paste its name for the property in `.env` (example below)

  ```diff
  -AWS_S3_BUCKET=
  +AWS_S3_BUCKET=crocodile-development
  ```

6. Go to <https://console.aws.amazon.com/cloudfront/home> &ndash; Create Distribution &ndash; Get Started
7. Set "Origin Domain Name" equal to your S3 bucket name (their autocomplete drop-down will help you find it)
8. Leave the remaining defaults as is (some fields might be blank, this is OK)
9. Copy/paste the newly created Distribution ID and Domain Name for respective properties in your `.env` file (example below)

  ```diff
  -AWS_CF_DI=
  +AWS_CF_DI=E2IBEULE9QOPVE
  -AWS_CF_DOMAIN=
  +AWS_CF_DOMAIN=d36aditw73gdrz.cloudfront.net
  ```

#### Outbound Email Configuration

> By default, in a development environment, we simply render the email in your browser.  However on non-development environments we send the outbound emails through Postmark App by default (though you can swap in your own `transport` provider):

1. Go to [https://postmarkapp.com](https://postmarkapp.com?utm_source=crocodilejs) &ndash; Start Free Trial
2. Create a free trial account, then click Get Started, and proceed to create a "Server" and "Sender Signature"
3. Copy/paste the "Server API token" under "Credentials" in your `.env` file (example below)

  ```diff
  -POSTMARK_API_TOKEN=
  +POSTMARK_API_TOKEN=ac6657eb-2732-4cfd-915b-912b1b10beb1
  ```

##### Logging Configuration

> We recommend to use [Sentry][sentry] for server-side and client-side logging, though you could swap in your own provider:

1. Go to <https://getsentry.com/> &ndash; Try for free
2. Create a free account, then proceed to create a "Project"
3. Under your project, on the left side under the "DATA" section, go to "Client Keys (DSN)", and copy the private (not public) key value for "DSN" to your clipboard.
4. Paste this value in your `.env` file (example below)

  ```diff
  -SENTRY_DSN=
  +SENTRY_DSN=https://fde13b9ab0104zz9a157a045826fb97b:fd9a23972636435eaf4bf9a414355d9a@app.getsentry.com/87713
  ```
5. Under your project, on the left side under the "DATA" section, go to "Client Keys (DSN)", and copy the public (not private) key value for "DSN" to your clipboard.
6. Paste this value in your `.env` file (example below)

  ```diff
  -RAVEN_DSN=
  +RAVEN_DSN=https://fde13b9ab0994zz9a157a045826fb52b@app.getsentry.com/87713
  ```

#### Code Coverage Configuration

> We recommend to use [CodeCov][codecov] for code coverage configuration, though you could swap in your own provider:

1. Go to <https://codecov.io/> &ndash; Sign up with GitHub
2. Click on your existing project, then proceed to settings where you can copy to your clipboard your Codecov token.
3. Paste this value in your `.env` file (example below)

  ```diff
  -CODECOV_TOKEN=
  +CODECOV_TOKEN=522d2za9-22z4-az8m-9190-215zef1qpnz1
  ```

#### Favicon and Touch Icon Configuration

You can customize the favicon and touch icons &ndash; just generate a new set at <https://realfavicongenerator.net> and overwrite the existing in the [src/assets/][src-assets] folder.  Just make sure that the paths match up in the `src/assets/browserconfig.xml` and `src/assets/manifest.json` files.

### Development

You should have Crocodile [installed](#installation) and [configured](#configuration) by now.

1. Change directories to your newly created project directory:

  ```bash
  cd <dir>
  ```

2. Install NPM dependencies:

  ```bash
  npm install
  ```

3. Start watching assets and scripts for changes (note that this also does the required initial build of the project to the `lib` folder &ndash; which has to happen in order for you to use Crocodile):

  > Assets (also starts [LiveReload](#livereload-built-in)):

  ```bash
  npm run watch-assets
  ```

  > Scripts:

  ```bash
  npm run watch-scripts
  ```

4. Start the processes (install `nodemon` with `npm install -g nodemon`):

  > Web:

  ```bash
  nodemon lib/web
  ```

  > API:

  ```bash
  nodemon lib/api
  ```

  > Jobs:

  ```bash
  nodemon lib/agenda
  ```

5. Go to <http://localhost:3000> in your browser.

6. See [Deployment](#deployment) below for how to set up other environments, such as production.

### Deployment

<img alt="Automated Continuous Integration Deployment Setup" width="649" height="60" style="width:649px;height:60px;" src="https://cdn.rawgit.com/crocodilejs/crocodile-node-mvc-framework/master/media/crocodile-deployment.png" />

We've written a comprehensive tutorial for deployment, continuous integration, and how to automate everything &ndash; you can [read the article here][nifty-ci-setup].

If you're just interested in what tools/services we recommend, then here is a brief list:

* [GitHub][github] - repository hosting
* [Digital Ocean][do-referral]<sup>2</sup> - server hosting
* [SemaphoreCI][semaphoreci] - automated continuous integration
* [Route53][aws] - DNS management
* [Namecheap][namecheap] - domain name registrar
* [PM2][pm2]<sup>1,3</sup> - zero-downtime deployment
* [Sentry][sentry]<sup>1</sup> - log storage and query service
* [S3][aws]<sup>1</sup> - asset storage
* [CloudFront][aws]<sup>1</sup> - content delivery network for assets
* [Postmark][postmarkapp]<sup>1,4</sup> - transactional email
* [MailChimp][mailchimp] - bulk email
* [Slack][slack-referral-url]<sup>5</sup> - chat room &amp; automated notifications

<small><sup>1</sup> Baked into Crocodile by default &ndash; you just need to provide credentials in the [configuration](#configuration) step</small><br />
<small><sup>2</sup> You can get $10 free credit for signing up by clicking our referral link above</small><br />
<small><sup>3</sup> We include `SIGTERM` listener for graceful reloading, see [src/app.js][src-index] for more insight</small><br />
<small><sup>4</sup> You can send 150,000 free ~~credits~~ transactional emails if you're [bootstrapped][bootstrapped-promotion] and [DMARC compliant][dmarc-promotion]</small><br />
<small><sup>5</sup> You can get $100 free credit for signing up by clicking our referral link above</small>

### Advice

The only way to ship code faster is to respect these three points:

1. Use as many [tools](#tools) as possible to automate your workflow.
2. Understand that [good coders code, and great reuse][good-coders-code].
3. Avoid [vim][vim-antipatterns] and [JavaScript][js-antipatterns] anti-patterns and context-switching habits in order to stay focused.

### Tools

Here is a brief list of recommended tools used to ship rapidly developed MVP's:

* Use and modify the included `.github` folder of GitHub contribution templates (e.g. [./github/PULL_REQUEST_TEMPLATE.md][pr-template] is a pull request template).
* Use a Mac OS X (preferred), [Ubuntu][ubuntu], or [Linux Mint][linux-mint] operating system for development.  If you're on Windows, use [VirtualBox][virtualbox] to install [Ubuntu][ubuntu] or [Linux Mint][linux-mint], or you can setup a dual-boot with them.  Or you could use [Vagrant][vagrant].
* Use [brew][brew] to install other tools for planning and building your app (e.g. [GIMP][gimp], [Dropbox][dropbox], [Evernote][evernote], [iTerm 2 Beta][iterm], `google-chrome`, [git-extras][git-extras], [redis][redis], [mongodb][mongodb], `vim`, `wget`, ...).
* Use [Seuss.md][seuss] to plan out your thoughts in a Markdown document before writing any code (this is the "Readme First Approach" that [@tj][tj-github] and [@substack][substack-github] shared with me).
* Use [Sketch][sketch] to design your app's screens and basic mockups.
* Use `vim` as your editor to write your code &ndash; build up muscle memory by installing magnitude of plugins, which will automate [your puny human][puny-human] mistakes.  If you need inspiration, here is [@niftylettuce's vim config][vim-config].
* Install an `eslint` plugin into your text editor so that on file save it lints your code according to the rules defined in the [.eslintrc][eslint-file] file.
* Use [LookerUpper][lookerupper] plugin to easily lookup package documentation.
* Use [fixpack][fixpack] to keep your `package.json` file tidy by running `fixpack` after you alter it.
* Instead of using `npm install --save <name>` to install packages, use [pnpm][pnpm] to install them faster; `pnpm install --save <name>`.


## <a href="#crocodile-index">:crocodile:</a> [Is there a book on CrocodileJS?](#crocodile-is-there-a-book-on-crocodilejs)

**Yes, there is a book (coming soon) called <u>Rapid MVP's</u>**.  It comes with Markdown, HTML, and PDF versions, and also accompanying **<u>source code</u> AND <u>screencasts</u>**!  The author [@niftylettuce][nifty-twitter] is self-publishing, and goes in-depth to show you how to build rapid MVP's.  The book will include a "How It's Made" for at least two of his new (and hopefully profitable) side-projects.

It is **available for <u>early bird</u> pre-order** right now at <https://rapidmvp.com>!  Even if you don't buy the book, you can still get free/inspirational behind the scenes tips, tutorials, and videos!  And a sticker!

> **Get a <u>FREE CROCODILE STICKER</u> mailed to you: <https://rapidmvp.com>** (no pre-order required)

## <a href="#crocodile-index">:crocodile:</a> [Can I get help?](#crocodile-can-i-get-help)

<a href="http://slack.crocodilejs.com"><img alt="Join us in Slack" src="https://cdn.rawgit.com/crocodilejs/crocodile-node-mvc-framework/master/media/crocodile-slack-join.png" width="300" height="255" style="width:300px; height:255px;" /></a>

[Join us in Slack][slack-url].  Still need help?  [File an issue](/issues).


## <a href="#crocodile-index">:crocodile:</a> [How do I get updates?](#crocodile-how-do-i-get-updates)

We provide updates to this repository and a detailed changelog, which you can then add/merge into your project.

The [GitHub Releases Pages][gh-releases] provides detailed documentation for every release of CrocodileJS.

You can also use the CLI tool `crocodile`, and run the command `crocodile upgrade` in order to upgrade your project.

Please note that after you upgrade, you will need to update the version specified in `.crocodile.yml` of your project.

You will need to "star" and "watch" this repository to stay active.  We don't have an automated update system nor a Google Group.  It is your responsibility and duty as a CrocodileJS developer to stay up to date on everything.  **<u>Lastly, it's a necessity</u>** that you [join us on Slack][slack-url] to stay in the loop!

You can also follow us on Twitter at <https://twitter.com/niftylettuce>.


## <a href="#crocodile-index">:crocodile:</a> [Who built it?](#crocodile-who-built-it)

CrocodileJS v1.0.0 was released in September 2016 by [@niftylettuce][nifty-twitter].

## <a href="#crocodile-index">:crocodile:</a> [Can we hire or partner with @niftylettuce?](#crocodile-can-we-hire-niftylettuce)

I am always willing to entertain new opportunities.  Please reach out to me at <niftylettuce@gmail.com>.

## <a href="#crocodile-index">:crocodile:</a> [License](#crocodile-licee)

Crocodile is [MIT][license-url] licensed

[gh-mongoose-issue]: https://github.com/Automattic/mongoose/issues/3683#issue-122632405
[mongoose-json-select]: https://github.com/nkzawa/mongoose-json-select
[mongoose-beautiful-unique-validation]: https://github.com/matteodelabre/mongoose-beautiful-unique-validation
[koa-nunjucks-promise]: https://github.com/hanai/koa-nunjucks-promise
[koa-ratelimit]: https://github.com/koajs/ratelimit
[koa-conditional-get]: https://github.com/koajs/conditional-get
[koa-etag]: https://github.com/koajs/etag
[koa-response-time]: https://github.com/koajs/response-time
[koa-connect-flash]: https://github.com/theverything/koa-connect-flash
[istanbul]: https://github.com/gotwarlost/istanbul
[jsdom]: https://github.com/tmpvar/jsdom
[mocha]: https://github.com/mochajs/mocha
[dirty-chai]: https://github.com/prodatakey/dirty-chai
[check-chai]: https://github.com/niftylettuce/check-chai
[chai]: https://github.com/chaijs/chai
[koa-livereload]: https://github.com/yosuke-furukawa/koa-livereload
[gulp-livereload]: https://github.com/vohof/gulp-livereload
[request]: https://github.com/request/request
[boom]: https://github.com/hapijs/boom
[chalk]: https://github.com/chalk/chalk
[chalkline]: https://github.com/niftylettuce/chalkline
[dotenv]: https://github.com/motdotla/dotenv
[frisbee]: https://github.com/niftylettuce/frisbee
[koa-convert]: https://github.com/koajs/convert
[lodash]: https://github.com/lodash/lodash
[moment]: https://github.com/moment/moment
[underscore-string]: https://github.com/epeli/underscore.string
[validator]: https://github.com/chriso/validator.js
[koa-manifest-rev]: https://github.com/niftylettuce/koa-manifest-rev
[gulp-rev]: https://github.com/sindresorhus/gulp-rev
[babelify]: https://github.com/babel/babelify
[browserify]: https://github.com/substack/node-browserify
[eslint]: https://github.com/eslint/eslint
[gulp-awspublish]: https://github.com/pgherveou/gulp-awspublish
[gulp-cloudfront]: https://github.com/smysnk/gulp-cloudfront
[gulp-eslint]: https://github.com/adametry/gulp-eslint
[gulp-imagemin]: https://github.com/sindresorhus/gulp-imagemin
[gulp-postcss]: https://github.com/postcss/gulp-postcss
[gulp-sourcemaps]: https://github.com/floridoo/gulp-sourcemaps
[gulp-uglify]: https://github.com/terinjokes/gulp-uglify
[imagemin-pngquant]: https://github.com/imagemin/imagemin-pngquant
[noun-project]: https://thenounproject.com/term/doughnut/163279/
[license-image]: http://img.shields.io/badge/license-MIT-blue.svg
[license-url]: LICENSE
[mvc]: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
[nodejs]: https://nodejs.org
[node]: https://nodejs.org
[rapid-mvp]: https://github.com/niftylettuce/rapid-mvp-standards
[frameworks-dont-make-sense]: http://www.catonmat.net/blog/frameworks-dont-make-sense/
[async-await]: https://tc39.github.io/ecmascript-asyncawait/
[pkrumins]: https://twitter.com/paulg
[nifty-twitter]: https://twitter.com/niftylettuce
[pg-twitter]: https://twitter.com/pkrumins
[dont-scale]: http://paulgraham.com/ds.html
[npm]: https://www.npmjs.com/
[lookerupper]: https://github.com/niftylettuce/lookerupper
[puny-human]: http://fakegrimlock.com/
[vim-config]: https://github.com/niftylettuce/.vim
[eslint-file]: .eslintrc
[fixpack]: https://github.com/henrikjoreteg/fixpack
[good-coders-code]: http://www.catonmat.net/
[seuss]: https://github.com/niftylettuce/seuss.md
[tj-github]: https://github.com/t
[substack-github]: https://github.com/substack
[eskimo-ship]: http://niftylettuce.com/posts/eskimo-rapid-mvp-node-boilerplate/
[react]: https://github.com/facebook/react
[angular]: https://github.com/angular/angular
[nunjucks]: https://mozilla.github.io/nunjucks/
[standard-signature]: https://standardsignature.com/
[prove]: https://getprove.com
[wakeup]: https://wakeup.io
[niftylettuce-website]: http://niftylettuce.com
[pnpm]: https://github.com/rstacruz/pnpm
[gimp]: https://www.gimp.org/
[dropbox]: https://db.tt/2ZTl6efc
[evernote]: https://www.evernote.com/referral/Registration.action?sig=2e640ea469c7e68be162fb13114e2dca&uid=80317596
[iterm]: https://www.iterm2.com/
[git-extras]: https://github.com/tj/git-extras
[redis]: http://redis.io/
[mongodb]: https://www.mongodb.org/
[brew]: http://brew.sh/
[sketch]: https://www.sketchapp.com/
[koa]: https://github.com/koajs/koa/tree/v2.x
[slack-image]: http://slack.crocodilejs.com/badge.svg
[slack-url]: http://slack.crocodilejs.com
[mongoose]: http://mongoosejs.com/
[passport]: https://github.com/jaredhanson/passport
[passport-google-oauth]: https://github.com/jaredhanson/passport-google-oauth
[passport-package]: https://www.npmjs.com/search?q=passport
[pg]: https://github.com/brianc/node-postgres
[bookshelf]: https://github.com/tgriesser/bookshelf
[spa-image]: https://cdn.rawgit.com/crocodilejs/crocodile-node-mvc-framework/master/media/spa-image.svg
[avc-chicken-image]: https://cdn.rawgit.com/crocodilejs/crocodile-node-mvc-framework/master/media/avc-eat-this-chicken.jpg
[fake-grimlock]: http://avc.com/2011/09/minimum-viable-personality/
[browserify]: http://browserify.org
[babelify]: https://github.com/babel/babelify
[gulpfile]: gulpfile.babel.js
[gulp]: http://gulpjs.com/
[sweetalert2]: https://github.com/limonte/sweetalert2
[crocodile-dependencies]: https://cdn.rawgit.com/crocodilejs/crocodile-node-mvc-framework/master/media/crocodile-deployment.png
[callback-hell]: http://callbackhell.com/
[bootstrap-4-alpha]: http://v4-alpha.getbootstrap.com/
[koa-compress]: https://github.com/omsmith/compress/tree/koa2
[lookup-operator]: https://docs.mongodb.org/manual/reference/operator/aggregation/lookup/
[koa-helmet]: https://github.com/venables/koa-helmet
[dns-prefetch]: https://github.com/helmetjs/dns-prefetch-control
[frameguard]: https://github.com/helmetjs/frameguard
[poweredby]: https://github.com/helmetjs/hide-powered-by
[hsts]: https://github.com/helmetjs/hsts
[ienoopen]: https://github.com/helmetjs/ienoopen
[nosniff]: https://github.com/helmetjs/dont-sniff-mimetype
[xssfilter]: https://github.com/helmetjs/x-xss-protection
[koa-vs-express]: https://github.com/koajs/koa/blob/master/docs/koa-vs-express.md
[express]: http://expressjs.com/
[stripe-inspired]: https://www.heavybit.com/library/video/move-fast-dont-break-api/
[eslint-config-airbnb]: https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb
[config-file-seo]: src/config/index.js
[src-index]: src/app.js
[mirror-it]: https://help.github.com/articles/duplicating-a-repository/
[nifty-ci-setup]: http://niftylettuce.com/posts/automated-node-app-ci-graceful-zerodowntime-github-pm2/
[slack-referral-url]: https://slack.com/r/02kjqk4v-06846hdf
[mailchimp]: http://mailchimp.com/
[postmarkapp]: https://postmarkapp.com
[aws]: https://console.aws.amazon.com
[sentry]: https://getsentry.com
[pm2]: https://github.com/Unitech/pm2
[namecheap]: https://www.namecheap.com/?aff=34556
[do-referral]: https://m.do.co/c/a7fe489d1b27
[github]: https://github.com/
[semaphoreci]: https://semaphoreci.com/
[dmarc-promotion]: https://postmarkapp.com/blog/get-100000-free-postmark-credits
[bootstrapped-promotion]: https://twitter.com/postmarkapp/status/197121068052389888
[src-config]: src/
[dot-env-file]: .env.example
[nvm]: https://github.com/creationix/nvm
[vagrant]: https://www.vagrantup.com/
[virtualbox]: https://www.virtualbox.org/wiki/Downloads
[linux-mint]: https://www.linuxmint.com/
[ubuntu]: http://www.ubuntu.com
[pr-template]: .github/PULL_REQUEST_TEMPLATE.md
[build-image]: https://semaphoreci.com/api/v1/niftylettuce/crocodile-node-mvc-framework/branches/master/shields_badge.svg
[build-url]: https://semaphoreci.com/niftylettuce/crocodile-node-mvc-framework
[agenda]: https://github.com/rschmukler/agenda
[codecov-image]: https://img.shields.io/codecov/c/github/crocodilejs/crocodile-node-mvc-framework/master.svg
[codecov-url]: https://codecov.io/github/crocodilejs/crocodile-node-mvc-framework
[standard-image]: https://img.shields.io/badge/code%20style-standard%2Bes7-brightgreen.svg
[standard-url]: https://github.com/crocodilejs/eslint-config-crocodile
[stability-image]: https://img.shields.io/badge/stability-stable-green.svg
[stability-url]: https://nodejs.org/api/documentation.html#documentation_stability_index
[src-assets]: src/assets/
[email-templates]: https://github.com/niftylettuce/node-email-templates
[crocodile-demo]: https://crocodilejs.com
[twelve-factors]: http://12factor.net/
[mustache]: https://github.com/janl/mustache.js/
[dotenv-extended]: https://github.com/keithmorris/node-dotenv-extended
[dotenv-mustache]: https://github.com/samcrosoft/dotenv-mustache
[dotenv-parse-variables]: https://github.com/niftylettuce/dotenv-parse-variables
[codecov]: https://codecov.io
[js-antipatterns]: https://shichuan.github.io/javascript-patterns/
[vim-antipatterns]: https://sanctum.geek.nz/arabesque/vim-anti-patterns/
[passport-stripe]: https://github.com/mathisonian/passport-stripe
[passport-facebook]: https://github.com/jaredhanson/passport-facebook
[passport-twitter]: https://github.com/jaredhanson/passport-twitter
[passport-github]: https://github.com/jaredhanson/passport-github
[passport-linkedin]: https://github.com/jaredhanson/passport-linkedin
[passport-instagram]: https://github.com/jaredhanson/passport-instagram
[lean-method]: http://www.tothenew.com/blog/high-performance-find-query-using-lean-in-mongoose-2/
[mongoose-static-method]: http://mongoosejs.com/docs/guide.html#statics
[grunt]: http://gruntjs.com/
[outdated-express]: https://github.com/balderdashy/sails/issues/3460
[totaljs-example]: https://github.com/totaljs/framework/blob/master/index.js
[node-philosophy]: http://substack.net/how_I_write_modules
[hackathon-starter]: https://github.com/sahat/hackathon-starter
[totaljs]: https://www.totaljs.com/
[hapijs]: http://hapijs.com/
[sailsjs]: http://sailsjs.org/
[hackathon-app-file]: https://github.com/sahat/hackathon-starter
[gh-boilerplate]: https://www.google.com/search?q=github+node+boilerplate
[gh-releases]: https://github.com/crocodilejs/crocodile-node-mvc-framework/releases
[won-hackathon]: http://www.hackathon.io/tbd

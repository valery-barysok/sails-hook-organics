# sails-stdlib

Standard library for Node/Sails applications.

This package contains a set of hand-picked, trusted modules recommended by the Sails core team.


## Installation

```bash
npm install sails-stdlib --save
```


## Usage

```js
var stdlib = require('sails-stdlib');
var Gravatar = stdlib('gravatar'); // << just like doing `require('machinepack-gravatar');`
var Mailgun = stdlib('mailgun'); // << just like doing `require('machinepack-mailgun');`
```

### Documentation

##### General
- [ifthen](http://node-machine.org/machinepack-ifthen)
- [strings](http://node-machine.org/machinepack-strings)
- [numbers](http://node-machine.org/machinepack-numbers)
- [booleans](http://node-machine.org/machinepack-booleans)
- [dictionaries](http://node-machine.org/machinepack-dictionaries)
- [arrays](http://node-machine.org/machinepack-arrays)
- [json](http://node-machine.org/machinepack-json)
- [datetime](http://node-machine.org/machinepack-datetime/)
- [math](http://node-machine.org/machinepack-math)
- [paths](http://node-machine.org/machinepack-paths)
- [urls](http://node-machine.org/machinepack-urls)
- [emailaddresses](http://node-machine.org/machinepack-emailaddresses)

##### Scripts and NPM Packages
- [fs](http://node-machine.org/machinepack-fs)
- [http](http://node-machine.org/machinepack-http)
- [process](http://node-machine.org/machinepack-process)
- [console](http://node-machine.org/machinepack-console)
- [util](http://node-machine.org/machinepack-util)

##### App Servers & Web APIs
- [waterline](http://node-machine.org/machinepack-waterline)
- [sockets](http://node-machine.org/machinepack-sockets)
- [reqres](http://node-machine.org/machinepack-reqres)
- [sessionauth](http://node-machine.org/machinepack-sessionauth)
- [passwords](http://node-machine.org/machinepack-passwords)
- [mailgun](http://node-machine.org/machinepack-mailgun)
- [gravatar](http://node-machine.org/machinepack-gravatar)



### Example

```js
var stdlib = require('sails-stdlib');
var Gravatar = stdlib('gravatar');
var Mailgun = stdlib('mailgun');


// Get a gravatar for an email address.
// (http://node-machine.org/machinepack-gravatar/get-image-url)
var imageGravatar.getImageUrl({
  emailAddress: 'amy@gonzales-enterprises.com',
  gravatarSize: 400
}).execSync();


// Send an html email.
// (http://node-machine.org/machinepack-mailgun/send-html-email)
Mailgun.sendHtmlEmail({
  apiKey: 'key-3432afa32e9401482aba183c13f3',
  domain: 'sandbox5f89931913a9ab31130131350101.mailgun.og',
  toName: 'Amy Gonzales',
  subject: 'Welcome, Amy!',
  htmlMessage: 'Amy,\nThanks for joining our community. If you have any questions, please don\'t hesitate to send them our way. Feel free to reply to this email directly.\n\nSincerely,\nThe Management',
  fromEmail: 'harold@example.enterprise',
  fromName: 'Harold Greaseworthy',
}).exec(function (err) {
  if (err) {
    console.error('Failed to send email. Details:',err);
    return;
  }

  console.log('Email sent!');

});
```



## FAQ

#### I think I found a bug.

Thanks for taking the time to help out!  Please [create an issue](https://github.com/sailsjs/stdlib/issues/new) in this repo and someone will look into it ASAP.
If you see how to fix the problem and have a moment to prepare a patch, feel free to submit a pull request to the appropriate repo.

> Please be aware that we can't merge any unsolicited PRs that contain changes to usage, including additional methods or options.
> With this project, we're trying really hard to keep things consistent between individual methods, and that means being
> vigilant about the effect of any usage change in the grand scheme of the library.


#### I have an idea for how to improve...

We'd like to hear it!  The best way to share your ideas is to contribute (see below).


#### I wish this supported...

We are constantly looking for ways to improve this library. If we're missing something you need from a particular pack,
tweet at [@sailsjs](https://twitter.com/sailsjs) to explain your use case and we'll see what we can do.
If you're in a hurry, just look up the repo for the package in question from the list below, then create a fork.


#### Where's the code?

Each package in the standard library lives in its own repository:

##### General
- [ifthen](https://github.com/treelinehq/machinepack-ifthen)
- [strings](https://github.com/treelinehq/machinepack-strings)
- [numbers](https://github.com/treelinehq/machinepack-numbers)
- [booleans](https://github.com/treelinehq/machinepack-booleans)
- [dictionaries](https://github.com/treelinehq/machinepack-dictionaries)
- [arrays](https://github.com/treelinehq/machinepack-arrays)
- [json](https://github.com/treelinehq/machinepack-json)
- [datetime](https://github.com/sgress454/machinepack-datetime/)
- [math](https://github.com/treelinehq/machinepack-math)
- [paths](https://github.com/treelinehq/machinepack-paths)
- [urls](https://github.com/mikermcneil/machinepack-urls)
- [emailaddresses](https://github.com/mikermcneil/machinepack-emailaddresses)

##### Scripts and NPM Packages
- [fs](https://github.com/mikermcneil/machinepack-fs)
- [http](https://github.com/mikermcneil/machinepack-http)
- [process](https://github.com/treelinehq/machinepack-process)
- [console](https://github.com/treelinehq/machinepack-console)
- [util](https://github.com/treelinehq/machinepack-util)

##### App Servers & Web APIs
- [waterline](https://github.com/treelinehq/machinepack-waterline)
- [sockets](https://github.com/sgress454/machinepack-sockets)
- [reqres](https://github.com/mikermcneil/machinepack-reqres)
- [sessionauth](https://github.com/treelinehq/machinepack-sessionauth)
- [passwords](https://github.com/mikermcneil/machinepack-passwords)
- [mailgun](https://github.com/particlebanana/machinepack-mailgun)
- [gravatar](https://github.com/irlnathan/machinepack-gravatar)


#### Where's the changelog?

The [CHANGELOG.md file in this repo](./CHANGELOG.md) contains a record of usage changes for all of the packs in the standard library (in other words, any minor or major version bumps to the dependencies listed in the package.json file).  This makes the changelog more accurate and easier to update, since it saves contributors from having to maintain individual changelogs in at least 20 different repos.


#### Does this use semver?

Dependency versions are pinned, and all releases of `sails-stdlib` are carefully tested to ensure strict semantic versioning.


#### Does this support custom builds?

You can install and use any of the packages in this repo individually.  Just require the machinepack directly.


#### How do I run the tests?

Tests for each package are implemented in its repo.


#### What does the future hold?

The roadmap for this library is flexible and we're open to ideas.  The important thing is that we remain relentlessly focused on stability and versatility,
while keeping the library relatively lightweight and the usage intuitive.  Secondary to that, most of the immediate-term
improvements we're interested in making are related to performance.


#### I'd like to contribute.

Awesome!  Tweet [@sailsjs](https://twitter.com/sailsjs) and let us know the minimum # of hours per week you'll
be able to commit, and someone from the core team will contact you ASAP. 



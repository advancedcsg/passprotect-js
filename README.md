# passprotect-js

**_This is a fork from https://github.com/OktaSecurityLabs/passprotect-js_**

This is published as an NPM package to Artifactory as `@advanced/passprotect`. To install run:

```sh
npm install @advanced/passprotect
```

## Demo

![PassProtect demo](https://github.com/oktasecuritylabs/passprotect-js/raw/master/assets/passprotect.gif)

## What is PassProtect?

PassProtect is a developer library created and maintained by [Randall Degges](https://twitter.com/rdegges)
that you can drop into any web page which dramatically improves the security
of users accessing your website.

PassProtect works by binding itself to all `input` elements on the page of type 
`email` or `password`. Whenever a user enters a new value into one of these
`input` elements, PassProtect will check the user's email / password against
the fabulous [Have I Been Pwned?](https://haveibeenpwned.com) API service to see whether or not
the user's email OR password has been breached in the past.

Finally, if appropriate, PassProtect will inform the user that their credentials
were previously breached, give them some useful information, and ask them to
update their password as soon as they can to reduce the risk that their account
will be compromised.

PassProtect is a new, experimental way to proactively notify users about data
breaches and help casual web users play a more active role in protecting their
online accounts.

We believe that by informing and guiding users to reset their credentials when
necessary, we can all help make the web a safer place &lt;3


## How to Use PassProtect

To use PassProtect in your website, simply copy the following script tag
anywhere on your page. Don't worry about where you put it: anywhere is fine. It
will run once the page has loaded and will initialize itself without any
configuration necessary.

```html
<html>
  <head>
    <!-- ... -->
  </head>
  <body>
    <!-- ... -->
    <script src="https://cdn.passprotect.io/passprotect.min.js"></script>
  </body>
</html>
```

You'll ideally want to include the PassProtect script tag on every page that
contains an `input` element. There is almost no performance penalty for
including PassProtect on all pages of your site -- if a page doesn't contain any
`input` elements, PassProtect won't do anything and will immediately exit.

To keep things simple, our recommended approach is to just include the
PassProtect script on every page of your site.

## Initialising on demand

If you need to initialise the loading on demand, you can call the global function:

```js
window.passprotect.protectInputs()
```


## Is PassProtect Secure?

**YES!**

PassProtect never sends or stores password information over the network. It uses
[k-Anonymity](https://www.troyhunt.com/ive-just-launched-pwned-passwords-version-2/)
to safely communicate your sensitive data over the internet without risk.

PassProtect is also completely free, open source, and maintained by [Randall
Degges](https://twitter.com/rdegges). If you want to audit the source, or have
ideas about how to do things better, please open a
[GitHub issue](https://github.com/oktasecuritylabs/passprotect-js) or [email me](mailto:randall.degges@okta.com) directly.


## Changelog

**1.0.0**: May 24, 2018

- Removing email breach detection functionality.

**0.2.1**: May 22, 2018

- Improving form binding for posterity.

**0.2.0**: May 22, 2018

- Removing redundant `npm publish` script.
- Adding Firefox support.

**0.1.0**: *May 19, 2018*

- First release! Yey.

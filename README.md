# ELMS:LN style guides
Style guides for contributing to ELMS:LN. This is both code and visual styling. It is intended to be a guide to contributing to the platform and is always considered a work in progress.

## Design
This is outdated but we did have a professional, open style guide commissioned in 2013 - https://github.com/elmsln/elms-styles. We generally are now aligning with the [Material Design specification](https://material.io/guidelines/). All design and styles are currently being normalized now that we have a design lead dedicated to the project.

## PHP
Whenever possible we'll defer to the standards of the software community we are borrowing from. For example, PHP standards are relative to the [Drupal coding standards](https://www.drupal.org/docs/develop/standards). While these standards are written towards Drupal 8 and we are mostly Drupal 7 they are still largely applicable. This is a monster of a platform so documentation of what's going on in functions is much appreciated by our user base when they need to fix something a year from now and don't remember what was going on :).

## Javascript
While not exclusively Webcomponents, ELMS:LN is transitioning entirely to webcomponents. As such, we have some minor conventions worth noting specific to Webcomponents and Polymer.
- Keep an eye towards the notion of #usetheplatform. This means whenever possible, use what's baked into the browser as opposed to pulling in 3rd party libraries. For example, we shouldn't be pulling in a copy and paste clipboard manager (clipboard.js) when a simple `document.execCommand('copy');` will work across our target browsers.
- commas at the end of array and object statements:
```
street: {
  type: String,
  value: 'default address',
},
```
- docblock comment all properties and functions in polymer webcomponents
```
/**
 * Street the user lives on, typically the top line in a mailing address.
 */
street: {
  type: String,
  value: 'default address',
},
```
- We currently ride on Polymer 1.x.x, all polymer based elements should be compatible with it.
- Whenever possible, develop hybrid elements that work across Polymer versions.
- Always use `this.addEventListener` instead of a `listeners: {}` object in Polymer elements produced
- only use `notify: true` when intending for an event to bubble up

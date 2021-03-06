# Angular Date Picker Polyfill

This is an [HTML5 date input](http://diveintohtml5.info/forms.html#type-date) polyfill for Angular.js. For browsers such as Chrome and Safari for iOS, the native datepicker will be used and this directive will have no effect, but for others it will add a datepicker popup to inputs of type `date` and `datetime-local`. Or if you want your UX to be completely consistent across browsers, you can add the directive to any other type of element.

## Dependencies

* Angular 1.3+
* Modernizr

## Usage

First, you'll need to include the javascript and css file and include 'angular-date-picker-polyfill' as a dependency in your angular module.

```javascript
angular.module('myApp', ['angular-date-picker-polyfill']);
```

Next, it will simply work for any date inputs in your app:

```html
<input type='date' ng-model='myDate' />
```

Angular 1.3 has built-in support for date inputs and takes care of setting validity on the field. But note that your model must be a javascript date object. It will not parse dates for you.

If you want to apply it to a normal text field, or if you don't want to use native datepickers, you can just add the `aa-date-input` attribute like so:

```html
<input type='text' ng-model='myDate' aa-date-input />
```

And if you want to use it on a non-input element, you can do something like the following:

```html
<button type='button' tabindex='0' ng-model='myDate' aa-date-input>
  <span ng-show='myDate'>{{ myDate | date:'shortDate'}}</span>
  <span ng-hide='myDate'>Not Set</span>
</button>
```

Note the `tabindex` attribute. This will allow the button (or any other element) to gain focus like a normal form field.

It works similarly for Date/Time. It will automatically work for inputs of type `datetime-local`.

```html
<input type='datetime-local' ng-model='myDate' />
```

And if you want to apply it to other elements, just add the `aa-date-time-input` attribute.

```html
<button type='button' tabindex='0' ng-model='myDate' aa-date-time-input>
  <span ng-show='myDate'>{{ myDate | date:'short'}}</span>
  <span ng-hide='myDate'>Not Set</span>
</button>
```

You can also use the Calendar and Timepicker inline and outside the context of the popup:

```html
<div ng-model='myDate' aa-calendar></div>
```

```html
<div ng-model='myDate' aa-timepicker></div>
```

## Theming

There is a very basic theme provided. Others may be added later and I would love for others to contribute additional ones.

## Dev Status

This is still alpha software and has not yet been well tested.

## TODO:

- [ ] Better test coverage
- [ ] Setup automatic testing using a CI service
- [ ] Additional Themes

## Development

### Requirements:

* [NPM](https://www.npmjs.com)
* [Gulp](http://gulpjs.com)
* [PhantomJS](http://phantomjs.org)

After cloning the repository, run the following to install the dependencies:

```sh
npm install && bower install
```

Then to watch and compile assets:
```sh
gulp dev
```

And to run the tests:
```
npm run spec
```

## Contributing

Contributions are welcome. Non-CSS changes that don't include test coverage will not be merged.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request




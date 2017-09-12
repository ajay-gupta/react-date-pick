# React Date Pick
A simple and reusable Datepicker component for React

## Installation

The package has can be installed via:
- Bower: `bower install react-date-pick`
- NPM: `npm install react-date-pick —-save`
- Bundler (rails gem): `bundle install rails-assets-react-date-picker`. This requires to include https://rails-assets.org/ as a source in your gemfile.

You’ll need to install React and Moment.js separate since those dependencies aren’t included in the package. Below is a simple example on how to use the Datepicker in a React view.

```
var React = require(‘react’);
var DatePicker = require(‘react-datepicker’);
var moment = require(‘moment’);

var Example = React.createClass({
  displayName: ‘Example’,

  getInitialState: function() {
    return {
      startDate: moment()
    };
  },

  handleChange: function(date) {
    this.setState({
      startDate: date
    });
  },

  render: function() {
    return <DatePicker
        selected={this.state.startDate}
        onChange={this.handleChange} />;
  }
});
```

## Configuration

The default Datepicker can be initialised by:

```
<DatePicker
        selected={this.state.startDate}
        onChange={this.handleChange} />
```

This included the Datepicker with its default functionality. To use more functionality you can pass extra props to the Datepicker to enable them.

- Change date format by passing a different date format in the props: `dateFormat: “YYYY/MM/DD”`
- Add placeholder text: `placeholderText: ‘Click to select a date’` (Defaults to the selected date when no placeholder text is added)
- Give users a predefined date range: `minDate: moment()` & `maxDate: moment().add(5, ‘days’)` (this gives users the ability to select a date between today and 5 days in the future)
- Exclude a set of dates from those that are selectable: `excludeDates: [ moment(), moment(‘2015-01-01’) ]` (prevent users from selecting today or Jan 1st, 2015)
- Set custom moment.js instance (could have defined custom locale settings): `moment: require(‘./foo/moment’)`
- Set custom locale settings for locale: `locale: “cs”`
- Set date format for calendar: `dateFormatCalendar: “YYYY/MM/DD”`
- Set custom weekdays (for locale days): `weekdays: [‘Ne’, ‘Po’, ‘Út’, ‘St’, ‘Čt’, ‘Pá’, ‘So’]`
- Set custom calendar week start day: `weekStart: ‘0’` would start the week on Sunday


## Local Development


# The component
To help you developing the component we’ve set up some tests that covers the basic functionality (can be found in  `/tests`). Although, we’re a big fan of tests, this only covers a small piece of the component. We highly recommend you to add a tests when you’re adding new functionality.

While developing, you can run `grunt watch` to compile your changes, run linters and tests.

# The examples
The example site is a simple app that uses the Datepicker by simply requiring the latest published version. This makes it the ideal real world example for every other website that wants to use the component.

To extend the examples with a new example, you can simply duplicate one of the existing examples and change the unique properties of your example.

To start your example app, you can run `npm start`. This starts a simple webserver on http://localhost:8080. You changes will be automatically reloaded in the browser.

To compile your changes for the gh-pages branch you need to run `npm run webpack` when you’re done.

## License

Licensed under MIT license, see [LICENSE](LICENSE) for the full license.

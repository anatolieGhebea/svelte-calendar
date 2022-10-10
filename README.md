# NOTES
This package is mostly an extension for the 6edesign/svelte-calendar, for the time beeing refer to the orignal documentation.

# svelte-calendar

A small date picker built with Svelte 3. Demo available here: [view docs and examples](https://6edesign.github.io/svelte-calendar).

![Demo](static/demo.gif)

## Installation

original package
```sh
npm i -D svelte-calendar
```

this package
```sh
npm i @anatolieghebea/svelte-calendar
```

## Features

- Day, Month & Year pickers
- Responsive
- Keyboard, touch, and scroll support
- Inline & Picker modes
- Virtual/infinite grid for animation performance
- Store-driven and extensible
- [Localization](https://6edesign.github.io/svelte-calendar) using `day.js`
- Posibility to disable an array of dates

## Usage within svelte-kit project

When using this component within a svelte-kit application it is necessary to add its two dependencies (`just-throttle` and `dayjs`) to the `config.kit.vite.optimizeDeps.include` array in `svelte.config.js`. Eg: your config should include the following:

```js
const config = {
  kit: {
    vite: {
      optimizeDeps: {
        include: ['just-throttle', 'dayjs']
      }
    }
  }
};

export default config;
```

# Disabling dates 

````
  <script>
  import dayjs from 'dayjs';
	import { Datepicker } from '@anatolieghebea/svelte-calendar';

	const today = new Date();
	const tomorrow = dayjs().add(7, 'day').toDate();

	// the format must be specified, it's used in the store to format and compare the dates to be excluded
	const format = 'YYYY-MM-DD';
	const disabled = [ dayjs().add(2, 'day').format(format), dayjs().add(4, 'day').format(format) ];

  </script>
  <Datepicker start={today} end={tomorrow} {format} disabledDates={disabled} />
````


## Features In Development

- time picker
- date & date-time range picker

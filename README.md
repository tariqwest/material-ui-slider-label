

# Material UI Slider + Value Label

[Material UI](http://www.material-ui.com/) is a set of [React](http://facebook.github.io/react/) components that implement
[Google's Material Design](https://www.google.com/design/spec/material-design/introduction.html)
specification.

Among these really great components is a [slider](http://www.material-ui.com/#/components/slider), but it is missing the [value label / info bubble](https://material.io/guidelines/components/sliders.html#sliders-discrete-slider) the Google design guideline calls for. 

This component augments the Material UI Slider component with a value label / info bubble styled to your specifications.

![enter image description here](https://cloud.githubusercontent.com/assets/61205/18767638/07c9da50-80e6-11e6-92d6-eb2828bbd8ed.gif)


## Installation
```
npm install https://github.com/tariqwest/material-ui-slider-label.git
```

## Usage

Use this with Material UI to add a label bubble to a slider.

**./SearchRadiusInput.js**
```jsx
import React from 'react';
import Subheader from 'material-ui/Subheader';
import Slider from 'material-ui-slider-label/Slider';
import { cyan500 } from 'material-ui/styles/colors';

const styles = {
  subheader: {
    textTransform: 'capitalize',
  },
  labelStyleOuter: {
    width: '30px',
    height: '30px',
    borderRadius: '50% 50% 50% 0',
    background: cyan500,
    position: 'absolute',
    transform: 'rotate(-45deg)',
    top: '-40px',
    left: '-9px',
  },
  labelStyleInner: {
    transform: 'rotate(45deg)',
    color: 'white',
    textAlign: 'center',
    position: 'relative',
    top: '3px',
    right: '0px',
    fontSize: '10px',
  },
};

const SearchRadiusInput = ({ radius, onChange }) => (
  <div>
    <Subheader style={styles.subheader}>
      {'Search radius'}
    </Subheader>
    <Slider
      defaultValue={5 / 100}
      min={0}
      max={1}
      step={5 / 100}
      value={radius / 100}
      onChange={onChange}
      label={
        <div style={styles.labelStyleOuter}>
          <div style={styles.labelStyleInner}>
            {radius}
          </div>
        </div>
      }
    />
  </div>
);

export default SearchRadiusInput;

```


## License
This project is licensed under the terms of the
[MIT license](https://github.com/tariqwest/material-ui-slider-label/blob/master/LICENSE)

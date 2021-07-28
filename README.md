# Date-Picker

### Install
 #### npm
    npm i react-datepicker
 #### yarn 
    yarn add react-datepicker
    
### Code
 ``` 
import DatePicker from "react-datepicker";
import React, { useState } from 'react'
import "react-datepicker/dist/react-datepicker.css";

function App() {

  const [date, setSubscriptionType] = useState({
    date:new Date()
  })

  const handleChange = (key, value) => {
    setSubscriptionType((prev) => ({ ...prev, [key]: value }));
  };

  return (
    <div>

      <DatePicker
        selected={date.date}
        onChange={(e) => handleChange("date", e)}
        placeholderText="Date"
      />
      
    </div>
  );
}

export default App;

```

### Clear datepicker input

```


      <DatePicker
        selected={date.date}
        onChange={(e) => handleChange("date", e)}
        isClearable
        placeholderText="Date"
      />
      
   
```

### Custom date format

```
      <DatePicker
        selected={date.date}
        onChange={(e) => handleChange("date", e)}
        dateFormat="dd/MM/yyyy"
        placeholderText="Date"
      />
```

### Custom time class name

```
import DatePicker from "react-datepicker";
import React, { useState } from 'react'
import "react-datepicker/dist/react-datepicker.css";
function App() {

  const [date, setSubscriptionType] = useState({
    date: new Date()
  })

  const handleChange = (key, value) => {
    setSubscriptionType((prev) => ({ ...prev, [key]: value }));
  };

  let handleColor = (time) => {
    return time.getHours() > 12 ? "text-success" : "text-error";
  };


  return (
    <div>

      <DatePicker
        showTimeSelect
        selected={date.date}
        onChange={(date) => handleChange('date', date)}
        timeClassName={handleColor}
      />

    </div>
  );
}

export default App;

```
### Options

| Name | Type | Description |
| --- | --- | --- |
| dateFormat |  | Defines the format for the date. |
| minDate | Date |  defines minimum date. Disabled earlier dates |
| maxDate | Date | defines maximum date. Disabled later dates |
   
 
 
 


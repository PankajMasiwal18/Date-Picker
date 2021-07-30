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

### Date Range

```
() => {
  const [startDate, setStartDate] = useState(new Date("2014/02/08"));
  const [endDate, setEndDate] = useState(new Date("2014/02/10"));
  return (
    <>
      <DatePicker
        selected={startDate}
        onChange={(date) => setStartDate(date)}
        selectsStart
        startDate={startDate}
        endDate={endDate}
      />
      <DatePicker
        selected={endDate}
        onChange={(date) => setEndDate(date)}
        selectsEnd
        startDate={startDate}
        endDate={endDate}
        minDate={startDate}
      />
    </>
  );
};
```

### Date range for one datepicker

```
() => {
  const [startDate, setStartDate] = useState(new Date());
  const [endDate, setEndDate] = useState(null);
  const onChange = (dates) => {
    const [start, end] = dates;
    setStartDate(start);
    setEndDate(end);
  };
  return (
    <DatePicker
      selected={startDate}
      onChange={onChange}
      startDate={startDate}
      endDate={endDate}
      selectsRange
      inline
    />
  );
};
```
### Options

| Name | Type | Description |
| --- | --- | --- |
| dateFormat |  | Defines the format for the date. |
| minDate | Date |  defines minimum date. Disabled earlier dates |
| maxDate | Date | defines maximum date. Disabled later dates |
   
 
 
 


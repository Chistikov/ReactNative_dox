# Создание компонета

## Создание функционального компонента
app.js
```javascript
import React, { useState } from "react";
import { StyleSheet, View } from "react-native";

import ChildComponent from "./ChildComponent";

export default function(props){
  let [variable, setVariable] = useState(1);
  
  return (
    <View style={styles.container}>
      <ChildComponent counter={variable} changeCounterHandler={changeCounter}/>
    </View>
  )
  
  function changeCounter(newCounterValue){
    setVariable(newCounterValue);
  }
  
  let styles = StyleSheet.create({
    container: {
      backgroundColor: 'red'
    }
  })
}
```

ChildComponent.jsx
```javascript
import React from "react";
import { View, Text } from "react-native";

export default function(props){ 
  return (
    <View style={styles.container}>
      <Text>{props.counter}</Text>
      <Button onPress={btnPressHandler(props.counter++)}/>
    </View>
  );
  
  function btnPressHandler(counter){
    props.changeCounterHandler(counter)
  }
}
```

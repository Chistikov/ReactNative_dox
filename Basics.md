# Создание компонета

## Создание функционального компонента
```javascript
import React, { useState } from "react";
import { StyleSheet, View } from "react-native";

import ChildComponent from "./ChildComponent";

export default function(props){
  let [variable, setVariable] = useState(1);
  
  return (
    <View style={styles.container}>
      <ChildComponent/>
    </View>
  )
  
  let styles = StyleSheet.create({
    container: {
      backgroundColor: 'red'
    }
  })
}
```

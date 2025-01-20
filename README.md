# Random Background Color Generator App

This is a simple React Native application that generates a random background color when a button is pressed. The generated color is displayed on the screen as well.

## Features

- Generates random background colors.
- Displays the hex code of the generated color.
- User-friendly button interface.

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```

2. Navigate to the project directory:
   ```bash
   cd <project-directory>
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

4. Run the app:
   ```bash
   npm start
   ```

## Usage

1. Launch the app on your emulator or physical device.
2. Press the "Press me" button to generate a random background color.
3. The background color of the app will change, and the hex code of the color will be displayed.

## Code Overview

Below is the main code used in the application:

```javascript
import React, { useState } from 'react';

import {
  StatusBar,
  StyleSheet,
  Text,
  TouchableOpacity,
  View,
} from 'react-native';

export default function App(): React.JSX.Element {
  const [randomBackground, setRandomBackground] = useState("#ffffff");

  const generateColor = () => {
    const hexRange = "0123456789ABCDEF"
    let color = "#"

    for (let i=0; i<6; i++) {
      color += hexRange[Math.floor(Math.random() * 16)]
    }

    setRandomBackground(color)
  }

  return (
    <>
      <StatusBar backgroundColor={randomBackground}/>
        <View style={[styles.container, {backgroundColor: randomBackground}]}>
          <TouchableOpacity onPress={generateColor}>
            <View style={styles.actionBtn}>
              <Text style={styles.actionBtnTxt}>Press me</Text>
            </View>
          </TouchableOpacity>
              <Text style={styles.actionBtnTxt}>Color: {randomBackground}</Text>
        </View>
    </>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
  },
  actionBtn: {
    borderRadius: 12,
    backgroundColor: "#6a1b4d",
    paddingVertical: 10,
    paddingHorizontal: 40,
  },
  actionBtnTxt: {
    fontSize: 24,
    color: "#ffffff",
    textTransform: 'uppercase',
  },
});
```

## Screenshots

#default color :-
![default](https://github.com/user-attachments/assets/8b60b305-7606-438a-b7b2-71542dca0913)

#after click :-
![1](https://github.com/user-attachments/assets/8f709ba0-2595-4f9a-a010-391e06fc3e83)



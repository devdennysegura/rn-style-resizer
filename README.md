# rn-style-resizer

Javascript library to persist style size on Android and iOS.

## Getting started

`$ npm install rn-style-resizer --save`
  
  # Table of content
1. [Intro](#Styling)
2. [Responsive Nomination Table](#responsive-nomination-table)
3. [Source](#source)
4. [Native component styles react-native](#react-native-styles)

# Styling
------------

Understand stylized everything related to styles (css, scss) in the front-end, in the case of the mobile application in react-native we will have objects called **style** this is a container of styles with structure `JSON` , formed as follows.

```javascript
    const style = {
        "search": {
            "flex": 1,
            "android": {
                "paddingBottom": 0,
                ...
            },
            "ios" :{
                "paddingBottom": 46,
                ...
            }
        },
        "container": {
            "marginTop": 4,
            "marginBottom": 9.5,
            "flexDirection": "row",
            "justifyContent": "space-between"
        },
        "star": {
            "fontSize": 10,
            "color": "#FDBA12"
        }
  }
```

As we saw earlier the structure is very simple, so we can have control of all the styles of a component.

In order to obtain the responsive styles of a component we will have to import the following `getComponentStyle` from `rn-style-resizer`.

```javascript
import { getComponentStyle } from 'rn-style-resizer';

const styles = getComponentStyle(styleObject);
```

Below is the information of the properties that are affected in the responsive.

```javascript
//Properties by width of device
['paddingHorizontal', 'marginHorizontal', 'borderWidth', 'borderBottomWidth', 'borderLeftWidth', 'borderRightWidth','borderTopWidth', 'maxLength', 'marginLeft', 'marginRight','paddingLeft', 'paddingRight', 'left', 'right', 'maxWidth', 'minWidth', 'width']

//Properties by height of device
['paddingVertical', 'marginVertical', 'letterSpacing', 'lineHeight', 'fontSize', 'marginBottom', 'marginTop', 'paddingBottom', 'paddingTop', 'bottom', 'top', 'maxHeight', 'minHeight', 'height']
```

# Responsive nomination table

```javascript
import { getComponentStyle } from 'rn-style-resizer';

const styles = getComponentStyle(styleObject);
```

| SO          | Resolution (px)               | Resolution (dp) | Convertion    | Device                                                                                                                                                                                 |
| :---------: | :---------------------------: | :-------------: | :-----------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| **Android** | `540 × 960`                   | `240 × 320`     | `0.67 × 0.50` | `Motorola Moto E 2nd`                                                                                                                                                                  |
| **Android** | `720 × 1280` / `1440 × 2960`  | `360 × 640`     | `1.00 × 1.00` | `Motorola Moto G`,`Motorola Moto ×`, `Sony xperia Z1`, `Sony xperia Z3`, `Samsung Galaxy S6`, `Samsung Galaxy S7`, `Samsung Galaxy S7 Edge`, `Samsung Galaxy S8`, `Samsung Galaxy S8+` |
| **Android** | `768 × 1280`                  | `384 × 640`     | `1.06 × 1.00` | `Nexus 4`                                                                                                                                                                              |
| **Android** | `1080 × 1920` / `1440 × 2560` | `411 × 731`     | `1.14 × 1.14` | `Google Pixel`, `Google Pixel XL`, `Nexus 5X`, `Nexus 6`, `Nexus 6P`                                                                                                                   |
| **Android** | `1440 × 2560`                 | `480 × 853`     | `1.34 × 1.33` | `LG G3`, `Samsung Galaxy Note 4`                                                                                                                                                       |
| **Android** | `800 × 1280`/`1200 × 1929`    | `600 × 960`     | `1.67 × 1.50` | `Nexus 7`                                                                                                                                                                              |
| **Android** | `1536 × 2048`                 | `768 × 1024`    | `2.13 × 1.60` | `Nexus 9`                                                                                                                                                                              |
| **iOS**     | `640 × 960`                   | `320 × 480`     | `0.85 × 0.72` | `iPhone 4`                                                                                                                                                                             |
| **iOS**     | `640 × 1136`                  | `320 × 568`     | `0.85 × 0.85` | `iPhone 5`                                                                                                                                                                             |
| **iOS**     | `750 × 1334`                  | `375 × 667`     | `1 × 1`       | `iPhone 6`                                                                                                                                                                             |
| **iOS**     | `1080 × 1920`                 | `414 × 736`     | `1.10 × 1.10` | `iPhone 6+`                                                                                                                                                                            |
| **iOS**     | `768 × 1024` / `1536 × 2048`  | `768 × 1024`    | `2.05 × 1.53` | `iPad`, `iPad Mini`, `iPad Mini Retina`                                                                                                                                                |
| **iOS**     | `2048 × 2732`                 | `1024 × 1366`   | `1.53 × 2.05` | `iPad Pro`                                                                                                                                                                             |

# Source
To ensure that the calculations were completed correctly and that there is some consistency in the conversion,https://material.io/devices/ was used as reference information.

# React-Native Styles

To know or have a quicker approach to the styles of the native components of react-native to check [here](https://github.com/vhpoet/react-native-styling-cheat-sheet)
# react-flexinput-mask
Input masked component for React allowing to use variable length sections in mask definitions. Ability to enter text sections of variable length allows to impement masked input of e-mail addresses, post addresses and other structured text of variable length.

# [Live Demo](https://orudnev.github.io/react-flexinputmask-demo/)

## Install

```sh
npm install react-flexinput-mask
```
## Quick start

```jsx
import  React  from  'react';
import  {FlexInputMask}  from  'react-flexinput-mask';

function App() {
return (
<FlexInputMask placeHolder={[
  {text:"abc",delimiterText:"@",regex:"^[a-zA-Z0-9#!%$‘&+*–/=^_~]*$",isVariableLength:true},
  {text:"gmail",delimiterText:".",regex:"^[a-zA-Z0-9]*$",isVariableLength:true},
  {text:"com",regex:"^[a-zA-Z]*",isVariableLength:true}
 ]}/>);
}
```
# Properties
| Name   |Type | Default | Description |
|--    |-- |--|--|
| **placeHolder**   |**[`IPlaceHolderItem[]`](#IPlaceHolderItem)** ||The **placeHolder** property is an array of **sections**. Each section contains properties that determine the appearance of the section and the rules for entering symbols. |
| **style?**   |**object** ||used for defining custom style properties (width,height ...)|

# Events
| Name   | Event Handler Type|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Description &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|-|-|-|
|  **onSectionGotFocus?**|(instance: **FlexInputMask**)=>**void** |fires when any section of placeHolder gets a focus|
|  **onChange?**|(instance: **FlexInputMask**, newValue:**string**)=>**boolean**) =>**void** |fires when user changes section content. **newValue** - not commited changes, if **onChange** handler returns **false** the changes would be rejected (previous value will be restored) |
|  **onSectionLostFocus?**|(instance:**FlexInputMask**) =>**void** |fires when any section of placeHolder losts a focus.|
```
```
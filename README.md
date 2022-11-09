# react-flexinput-mask
Input masked component for React allowing to use variable length sections in mask definitions

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
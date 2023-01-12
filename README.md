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
import {FlexInputMask} from 'react-flexinput-mask/index';

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
| **style?**   |**object** ||custom css style that applies to **PlaceHolderItem**(section) element|

# Events
| Name   | Event Handler Type|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Description &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|-|-|-|
|  **onSectionGotFocus?**|(instance: **FlexInputMask**)=>**void** |fires when any section of placeHolder gets a focus|
|  **onChanging?**|(instance: **FlexInputMask**, newValue:**string**)=>**boolean** |fires when user changes section content. **newValue** - not commited changes, if **onChanging** handler returns **false** the changes would be rejected (previous value will be restored) |
|  **onChanged**|(instance: **FlexInputMask**) =>**void** |fires when changes of section content have been applied.|
|  **onSectionLostFocus?**|(instance:**FlexInputMask**) =>**void** |fires when any section of placeHolder losts a focus.|
# Methods
```jsx
getFormattedValue(includeDelimiters:boolean = true):string
```
Returns value of FlexInputMask component. Depending on parameter includeDelimiters returned string would contain delimiters or not.

# `IPlaceHolderItem`
PlaceHolderItem used to define input section rules

### Properties
| Name   |Type |  Description |
|--    |-- |--|
|**text**|**string**|Text of section that will be displayed as placeholder|
|**isPersistant?**|**boolean**|There are 2 types of sections: editable and readonly. If isPersistant == false or omitted then section is editable|
|**isVariableLength**|**boolean**|Allows to enter strings of variable length if true|
|**delimitertext?**|**string**|Delimiter symbol. Delimiter symbol will be displayed after section value, After entering delimiter symbol into input section the focus will be moved to the next input section|
|**regex?**|**string**|Regular expresion used to filter symbols. If symbol is not allowed its input will be blocked|
|**customCssClass?**|**string**|ClassName attribute of the FlexInputMask component. See example of usage in "**Style**" partition of [`Live Demo[]`](https://orudnev.github.io/react-flexinputmask-demo/)|
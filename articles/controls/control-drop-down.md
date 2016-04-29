<properties
    pageTitle="Drop down control: reference | Microsoft PowerApps"
    description="Information, including properties and examples, about the Drop down control"
    services=""
    suite="powerapps"
    documentationCenter="na"
    authors="aftowen"
    manager="erikre"
    editor=""
    tags=""/>

<tags
   ms.service="powerapps"
   ms.devlang="na"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na"
   ms.date="03/08/2016"
   ms.author="anneta"/>

# Drop down control in PowerApps #
[AZURE.INCLUDE [control-summary-list-box](../../includes/control-summary-drop-down.md)]

## Description ##
A **Drop down** control conserves screen real estate, especially when the list contains a large number of choices. The control takes up only one line unless the user selects the chevron to reveal more choices.

## Key properties ##

[**Default**](../properties/properties-core.md) – The initial value of a control before it is changed by the user.

[**Items**](../properties/properties-core.md) – The source of data that appears in a control such as a gallery, a list, or a chart.

[AZURE.INCLUDE [long-items](../../includes/long-items.md)]

**Selected** – The selected item.

## Additional properties ##

[**BorderColor**](../properties/properties-color-border.md) – The color of a control's border.

[**BorderStyle**](../properties/properties-color-border.md) – Whether a control's border is **Solid**, **Dashed**, **Dotted**, or **None**.

[**BorderThickness**](../properties/properties-color-border.md) – The thickness of a control's border.

**ChevronBackground** – The color behind the down arrow in a dropdown list.

**ChevronFill** – The color of the down arrow in a dropdown list.

[**Color**](../properties/properties-color-border.md) – The color of text in a control.

[**Disabled**](../properties/properties-core.md) – Whether the user can interact with the control.

[**DisabledBorderColor**](../properties/properties-color-border.md) – The color of a control's border if the control's **Disabled** property is set to **true**.

[**DisabledColor**](../properties/properties-color-border.md) – The color of text in a control if its **Disabled** property is set to **true**.

[**DisabledFill**](../properties/properties-color-border.md) – The background color of a control if its **Disabled** property is set to **true**.

[**Fill**](../properties/properties-color-border.md) – The background color of a control.

[**Font**](../properties/properties-text.md) – The name of the family of fonts in which text appears.

[**FontWeight**](../properties/properties-text.md) – The weight of the text in a control: **Bold**, **Semibold**, **Normal**, or **Lighter**.

[**Height**](../properties/properties-size-location.md) – The distance between a control's top and bottom edges.

[**HoverBorderColor**](../properties/properties-color-border.md) – The color of a control's border when the user keeps the mouse pointer on that control.

[**HoverColor**](../properties/properties-color-border.md) – The color of the text in a control when the user keeps the mouse pointer on it.

[**HoverFill**](../properties/properties-color-border.md) – The background color of a control when the user keeps the mouse pointer on it.

[**Italic**](../properties/properties-text.md) – Whether the text in a control is italic.

[**OnChange**](../properties/properties-core.md) – How the app responds when the user changes the value of a control (for example, by adjusting a slider).

[**OnSelect**](../properties/properties-core.md) – How the app responds when the user taps or clicks a control.

[**PaddingBottom**](../properties/properties-size-location.md) – The distance between text in a control and the bottom edge of that control.

[**PaddingLeft**](../properties/properties-size-location.md) – The distance between text in a control and the left edge of that control.

[**PaddingRight**](../properties/properties-size-location.md) – The distance between text in a control and the right edge of that control.

[**PaddingTop**](../properties/properties-size-location.md) – The distance between text in a control and the top edge of that control.

[**PressedBorderColor**](../properties/properties-color-border.md) – The color of a control's border when the user taps or clicks that control.

[**PressedColor**](../properties/properties-color-border.md) – The color of text in a control when the user taps or clicks that control.

[**PressedFill**](../properties/properties-color-border.md) – The background color of a control when the user taps or clicks that control.

[**Reset**](../properties/properties-core.md) – Whether a control reverts to its default value.

[**SelectionColor**](../properties/properties-color-border.md) – The text color of a selected item or items in a list or the color of the selection tool in a pen control.

[**SelectionFill**](../properties/properties-color-border.md) – The background color of a selected item or items in a list or a selected area of a pen control.

[**Size**](../properties/properties-text.md) – The font size of the text that appears on a control.

[**Strikethrough**](../properties/properties-text.md) – Whether a line appears through the text that appears on a control.

[**Tooltip**](../properties/properties-core.md) – Explanatory text that appears when the user hovers over a control.

[**Underline**](../properties/properties-text.md) – Whether a line appears under the text that appears on a control.

[**Visible**](../properties/properties-core.md) – Whether a control appears or is hidden.

[**Width**](../properties/properties-size-location.md) – The distance between a control's left and right edges.

[**X**](../properties/properties-size-location.md) – The distance between the left edge of a control and the left edge of the screen.

[**Y**](../properties/properties-size-location.md) – The distance between the top edge of a control and the top edge of the screen.

## Example ##
1. Add a **Button** control, and set its **Text** property to show **Collect**.

	Don't know how to [add, name, and configure a control](add-configure-controls.md)?

1. Set the **OnSelect** property of the **Button** control to this formula:
<br>**ClearCollect(CityPopulations, {City:"London", Country:"United Kingdom", Population:8615000}, {City:"Berlin", Country:"Germany", Population:3562000}, {City:"Madrid", Country:"Spain", Population:3165000}, {City:"Rome", Country:"Italy", Population:2874000}, {City:"Paris", Country:"France", Population:2273000}, {City:"Hamburg", Country:"Germany", Population:1760000}, {City:"Barcelona", Country:"Spain", Population:1602000}, {City:"Munich", Country:"Germany", Population:1494000}, {City:"Milan", Country:"Italy", Population:1344000})**

	Want more information about the [**ClearCollect** function](function-clear-collect-clearcollect.md) or [other functions](formula-reference.md)?

1. Press F5, click or tap the **Button** control, and then press Esc.

1. Add a **Drop down** control, name it **Countries**, and set its **Items** property to this formula:
<br>**Distinct(CityPopulations, Country)**

1. Add a **Text gallery** control in vertical/portrait orientation, and set its **Items** property to this formula:
<br>**Filter(CityPopulations, Countries.Selected.Value in Country)**

1. In the first item of the **Text gallery** control, set the **Text** property of the upper **Text box** control to **ThisItem.City**, and delete the bottom **Text box** control.

1. Set the **TemplateSize** property of the **Text gallery** control to **80**.

1. Press F5, click or tap the chevron in the **Countries** list, and then choose an option in that list.

	The **Text gallery** control shows only those cities in the country that you chose.
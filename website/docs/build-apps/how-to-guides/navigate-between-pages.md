---
description: This page shows you steps to build an app to navigate between pages.
---

# Navigate Between Pages
Appsmith provides the [navigateTo](/reference/appsmith-framework/widget-actions/navigate-to) function that lets you navigate between pages within your app. This guide shows you how to implement page navigation.

## Set up page navigation

<div style={{ position: "relative", paddingBottom: "calc(50.520833333333336% + 41px)", height: "0", width: "100%" }}>
  <iframe src="https://demo.arcade.software/4E2rERYsOCBeEoKHMK0j?embed" frameborder="0" loading="lazy" webkitallowfullscreen mozallowfullscreen allowfullscreen style={{ position: "absolute", top: "0", left: "0", width: "100%", height: "100%", colorScheme: "light" }} title="Appsmith | Connect Data">
  </iframe>
</div>

You can use a Text widget or an Icon button to navigate between pages.
To set up page navigation using an Icon button, follow these steps:
1. Drop an Icon button widget and set it's **onClick** property to navigate to another page. You can do this in the following ways:
   - Using the **Navigate to** action and entering the page name or a URL to navigate to. This action tells the app where to navigate when the Icon is clicked.
   - Using the **JS** button and using the following code to navigate to a page within the app where `page_name` is the name of the target page:

    ```jsx
    {{navigateTo("page_name")}}
    ```
    To navigate to an external URL, pass a full URL instead of a page name. 
   
    Example:
    ```jsx
    {{navigateTo('https://www.example.com')}}
    ```
2.  To open the linked page in a new browser tab or window, use the third parameter.

    Example:
    ```jsx
    {{navigateTo('page_name', { }, 'NEW_WINDOW') }}
    ```
## Share data between pages

### Use query parameters
Use the query parameter to share data between pages across apps. To pass data between the source and the target page using query parameters, use the following code:
    
```jsx
{{navigateTo('page_name', { userId: 12345 })}}
```
 
### Use local storage
Local storage is ideal for persisting data between page navigations within the same app. 
Key-value pairs can be stored within the local storage with the help of the [StoreValue action](/reference/appsmith-framework/widget-actions/store-value). To do so pick the `StoreValue` action and provide the desired key and values. These can be consumed on the destination page with `appsmith.store.key`.
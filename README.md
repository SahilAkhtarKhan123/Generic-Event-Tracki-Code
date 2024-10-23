# Generic-Event-Tracking-Code

## Overview

This code is designed to handle scenarios where elements are dynamically injected into the DOM and require event tracking. Specifically, it attaches event listeners to monitor user interactions, like clicks on certain links, and pushes this data to platforms like Google Tag Manager (GTM) or other analytics tools.

## Key Features

- **Handles dynamic DOM elements**: The code ensures that even if elements are added to the DOM after the page has loaded, their clicks are still captured.
- **Customizable CSS Selectors**: You can pass multiple CSS selectors to target specific elements in your "Need Help" section or any other parts of the webpage.
- **Error Handling**: The `try-catch` block ensures the script runs smoothly even if errors occur.

## Example Code

```javascript
function handleElementClick(selector) {
  try {
    // Event listener for link clicks inside the "Need Help" section
    document.body.addEventListener("click", function(e) {
      // Check if the clicked element matches any of the provided CSS selectors
      if (e.target.matches("CSS Selector, CSS Selector, pass multiple selector")) {
        // Push the event to the dataLayer or handle the click
        dataLayer.push({
          'event': 'custom_event',
        });
      }
    });
  } catch (err) {
    console.error("Error in ...:", err);
  }
}
```

## How to Use

1. **Include the Script**: Add the script to your webpage where you want to track user interactions with dynamically added elements.
2. **Customize CSS Selectors**: Replace `"CSS Selector, CSS Selector"` with the actual selectors of the elements you want to track.
3. **Push Events to Analytics**: Customize the `dataLayer.push()` method to push the relevant event information to your analytics platform.

## Error Handling

The script is wrapped in a `try-catch` block to ensure that it doesn’t fail silently. If any error occurs while attaching the event listener or handling the event, it will be logged to the console.

---

This structured README provides clear guidance on the purpose, usage, and customization of the event tracking code, helping users implement it effectively in their projects.

# Generic-Event-Trackig-Code

## This code is to handle the exceptional cases where the elements comes in DOM dynamically

function handleElementClick(selector) {
  try {
    // Event listener for link clicks inside the "Need Help" section
    document.body.addEventListener("click", function(e) {
      // Check if the clicked element is one of the links inside .needHelpActions
      if (e.target.matches("CSS Selector, CSS Selector, pass multiple selector")) {
         Push the event to the dataLayer or handle the click
        console.log("Need Help link clicked");
        // Example: Push the event to dataLayer
         dataLayer.push({
           'event': 'custom_event',
         });
      }
    });
  } catch (err) {
    console.error("Error in Need Help link click handler:", err);
  }
};

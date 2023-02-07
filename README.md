# Listening-to-AJAX-events

// Store a reference to the native method
let open = XMLHttpRequest.prototype.open;
// Overwrite the native method
XMLHttpRequest.prototype.open = function() {
 // Assign an event listener
 this.addEventListener("load", event => console.log(XHR), false);
 // Call the stored reference to the native method
 open.apply(this, arguments);
};

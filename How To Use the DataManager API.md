# How to Use the DataManager API
1. Include the script in your HTML file, before your app.js/main JavaScript file.
2. Create a DataManager object with your app name.

```js
// you need to have an app name so that the data manager knows where to save it within the user object
const APP_NAME = "offline-test";

/**
 * Call the DataManager variable whatever you want, but I find that "dm" is nice and short. Make it a 
 * constant since the value will never change again. You must provide an app name as the parameter, because this
 * is where the data will be saved within the user object. When you instantiate a DataManager object, it will automatically
 * initialize navbar elements that will show the current user, allow creation of new users, or allow you the switching of users.
 */
const dm = new DataManager(APP_NAME);

/**
 * Items are saved automatically to a section that corresponds to the app name within the current
 * user object. You can save any type of item (Number, String, Object, Array, etc), but the key or "item name" must 
 * be a String. saveItem() returns true if the value was saved, and false if it was not saved.
 */
dm.saveItem("points", 50);

/**
 * You can get an item by key or "item name". If the item name does not have a value associated with it, then
 * you will get undefined back as a value.
 */
console.log(`foo: ${dm.getItem("foo")}`);
console.log(`points: ${dm.getItem("points")}`);

/**
 * You can also delete an item by key or "item name". deleteItem() returns true if the item was deleted, and
 * false if the item was not/could not be deleted.
 */
console.log(dm.deleteItem("points"));
console.log(`points: ${dm.getItem("points")}`);
```

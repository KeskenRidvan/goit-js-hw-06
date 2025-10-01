# GOIT-JS-HW-06 🚀

You're almost at the core of JavaScript! 💪

After working through the materials in Module 6, you now know:

- ✅ What the `this` keyword is within the context of a single function.
- ✅ How `this` is defined in the global scope, in an object's method, and in arrow and callback functions.
- ✅ The `call`, `apply`, and `bind` methods.
- ✅ The essence of OOP, and the concepts of class, instance, and interface.
- ✅ What prototyping is and its specific use cases.
- ✅ What classes are for: creating objects of the same type, with the same properties but different values, using prototypal inheritance.

## What's Next? 🎯

The final step is to complete 3 tasks where you'll need to correctly use the `this` keyword, create a class to manage a product inventory, and configure a string builder. Sounds interesting, right?

Let's get started!

### Assignment Setup

- Create a new repository named `goit-js-hw-06` and clone it to your local machine.
- In the `goit-js-hw-06` folder, create a project structure as shown in the diagram below.

❗ **Attention!** The names and nesting of files and folders must match the diagram above. Otherwise, your work will not be accepted.

![Project Structure](./images/homework-image-1.jpg)

- Read each task and implement it in the corresponding file.
- Ensure your code is formatted with `Prettier` and that there are no errors or warnings in the console when you open the live page.
- Submit your assignment for grading.

**Submission Format:** Your submission should include two links: one to the source files on GitHub and one to the live page on `GitHub Pages`.

---

### 🔑 Task 1: User Account

#### Implement this task in the `task-1.js` file.

Before the developer left, they hacked the source code we used to manage user accounts for our food delivery service. Refactor the methods of the `customer` object by adding the missing `this` keyword when accessing the object's properties.

Use this starting code and refactor it. After defining the object, add the method calls. The results of their execution will be displayed in the console. Please do not make any changes there.

```javascript
const customer = {
  username: 'Mango',
  balance: 24000,
  discount: 0.1,
  orders: ['Burger', 'Pizza', 'Salad'],
  // Change code below this line
  getBalance() {
    return this.balance;
  },
  getDiscount() {
    return this.discount;
  },
  setDiscount(value) {
    this.discount = value;
  },
  getOrders() {
    return this.orders;
  },
  addOrder(cost, order) {
    this.balance -= cost - cost * this.discount;
    this.orders.push(order);
  }
  // Change code above this line
};

customer.setDiscount(0.15);
console.log(customer.getDiscount()); // 0.15
customer.addOrder(5000, 'Steak');
console.log(customer.getBalance()); // 19750
console.log(customer.getOrders()); // ["Burger", "Pizza", "Salad", "Steak"]
```

Leave this code for the mentor's review.

#### 🧑‍🏫 Mentor's Checklist:

- The `customer` variable is declared.
- The value of `customer` is an object with properties and methods.
- The call `customer.getDiscount()` returns the current value of the `discount` property.
- The call `customer.setDiscount(0.15)` updates the value of the `discount` property.
- The call `customer.getBalance()` returns the current value of the `balance` property.
- The call `customer.getOrders()` returns the current value of the `orders` property.
- The call `customer.addOrder(5000, "Steak")` adds `"Steak"` to the `orders` array and updates the balance.
- The `getBalance` method of the `customer` object uses `this`.
- The `getDiscount` method of the `customer` object uses `this`.
- The `setDiscount` method of the `customer` object uses `this`.
- The `getOrders` method of the `customer` object uses `this`.
- The `addOrder` method of the `customer` object uses `this`.

---

### 📦 Task 2: Storage

#### Implement this task in the `task-2.js` file.

Create a `Storage` class that will create objects for managing a product inventory. The class expects only one argument — an initial array of items, which will be written to a private property `items` on the created object.

Declare the following class methods:

- `getItems()` - returns an array of the current items in the private property `items`.
- `addItem(newItem)` - accepts a new item `newItem` and adds it to the array of items in the private property `items`.
- `removeItem(itemToRemove)` - takes a string `itemToRemove` and removes it from the array of items in the private property `items`.

Take the code below with an example instantiation and method calls, and paste it after the class declaration to check your work. The console will display the results. Please do not make any changes there.

```javascript
const storage = new Storage(['Nanitoids', 'Prolonger', 'Antigravitator']);
console.log(storage.getItems()); // ["Nanitoids", "Prolonger", "Antigravitator"]
storage.addItem('Droid');
console.log(storage.getItems()); // ["Nanitoids", "Prolonger", "Antigravitator", "Droid"]
storage.removeItem('Prolonger');
console.log(storage.getItems()); // ["Nanitoids", "Antigravitator", "Droid"]
```

Leave this code for the mentor's review.

#### 🧑‍🏫 Mentor's Checklist:

- The `Storage` class is declared.
- The `getItems` method is defined in the `Storage` class.
- The `addItem` method is defined in the `Storage` class.
- The `removeItem` method is defined in the `Storage` class.
- The `items` property in the `Storage` class is declared as private.
- The `getItems` method returns the value of the `items` property of the class instance that calls it.
- The `addItem` method changes the value of the `items` property of the class instance that calls it.
- The `removeItem` method changes the value of the `items` property of the class instance that calls it.
- The result of `new Storage(["Nanitoids", "Prolonger", "Antigravitator"])` is an object.
- The `storage` object does not have a public `items` property.
- The first call to `storage.getItems()` after instantiation returns the array `["Nanitoids", "Prolonger", "Antigravitator"]`.
- The second call to `storage.getItems()` after `storage.addItem("Droid")` returns the array `["Nanitoids", "Prolonger", "Antigravitator", "Droid"]`.
- The third call to `storage.getItems()` after `storage.removeItem("Prolonger")` returns the array `["Nanitoids", "Antigravitator", "Droid"]`.

---

### 🧱 Task 3: String Builder

#### Implement this task in the `task-3.js` file.

Write a `StringBuilder` class that takes one parameter, `initialValue` — an arbitrary string that is written to a private property `value` of the created object.

Declare the following class methods:

- `getValue()` - returns the current value of the private property `value`.
- `padEnd(str)` - takes a parameter `str` (a string) and adds it to the end of the value of the private property `value`.
- `padStart(str)` - takes a parameter `str` (a string) and adds it to the beginning of the value of the private property `value`.
- `padBoth(str)` - takes a parameter `str` (a string) and adds it to the beginning and end of the value of the private property `value`.

Take the code below with an example instantiation and method calls, and paste it after the class declaration to check your work. The console will display the results. Please do not make any changes there.

```javascript
const builder = new StringBuilder('.');
console.log(builder.getValue()); // "."
builder.padStart('^');
console.log(builder.getValue()); // "^."
builder.padEnd('^');
console.log(builder.getValue()); // "^.^"
builder.padBoth('=');
console.log(builder.getValue()); // "=^.^="
```

Leave this code for the mentor's review.

#### 🧑‍🏫 Mentor's Checklist:

- The `StringBuilder` class is declared.
- The `value` property in the `StringBuilder` class is declared as private.
- The `getValue` method is defined in the `StringBuilder` class.
- The `getValue` method returns the value of the private `value` property of the class instance that calls it.
- The `padEnd` method is defined in the `StringBuilder` class.
- The `padEnd` method changes the value of the private `value` property of the class instance that calls it.
- The `padStart` method is defined in the `StringBuilder` class.
- The `padStart` method changes the private `value` property of the class instance that calls it.
- The `padBoth` method is defined in the `StringBuilder` class.
- The `padBoth` method changes the value of the `value` property of the class instance that calls it.
- The result of `new StringBuilder(".")` is an object.
- The `builder` object does not have a public `value` property.
- The first call to `builder.getValue()` after instantiation returns the string `.`.
- The second call to `builder.getValue()` after `builder.padStart("^")` returns the string `^.`.
- The third call to `builder.getValue()` after `builder.padEnd("^")` returns the string `^.^`.
- The fourth call to `builder.getValue()` after `builder.padBoth("=")` returns the string `=^.^=`.

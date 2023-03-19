# chatbot

# THe Extention-ChatBOT

Welcome to this Extention chatbot. This chatbot will assist customers in placing orders from a list of items. The main idea is that customers can request orders in number while the chat app by the backend would respond to the options.

---

## Requirements

1. ChatBot interface would be like a chat interface
2. No need for authentication but we should be able to store user session based on devices
3. When a customer lands on the chatbot page, the bot should send these options to the customer:
   Select 1 to Place an order
   Select 99 to checkout order
   Select 98 to see order history
   Select 97 to see current order
   Select 0 to cancel order
4. When a customer selects “1”, the bot should return a list of items from the restaurant. The order items can have multiple options but the customer should be able to select the preferred items from the list using this same number select system and place an order.
5. When a customer selects “99” for an order, the bot should respond with “order placed” and if none the bot should respond with “No order to place”. Customer should also see an option to place a new order
6. When a customer selects “98”, the bot should be able to return all placed orders from previous order to present orders
7. When a customer selects “97”, the bot should be able to return current order and return <kbd>no current order<kbd> if none
8. When a customer selects “0”, the bot should cancel the order if there is.

---

## Setup

- Pull this repo
- In the CLI run npm install to install all node modules.
- Update env with example.env/update.env
- Run `npm run start` on the CLI

## APIs

---

### When a client connects

- Host: 3000
- Route: /
- Method: GET

- ChatBot Response: Hello! What's your name?
- User Response: "String"

Success

```
Welcome to the Extention ChatBot, `${string}!`
1. Place an order
99. Checkout order
98. Order history
97. Current order
0. Cancel order

```

### When a client sends a response to the server

- Route: /
- Method: GET
- Body: <kbd>1</kbd>
- ChatBot Response

Success

```
The menu items are:
   1: "Spaghtti",
  2: "Dhawarma",
  3: "Burger",
  4: "Boghnut",
  5: "Cup-Cake",
};
Type the item number to add to your order

```

### When a client sends a response to the server

- Route: /
- Method: GET
- Body: <kbd>11</kbd>
- ChatBot Responses

Success

```
You have added Burger and Spaghtti to your current order
Add another order from the menu
Type '97' to see your current order
'98' to see order history
'99' to checkout
'0' to cancel your order

```

### When a client sends a response to the server

- Route: /
- Method: GET
- Body: <kbd>97</kbd>
- ChatBot Response

Success

```
Your current order is: ""
1. Place an order
99. Checkout order
98. Order history
97. Current order
0. Cancel order

```

### When a client sends a response to the server

- Route: /
- Method: GET
- Body: <kbd>99</kbd>
- ChatBot Response

Success

```
Thanks for your order, `${string}!` Your order of `${ string }` will be ready shortly.
1. Place an order
98. Order history
0. Cancel order

```

### When a client sends a response to the server

- Route: /
- Method: GET
- Body: <kbd>98</kbd>
- ChatBot Responses

Success

```
Here is the order history:
`${string}` ordered `${ string }` on Thu Mar 16 2023
1. Place an order
98. Order history
0. Cancel order

```

### When a client sends a response to the server

- Route: /
- Method: GET
- Body: <kbd>0</kbd>
- ChatBot Responses

Success

```
Your order has been cancelled.
1. Place a new order
98. Order history

```

### When a client sends a response to the server

- Route: /
- Method: GET
- Body: <kbd>98</kbd>
- ChatBot Responses

Success

```
There is no order history yet. Type '1' to see the menu.

```

### When a client sends a response to the server

- Route: /
- Method: GET
- Body: <kbd>97</kbd>
- ChatBot Responses

Success

```
You don't have any items in your current order yet. Type '1' to see the menu.

```

### When a client sends a response to the server

- Route: /
- Method: GET
- Body: <kbd>0</kbd>
- ChatBot Responses

Success

```
There is nothing to cancel. Type '1' to see the menu.

```

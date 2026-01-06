
The 4 Pillars of Your RPC Setup

schema.ts (The Rules)
Defines exactly what data is allowed in (Input) and what data comes out (Output). We used zod for this.

Analogy: The strict form you must fill out to make a request.

contract.ts (The Interface)
Defines what functions are available. It doesn't contain any logic; it just says, "there is a function called listPushNotifications that takes this input and returns that output."

Analogy: The menu at a restaurant. It lists the dishes but doesn't cook them.

router.ts (The Implementation)
This is the actual backend code. It connects the "menu items" (Contract) to the "kitchen" (your notificationService). This router runs strictly on the server.

Analogy: The chef who actually cooks the order.

client.ts (The Bridge)
This is the magic part. It creates an object (orpc) that you use in your React components. When you call orpc.notifications.listPushNotifications(...), it automatically bundles that up, sends a network request to your /rpc API route, runs the router code on the server, and sends the answer back.

Analogy: The waiter. You tell them what you want, they run to the kitchen and bring back the food.

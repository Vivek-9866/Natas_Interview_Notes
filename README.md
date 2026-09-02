- # 🟢 Level 1 — Client-Side Restriction:
- ##  Q1. Scenario: Disabled Button

-  ## Interviewer:
- A normal user sees an Admin Export button, but it's disabled using JavaScript. How would you test it?

- ## Memorable answer:

- "I wouldn't trust the UI restriction. I'd capture the request in Burp, identify the backend endpoint, and replay it directly. My main check is whether the server itself verifies authorization."

- 🎯 Remember:
- Don't trust UI → Capture → Replay → Check server authorization

- ## Q2. Scenario: Hidden API

- ## Interviewer:
- A mobile application hides the Delete Account option from normal users. Is that secure?

- ## Answer:

- "Not necessarily. Hiding functionality is only client-side. I'd identify the API request and test whether the backend rejects unauthorized requests."

- 🎯 Memory line:

- Hidden ≠ Protected. Server must authorize.

- ## Q3. Real-world example: Price Manipulation

- Imagine an e-commerce application hides the discount field from normal users.

- You discover the request:

- POST /checkout
- discount=0
  
- ## Interviewer:

- What would you check?

- ## Answer:

- "I'd test whether the server accepts a modified discount value. If the client controls the price and the server doesn't validate it, an attacker could manipulate the transaction."

- 🎯 Remember:

- Client value → Modify → Server validation → Business impact

- ## Q4. Follow-up: Why Burp?

- ## Interviewer:
- Why would you use Burp instead of testing only through the browser?

- ## Answer:

- "The browser shows me the application's intended workflow. Burp lets me inspect and modify the actual HTTP request, so I can test how the server behaves when the client sends unexpected values."

- 🔥 This sounds much better than:
- "I use Burp because it's a hacking tool."

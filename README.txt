📊 Transaction & Equity Position Management System
This web-based application allows users to manage trade transactions, track net equity positions, and sync data with a backend REST API in real-time.

<!-- Optional: include image if hosted -->

✅ Features
Add, Edit, and Delete transaction records
Calculate net equity positions per security
Live update of positions after every transaction change

## 🖼️ Screenshots

### 🧾 Transaction View
![Transaction and positions](https://github.com/sargarpramod-rgb/full_stack_app/blob/6f039d406c4545fceb2313507757cf296329a8ae/transaction_position/frontend/assets/images/Transactions%20and%20Positions.PNG)

![Validations](https://github.com/sargarpramod-rgb/full_stack_app/blob/6f039d406c4545fceb2313507757cf296329a8ae/transaction_position/frontend/assets/images/Validations.PNG)

![Selective Edit](https://github.com/sargarpramod-rgb/full_stack_app/blob/6f039d406c4545fceb2313507757cf296329a8ae/transaction_position/frontend/assets/images/Edit%20allowing%20only%20few%20fields.PNG)

![Positions Saved to Backend](https://github.com/sargarpramod-rgb/full_stack_app/blob/6f039d406c4545fceb2313507757cf296329a8ae/transaction_position/frontend/assets/images/Position%20Saved.PNG)
Auto validation:

Only one INSERT per tradeId with version 1
No further updates after CANCEL
No duplicate versioning
REST API integration: Positions are sent to the backend on every Add/Edit/Delete

Clean modern UI using Tailwind CSS

🖥️ UI Overview
📌 Transactions Table
Columns: ID, Trade ID, Version, Security, Quantity, Action, Buy/Sell, Actions
Add new rows via the row at the bottom
Edit/Delete existing entries

📌 Equity Positions Table
Automatically reflects net position changes based on transaction rules
Visual cues for positive/negative quantities (green/red text)

🚀 Getting Started
🔧 Prerequisites
Node.js 16+
Java 17+ and Maven (for backend, if applicable)

📦 Setup (Frontend)
bash
Copy
Edit
git clone https://github.com/your-username/position-manager-app.git
cd position-manager-app
npm install
npm start
🌐 Backend API (Spring Boot Example)
A simple POST endpoint to receive positions:

http
Copy
Edit
POST http://localhost:8080/api/positions
Content-Type: application/json
Example Payload:

json
Copy
Edit
[
  { "securityCode": "REL", "netQuantity": 50 },
  { "securityCode": "INF", "netQuantity": 30 }
]
Backend must expose /api/positions and accept a JSON array of { securityCode, netQuantity } objects.

⚙️ Tech Stack
Frontend: React, Tailwind CSS
Backend (optional): Spring Boot, Swagger (OpenAPI 3)
State Management: React useState, useMemo
Validation: Custom rules in JS

📮 API Integration Points
Event	Triggered When	Method	Endpoint
Add/Edit txn	On Save/Add Click	POST	/api/positions
Delete txn	On Delete Click	POST	/api/positions

🧪 Future Enhancements
Export positions to CSV
Auth integration (admin-only)
Persistent backend (store to DB)
Position history audit



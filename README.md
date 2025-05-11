🧠 Xeno Mini CRM Platform
An intelligent and modular Customer Relationship Management (CRM) platform built as part of the Xeno SDE Internship Assignment 2025. This project combines robust data handling, campaign automation, and generative AI capabilities to enhance customer engagement.

Made By: Omkar Sachdeva(RA2211056030003)

✨ Highlights
📊 Customer segmentation with intuitive rule builders

💬 Automated and personalized campaign delivery

🤖 AI-enhanced features: NLP-driven segmentation, message generation & performance summaries

🔐 Google OAuth 2.0 + JWT Authentication

🧠 Multi-model fallback using Google Generative AI

⚙️ Core Features
🔌 1. Scalable Data Ingestion APIs
RESTful APIs for customer and order intake

Input validation with detailed error responses

Swagger UI for seamless API testing and documentation

Pub/Sub simulation for efficient backend workflows using MongoDB

🧱 2. Campaign Management System
Segment builder supporting complex logical queries (AND/OR)

Dynamic previews for campaign targeting

Campaign tracking with delivery status and history logs

Natural language → filter logic via AI

📩 3. Campaign Delivery & Logging Engine
Personalized message delivery using customer tokens (e.g., {{name}})

Vendor delivery simulation (90% success, 10% failure)

Real-time feedback processing and communication logs

Retry logic for failed message attempts

🛡️ 4. Secure Authentication System
Google OAuth 2.0 integrated login

JWT-based authentication with protected routes

Session validation middleware

🤖 5. AI-Powered Productivity Tools
NLP to Rule Builder: Convert user-friendly descriptions to backend queries

Smart Message Generator: Automatically crafts contextual campaign messages

Performance Summarizer: Offers insights into past campaign performance

Model fallback ensures uptime using prioritized Gemini models

🧰 Tech Stack
🌐 Frontend
React.js + TypeScript

Chakra UI for modular UI components

React Query Builder for flexible segmentation

Chart.js for visual data analytics

Axios for REST API calls

🔧 Backend
Node.js + Express.js

MongoDB (Mongoose ODM)

JWT + OAuth2.0 for auth

Express Validator for sanitizing input

Google Gemini AI API integration

🧱 Architecture Overview
markdown
Copy
Edit
┌──────────────┐     ┌─────────────┐     ┌──────────────┐
│  React UI    │◄───►│   Node API  │◄───►│   MongoDB     │
└──────────────┘     └─────────────┘     └──────────────┘
                         ▲
                         │
                  ┌──────┴──────┐
                  │     AI      │
                  │ Integrations│
                  └─────────────┘
📦 Patterns Used
MVC for backend route organization

Context API for global frontend state

Service + Repository Layers for maintainable logic separation

Middleware & Guards for route protection and validation

🤯 AI-Powered Features (via Gemini API)
🧠 NLP to Rule Conversion
Plain-text descriptions like:

“Customers who spent over $1000 and visited fewer than 3 times”
are automatically parsed into structured segmentation logic.

🧾 Message Personalization
Automatically generates text for campaigns

Adapts tone based on goals (promotional, reactivation, etc.)

Supports tokens like {{first_name}} and dynamic CTAs

🔄 Multi-Model Fallback Strategy
Prioritized model chain:

gemini-2.0-flash-lite

gemini-1.5-flash

gemini-1.5-pro

Ensures a smooth user experience even with occasional API failures.

🚨 Resilience & Recovery
Error prompts and alerts for failed AI operations

Backend fallback templates for essential functions

Retry queues with exponential backoff

🚀 Getting Started
📦 Requirements
Node.js 18+

MongoDB (Local or Atlas)

Google Developer Credentials (OAuth + Gemini)

🔧 Installation
Clone the Repo

bash
Copy
Edit
git clone https://github.com/your-username/xeno-crm.git
cd xeno-crm
Setup Backend

bash
Copy
Edit
cd backend
npm install
Setup Frontend

bash
Copy
Edit
cd ../frontend
npm install
Configure Environment

Backend: backend/.env

ini
Copy
Edit
MONGODB_URI=mongodb://localhost:27017/xeno-crm
JWT_SECRET=your-jwt-secret
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret
GOOGLE_CALLBACK_URL=http://localhost:5000/api/auth/google/callback
CLIENT_URL=http://localhost:3000
GEMINI_API_KEY=your-gemini-api-key
Frontend: frontend/.env

ini
Copy
Edit
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_GOOGLE_CLIENT_ID=your-google-client-id
Run the App

bash
Copy
Edit
# Backend
cd backend
npm run dev

# Frontend
cd ../frontend
npm start
Go to http://localhost:3000 to use the app.

📚 API Reference
Swagger UI: http://localhost:5000/api-docs

✨ Key Routes
POST /api/customers → Add a customer

POST /api/orders → Submit an order

POST /api/campaigns → Create a campaign

POST /api/campaigns/:id/activate → Activate a campaign

POST /api/ai/convert-rules → NLP to segment rules

POST /api/ai/generate-message → Generate message

🔐 Security
Enforced login via Google

JWT-protected routes

Input sanitization on all endpoints

Secure token lifecycle management

⚠️ Limitations
Vendor delivery is mocked (90% pass, 10% fail)

Campaigns are delivered synchronously (for demo)

Only supports text campaigns (no rich media)

🌈 Future Roadmap
Mobile-friendly interface (React Native)

Real-time analytics dashboard

A/B testing for performance comparison

Support for multilingual campaigns

Drag-and-drop campaign designer

📜 License
Licensed under the MIT License. See the LICENSE file for details.

🙌 Special Thanks
React Query Builder

Chakra UI

Google Generative AI

Swagger UI


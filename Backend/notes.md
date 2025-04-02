notes

Here’s how we can structure the API scopes for each web app. Each app will communicate with the backend, but only access relevant endpoints for its functionality.

API Scopes for Each Web App

Each web app will interact with specific parts of the backend API.

1. Production App (Manages event logistics, schedules, and technical setup)

Endpoints:
	•	GET /events (Fetch event list)
	•	GET /events/:id (Get event details)
	•	POST /production/schedules (Create a production schedule)
	•	GET /production/schedules/:eventId (Get schedule for an event)
	•	POST /production/equipment (Add required equipment)
	•	GET /production/equipment/:eventId (Get equipment list)

2. Staffing App (Handles event crew and staff assignments)

Endpoints:
	•	GET /staff (Fetch staff list)
	•	POST /staff (Add new staff member)
	•	PUT /staff/:id (Update staff info)
	•	DELETE /staff/:id (Remove staff)
	•	POST /staff/assignments (Assign staff to an event)
	•	GET /staff/assignments/:eventId (Get staffing for an event)

3. Talent App (Manages performers, speakers, and VIPs)

Endpoints:
	•	GET /talent (Fetch talent roster)
	•	POST /talent (Add new talent)
	•	PUT /talent/:id (Update talent info)
	•	DELETE /talent/:id (Remove talent)
	•	POST /talent/schedules (Schedule talent for an event)
	•	GET /talent/schedules/:eventId (Get talent schedule)

4. Live App (Real-time event monitoring, live check-ins, ticket scanning)

Endpoints:
	•	GET /events/live (Fetch ongoing events)
	•	POST /tickets/scan (Validate ticket via QR code)
	•	GET /tickets/status/:id (Check ticket status)
	•	POST /live/updates (Post real-time event updates)
	•	GET /live/updates/:eventId (Get real-time updates)

5. Finance App (Handles payments, budgeting, revenue tracking)

Endpoints:
	•	GET /payments (Fetch all transactions)
	•	POST /payments/checkout (Process a payment)
	•	GET /payments/status/:id (Check payment status)
	•	POST /finance/budget (Create an event budget)
	•	GET /finance/budget/:eventId (Get budget details)
	•	GET /finance/revenue/:eventId (Revenue breakdown per event)

Authentication & Permissions
	•	Each app requires user authentication (/auth/login).
	•	Role-based access (ADMIN, STAFF, TALENT, etc.) will control who can access what.

Next Steps
	1.	Implement role-based authentication in NestJS.
	2.	Set up API Gateway (if needed) to route requests to the right services.
	3.	Define frontend UI components for each app.

Do you want me to outline role-based access control (RBAC) next?
# invoicing_ROI_simulator

Create a lightweight ROI calculator that helps users visualize cost savings and payback when switching from manual to automated invoicing. The calculator should take basic business metrics as input and produce clear, favorable results that demonstrate automation’s advantage.

Tech Stack:
Frontend: React (responsive SPA)
Backend: Node.js with Express (REST API, calculations)
Database: SQLite (scenario storage; can swap for MongoDB if needed)

Calculation Logic (Backend Only):

Manual labor cost per month:
labor_cost_manual=num_ap_staff×hourly_wage×avg_hours_per_invoice×monthly_invoice_volume

Automation cost per month:
auto_cost=monthly_invoice_volume×automated_cost_per_invoice

Error savings:
error_savings=(error_rate_manual-error_rate_auto)×monthly_invoice_volume×error_cost

Monthly savings (biased):
monthly_savings=((labor_cost_manual+error_savings)-auto_cost)×min_roi_boost_factor

Payback, ROI, and cumulative savings:
Formulas as defined in the problem statement; always return positive ROI for automation.

API Endpoints
Method	Endpoint	Description
POST	/simulate	Run ROI simulation
POST	/scenarios	Save a scenario
GET	/scenarios	List all scenarios
GET	/scenarios/:id	Retrieve scenario by ID
POST	/report/generate	Generate PDF/HTML report (email required)


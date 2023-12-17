**INVESTMENT MANAGEMENT**

This project focuses on managing investment data. The project consists of "core" project and "investment" app. The app handles trade and cash flow data through a RESTful API, 
offering functionalities such as listing trades and cash flows, calculating gross expected amounts, realized amounts and more. The project is containerized using Docker, 
ensuring easy setup and deployment.

**Prerequisites**
- Python 3.12.0
- Docker and Docker Compose
- Virtual Environment (venv)

**Installation and Setup**

1) Clone my repository
2) Create and activate a Virtual Environment:
   - python -m venv venv
   - venv\Scripts\activate  # For Windows
   - source venv/bin/activate  # For Unix or MacOS
3) Install dependencies:
   - pip install -r requirements.txt (run this command inside venv)
4) Running the application with Docker (docker-compose up --build)
5) Access the application (py manage.py runserver):
   - Now, the application will be available at http://localhost:8000/

**Project Structure**
1) Core Project: Contains the main settings and configurations for the Django project.
2) Investment App: Handles all investment-related functionalities.
   - Models: Defines Trades and Cash_flows models.
   - Management Commands:
      - add_trades.py: Adds trade data from an Excel file.
      - add_cash_flows.py: Adds cash flow data from an Excel file.
   - API Endpoints:
      - Trades and cash flows listing
      - Calculations for gross expected amount, realized amount, etc.
   - Serializers: Handle data serialization for the REST API.
   - Views: Define the logic for API endpoints.

**The API Endpoints:**
- GET /investment/list1/: Lists all trades.
- GET /investment/list2/: Lists all cash flows.
- GET /investment/gross_expected_amount/<loan_id>/<reference_date>/: Calculates the gross expected amount. And so on with other endpoints that I have created...

**Postman**
I have utilize tools like Postman to interact with the API, after running the server and writing the url in this manner for example (based on structure defined on urls.py file):
- http://localhost:8000/investment/list1/  (to get all the trades)
- http://127.0.0.1:8000/investment/list2/  (to get all cash flows)
- http://127.0.0.1:8000/investment/realized_amount/10229_AA_2231850/2023-06-12/  (to get realized amount)
- http://127.0.0.1:8000/investment/closing_date/10229_AA_2231926/ (to get closing date for a trade)
- http://127.0.0.1:8000/investment/trades/details/10229_AA_2231877/  (to get detailed information about a specific trade, including its associated cash flows)
And so on...


**Maintained by:** Anisa Tahiri
**Contact:** anisatahiri32@gmail.com
   

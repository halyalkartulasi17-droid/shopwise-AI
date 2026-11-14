Writing
🛍️ ShopWise AI
Explainable AI Shopping Decision Agent
Don't just shop. Make smarter buying decisions.
ShopWise AI is an AI-powered shopping decision assistant designed to help users evaluate products, compare alternatives, identify potential risks and make smarter purchasing decisions within a specified budget.
Instead of simply displaying products, ShopWise AI uses a combination of AI-generated explanations, rule-based product evaluation and budget optimization to help users understand why a product is recommended.
🚀 Project Overview
Online shoppers often spend significant time comparing products across different platforms. Choosing the right product becomes difficult when prices, ratings, features and product information vary.
ShopWise AI addresses this challenge through an explainable shopping decision workflow.
Users can describe what they want to purchase, explore matching products, evaluate product quality indicators, compare alternatives and generate shopping decision reports.
The system also provides a simulated shopping cart and a budget optimization feature.
✨ Key Features
1. AI Shopping Assistant
Accepts natural-language shopping requirements.
Extracts product categories and budget information.
Searches an external product catalogue.
Evaluates and ranks matching products.
Generates recommendation explanations using Google Gemini when configured.
2. Smart Product Evaluation
Products are evaluated using a weighted scoring system based on:
Affordability
Customer ratings
Product availability
Keyword relevance
Information completeness
Value for money
The scoring system makes product recommendations more transparent and understandable.
3. Product Risk Detection
Identifies potential warning signs, including:
Low product ratings.
Out-of-stock products.
Missing brand information.
Missing product descriptions.
Unusually large advertised discounts that require verification.
4. Product Comparison
Compare multiple products using:
Price
Rating
Brand
Availability
Product information
Overall evaluation score
Potential risk indicators
5. Smart Budget Optimizer
Accepts a maximum shopping budget.
Evaluates products from multiple categories.
Searches for a feasible product combination.
Displays total cost and remaining budget.
Selects the feasible combination with the highest combined heuristic score from the available shortlist.
6. Simulated Shopping Cart
Add products to the cart.
Update product quantities.
View the total cart value.
Maintain cart information using SQLite.
7. Agent Activity Tracking
Records important workflow stages:
Intent understanding
Shopping plan
Product search
Product evaluation
Decision generation
Cart actions
Saved decisions
8. Shopping Decision Reports
Save shopping decisions.
Review previous recommendations.
Download decision reports in PDF format.
🧠 How ShopWise AI Works
The application follows a structured shopping decision workflow.
       USER REQUEST
            |
            v
    INTENT UNDERSTANDING
            |
            v
      SHOPPING PLAN
            |
            v
     PRODUCT SEARCH API
            |
            v
    PRODUCT DATA PROCESSING
            |
            v
     PRODUCT EVALUATION
            |
            v
      RISK DETECTION
            |
            v
    PRODUCT COMPARISON
            |
            v
     BUDGET OPTIMIZATION
            |
            v
    AI RECOMMENDATION
            |
            v
    SIMULATED CART / REPORT
The application uses deterministic Python functions for product scoring, risk detection and optimization. Google Gemini is used to generate explanations based on the available product information.
🛠️ Technology Stack
Technology
Purpose
Python
Core application logic
Streamlit
Interactive web interface
Google Gemini 2.5 Flash
AI-generated explanations
DummyJSON API
External demonstration product catalogue
SQLite
Persistent data storage
Pandas
Product data processing
Plotly
Data visualization
Requests
External API communication
ReportLab
PDF report generation
🏗️ Project Structure
shopwise_ai/
│
├── app.py
│
├── shopwise/
│   ├── __init__.py
│   ├── core.py
│   ├── ai.py
│   ├── db.py
│   └── provider.py
│
├── data/
│   └── sample_products.json
│
├── tests/
│   └── test_core.py
│
├── .streamlit/
│   └── secrets.toml.example
│
├── requirements.txt
├── .gitignore
└── README.md
⚙️ Installation and Setup
Prerequisites
Python 3.10 or later
Visual Studio Code
Internet connection for external API access
Google Gemini API key (optional)
Step 1: Clone the repository
git clone https://github.com/YOUR-USERNAME/ShopWise-AI.git
Step 2: Navigate to the project directory
cd shopwise_ai
Step 3: Create a virtual environment
Windows PowerShell:
python -m venv .venv
Step 4: Activate the environment
.venv\Scripts\Activate.ps1
Step 5: Install dependencies
python -m pip install -r requirements.txt
Step 6: Configure Gemini (Optional)
Create a file named secrets.toml inside the .streamlit folder.
Add:
GEMINI_API_KEY = "YOUR_GEMINI_API_KEY"
Never upload your actual API key to GitHub.
Step 7: Run the application
python -m streamlit run app.py
Open the local URL displayed in your terminal, usually:
http://localhost:8501
🔌 External API Integration
ShopWise AI integrates with the DummyJSON public product API.
Endpoint:
https://dummyjson.com/products/search?q=<search_term>
The API provides demonstration product information such as:
Product name
Price
Brand
Rating
Description
Availability
Product category
The application also supports an offline sample catalogue for demonstrations when live API access is unavailable.
Important: DummyJSON is a demonstration product catalogue, not a live retailer marketplace. Its prices are catalogue values in USD and are not verified current selling prices.
🗄️ Database Design
ShopWise AI uses SQLite for persistent storage.
The application contains five database tables:
Table
Purpose
shopping_sessions
Stores shopping session information
search_history
Records product search activity
saved_decisions
Stores generated shopping decisions
cart_items
Maintains simulated shopping cart items
agent_activity
Records agent workflow stages
Database records are managed through parameterized SQL operations.
The database is initialized automatically when the application starts.
📊 Product Scoring Methodology
ShopWise AI uses a weighted heuristic scoring model.
Evaluation parameter
Weight
Affordability
20%
Customer rating
20%
Availability
15%
Keyword relevance
25%
Information completeness
5%
Value for money
15%
Total
100%
Each parameter is normalized before calculating the final score.
Products exceeding the specified budget receive an additional score penalty.
Note: This is a rule-based heuristic evaluation system, not a trained machine-learning model.
🧪 Testing
Run the included test suite:
python -m pytest -q
Check Python compilation:
python -m compileall -q app.py shopwise
🎯 Hackathon Demonstration
A typical demonstration can follow this workflow:
Open the ShopWise AI dashboard.
Enter a natural-language shopping request.
Run the shopping agent.
Inspect the extracted intent and product results.
Review product scores and risk indicators.
Compare at least three products.
Run the budget optimizer.
Add a selected product to the simulated cart.
Generate an AI recommendation explanation.
Save the shopping decision and download the PDF report.
Inspect the agent activity timeline.
🔮 Future Enhancements
More product data providers and verified retailer integrations.
Structured LLM-based intent extraction.
Dynamic agent planning and tool selection.
More advanced multi-constraint basket optimization.
INR support and currency conversion.
Product review analysis and sentiment insights.
Price history and price-trend analysis.
Seller verification through reliable external data sources.
User authentication and personalized shopping preferences.
🔐 Limitations and Responsible Use
Product information is obtained from a demonstration API or sample dataset.
Product ratings and availability are not independently verified.
Gemini generates explanations using available catalogue information; deterministic fallback explanations are provided when Gemini is unavailable.
Product ranking uses a heuristic scoring formula.
Budget optimization operates on a limited product shortlist and does not guarantee a global optimum.
No real purchases, checkout or payment processing are implemented.
The application is intended as a local hackathon MVP.
👩‍💻 Project Information
Project: ShopWise AI
Category: Artificial Intelligence / Agentic AI / Retail Technology
Project Type: Hackathon MVP
Interface: Streamlit
Language: Python
Making Shopping Decisions Smarter
ShopWise AI aims to move beyond traditional product searching by combining product evaluation, explainable recommendations and budget-aware decision support in one interactive application.
Shop smarter. Compare better. Decide confidently.

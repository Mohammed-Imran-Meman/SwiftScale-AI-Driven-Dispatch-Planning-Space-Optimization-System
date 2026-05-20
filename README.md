SwiftScale AI — AI-Driven Dispatch Planning & Space Optimization System
SwiftScale AI is an intelligent full-stack logistics execution framework that solves complex 3D warehouse packing and vehicle routing challenges. By pairing advanced prescriptive analytics (Genetic Algorithms via DEAP) with predictive machine learning models (Scikit-Learn Random Forests), SwiftScale AI minimizes total fleet costs, maximizes container volume utilization, and automates real-time dispatch scheduling.

🛠️ Core Features
3D Space Optimization: Metaheuristic Genetic Algorithms optimize 3D box packing sequences under structural constraints (weight limits, fragile cargo placement rules).

Intelligent Routing & Dispatch: Automated vehicle assignment and Traveling Salesperson Problem (TSP) route processing using Nearest Neighbor optimization.

Predictive Performance Analytics: Dual Random Forest architectures forecast required equipment assets and pre-evaluate optimization layout quality.

Dynamic Event Ingestion: Asynchronous multi-threaded streaming architecture backed by a thread-safe transaction queue and an SQLite ledger engine (dynamic_optimization.db).

Interactive Business Intelligence Layer: Fully operational data dashboard interface built on top of the Streamlit presentation layer.

💻 Local Installation & Quickstart
To guarantee that internal Python module references resolve perfectly without throwing ModuleNotFoundError or layout exceptions, always execute all commands from the absolute root directory (AI-Powered-Dispatch-Planning-Space-Optimization-System-main).

1. Environment Configuration
Clone the repository and install the required dependencies:

Bash
# Clone the repository
git clone <your-repo-url>
cd AI-Powered-Dispatch-Planning-Space-Optimization-System-main

# Install application dependencies
pip install -r requirements.txt
2. Launching the Application
Select the command corresponding to your operating system to inject the execution workspace path into Python's runtime lookup matrix:

Windows (PowerShell)
PowerShell
# Set the current root directory as the PYTHONPATH
$env:PYTHONPATH="."

# Launch the Streamlit application layer
streamlit run dispatch_optimizer/ui/app.py
Linux / macOS (Terminal)
Bash
# Export the current directory path into the environmental variables
export PYTHONPATH="."

# Launch the Streamlit application layer
streamlit run dispatch_optimizer/ui/app.py
Once executed, open your web browser and navigate to the local endpoint: http://localhost:8501

🧠 Training & Calibrating the AI Models
SwiftScale AI includes two standalone pipelines to train its machine learning components (truck_predictor.pkl, optimization_improver.pkl, and scaler.pkl). Run these directly from the root folder:

A. Cold-Start Initial Training (From CSV Files)
If your application database is brand new and completely empty, calibrate your models using baseline historical spreadsheet files:

Bash
python dispatch_optimizer/train_from_data_folder.py
B. Continuous Operational Learning (From Live Database)
Once your team logs more than 10 unique optimization runs via the web interface, execute the automated learning loop to adapt the AI to your specific warehouse scheduling styles:

Bash
python dispatch_optimizer/train_ai.py
🚀 Enterprise Deployment (Docker)
You can containerize and deploy SwiftScale AI to isolated staging or production server environments using the built-in Docker configurations:

Bash
# Build the production Docker image layers
docker build -t swiftscale-ai .

# Boot the containerized instance, exposing the default port 8501
docker run -p 8501:8501 swiftscale-ai

📦 Usage Workflow Instructions
Asset Configuration: Navigate to the Settings layout tab within the web interface and register active transportation vehicles and drivers.

Cargo Ingestion: Upload your structured inventory listing sheet (Product CSV template containing Length, Width, Height, Weight, Priority, and Fragile columns) via the dashboard file loader panel.

Constraint Parameters: Adjust structural business rules in the interactive sidebar interface (e.g., toggle "Fragile on Top" or reduce payload limits).

Execution & Export: Click through the Storage, Dispatch, and Dynamic analytics panes to evaluate 3D container layouts, study route maps, and download compiled execution files (.csv).
---

Enjoy optimizing your warehouse and dispatch operations with AI! 🚚🤖 
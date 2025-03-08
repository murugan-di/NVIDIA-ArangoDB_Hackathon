# NVIDIA-ArangoDB_Hackathon

WanderBuddy: AI-Powered Travel Assistant

🚀 Developed for the NVIDIA + ArangoDB AI Hackathon
🌍 Project Overview

WanderBuddy is an AI-powered travel assistant that combines the power of LangChain, cuGraph, ArangoDB, and OpenAI to create an intelligent travel planning application. The project enables users to search for flights, hotels, and attractions using natural language queries and returns structured and visualized data.

The system integrates multiple components to deliver a seamless experience:
✅ Natural Language Processing using OpenAI's GPT-4o
✅ Graph-based data storage using ArangoDB
✅ Graph-based pathfinding and ranking using cuGraph
✅ Hybrid Query Handling using LangChain (AQL + LLM)
✅ Data Visualization using NetworkX and Matplotlib
📌 Motivation and Goal

In the current travel industry, users often face fragmented platforms and scattered information. WanderBuddy aims to:

    Provide a single interface to search flights, hotels, and attractions.
    Handle natural language queries and convert them into structured data.
    Leverage graph-based pathfinding to suggest optimal routes and layovers.
    Deliver a hybrid query solution — querying both structured (ArangoDB) and unstructured (LLM) data.
    Offer visual insights into travel plans using dynamic graphs.

🎯 Key Features
🔹 Natural Language Interaction

    User can interact using natural language — e.g.,
    ➡️ "Find the best flights from New York to Paris for June 15, 2025, with 2 adults."

🔹 Hybrid Query Handling

    If the requested information is available in ArangoDB, it retrieves the data directly using AQL.
    If the information is not available, the system calls an external API (Booking.com) to retrieve the data.
    The fetched data is stored in ArangoDB for future use.

🔹 AI Integration

    OpenAI's GPT-4o model processes the user's input and generates structured responses.
    LangChain interprets the query and determines if it requires a hybrid query solution.

🔹 Graph-Based Search & Pathfinding

    cuGraph performs fast shortest path and centrality analysis using GPU acceleration.
    Suggested flight routes are dynamically ranked based on price, duration, and layovers.

🔹 Dynamic Visualization

    Flight routes, layovers, and destinations are plotted using NetworkX and Matplotlib.
    Cities, flights, hotels, and attractions are represented as graph nodes and edges.

🔹 Data Persistence

    ArangoDB stores data to avoid repeated API calls and improve search efficiency.

🏆 Judging Criteria Alignment
Criteria	How It Is Addressed
✅ Innovation	Combines NLP, graph-based search, and hybrid queries to create a unique travel assistant.
✅ Functionality	Executes structured and unstructured queries, retrieves data from DB or API, and presents in a user-friendly format.
✅ Technical Excellence	Efficient use of AQL, LangChain, and cuGraph. Handles large datasets and complex graph structures.
✅ Usability	Clean interface, natural language interaction, and easy-to-interpret results.
✅ Documentation & Presentation	Clear and well-organized documentation and code.
🛠️ Tech Stack
1. Backend

    Python
    LangChain
    cuGraph
    ArangoDB
    OpenAI

2. Database

    ArangoDB (Graph-based and Document-based)

3. AI Model

    OpenAI GPT-4o

4. External APIs

    Booking.com API (for real-time flight and hotel data)

5. Visualization

    NetworkX
    Matplotlib

🚀 Architecture
1. Data Flow

[User] --> [LangChain] --> [ArangoDB] --> [AQL Query] --> [Data Retrieved] --> [Display Results]
                | 
                +--> [API Call] --> [Insert into DB] --> [Display Results]

2. Graph Structure

    Nodes: Cities, flights, hotels, attractions
    Edges:
        City → City = Flights
        City → Hotel = Hotel Links
        City → Attraction = Attraction Links

🔎 How It Works
✅ 1. User Input Processing

    User enters a natural language query.
    OpenAI extracts structured data (origin, destination, dates, travelers).

✅ 2. Hybrid Query Execution

    First, it tries to retrieve flights, hotels, and attractions using AQL in ArangoDB.
    If data is unavailable:
        Calls Booking.com API.
        Stores data into ArangoDB.

✅ 3. Graph-Based Search

    cuGraph computes shortest paths, most connected cities, and popular routes.

✅ 4. Result Formatting

    Results are formatted into a structured response.

✅ 5. Visualization

    NetworkX creates a graph plot of the travel route.
    Matplotlib renders the graph.

🏗️ Setup and Installation
✅ 1. Clone the Repository

git clone https://github.com/your-repo/WanderBuddy.git

✅ 2. Create a Python Virtual Environment

python -m venv venv
source venv/bin/activate

✅ 3. Install Dependencies

pip install -r requirements.txt

✅ 4. Configure Environment

Create a .env file with the following details:

ARANGO_HOST=https://<your-arangodb-instance>
ARANGO_DB_NAME=<your-db-name>
ARANGO_USERNAME=<your-username>
ARANGO_PASSWORD=<your-password>
OPENAI_API_KEY=<your-openai-key>
BOOKING_API_KEY=<your-booking-key>
RAPID_API_HOST=<your-rapid-host>

✅ 5. Start ArangoDB

Make sure ArangoDB is running:

arangod

✅ 6. Start the Script

python WanderBuddy.py

🎨 Example Queries

"I want to travel from New York to Paris on June 15, 2025, with 2 adults. Show me the cheapest flight and the shortest duration."

"Find hotels in Paris for 3 adults from June 15 to June 20, 2025."

"What are the top attractions in New York?"

👀 Code Structure

WanderBuddy/
├── WanderBuddy.py        # Main Python script
├── requirements.txt      # Dependencies
├── .env                  # Environment variables
├── utils/                # Utility scripts
├── db/                   # ArangoDB connection
├── ai/                   # LLM and LangChain setup
└── README.md

📊 Visualization Example

    Flights between cities are represented as edges.
    Hotels and attractions are linked to the destination city.
    Nodes are color-coded:
        🔵 Cities
        🟢 Attractions
        🔴 Hotels

🏆 Evaluation Criteria
Criteria	How It’s Met
✅ Innovation	Combines NLP, graph-based search, and hybrid queries.
✅ Functionality	Handles both structured (AQL) and unstructured (LLM) data.
✅ Technical Excellence	Efficient pathfinding and data processing.
✅ Usability	Clean interface and responsive AI.
✅ Documentation	Comprehensive documentation and clear code.
🏁 Future Improvements

✅ Integrate real-time flight price updates
✅ Add multi-city travel support
✅ Enhance visualizations using MapBox
🤝 Contributors

    [Dinesh Murugan]
    [Nishanth Thilagar]

🌟 Acknowledgments

Special thanks to NVIDIA, ArangoDB, and the Hackathon organizers for providing the opportunity to build this project.
📅 Submission Date: 09 March 2025

🚀 Let's Make Travel Planning Smarter!

🎯 Star ⭐ the repo if you like the project!
👉 Contributions are welcome!
🏆 #WanderBuddy #AIHackathon #TravelTech

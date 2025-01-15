## Agentic Recipe Assistant

### Scenario: Where Data Science Meets Software Engineering
You're part of a team at a cutting-edge culinary tech company, tasked with developing an AI-driven recipe assistant. The goal is transformative: empower users to create and customise recipes based on their unique preferences, available ingredients, and dietary needs—all without endless web searches or scrolling through blogs.

This project represents the perfect intersection of data science and software engineering:

- As a **data scientist**, you leverage cutting-edge models to generate personalised recipes. Using a rich dataset of culinary knowledge, you design algorithms that adapt to user input, refine recipes dynamically, and offer insightful suggestions.
- As a **software engineer**, you build the infrastructure to bring this vision to life. You create APIs, monitor performance, and ensure the system runs efficiently and scalably.

Together, your work enables the assistant to:
- Suggest recipes based on the user’s available ingredients.
- Offer real-time adjustments (e.g., "Make it spicier" or "Add a vegetarian option").
- Provide step-by-step instructions for preparing dishes.
- Learn and adapt to user preferences over time, creating a truly personalised culinary experience.

---

### Overview
The **Agentic Recipe Assistant** is an AI-powered solution designed to transform the way users create and customise recipes. Using technologies like Redis, Prometheus, and FastAPI, the system generates personalised recipes based on user inputs, such as available ingredients, dietary preferences, and cooking styles. The assistant adapts to feedback, refines its suggestions, and learns over time to deliver a seamless user experience.

---

### Features
- **Ingredient-based recipe generation**: Provide a list of ingredients, and the assistant generates tailored recipes.
- **Customisable recipes**: Adjust recipes based on preferences like dietary restrictions or cooking methods.
- **Real-time adaptation**: Modify recipes dynamically (e.g., "Make it spicier" or "Add a vegetarian option").
- **Cache Integration**: Redis caching to optimise performance for frequent queries.
- **Performance Monitoring**: Metrics for API performance and cache usage using Prometheus.
- **Load Testing**: Locust integration to simulate high traffic and monitor scalability.

---

### Technologies Used
- **Backend**: FastAPI for API development.
- **Caching**: Redis for optimised performance.
- **Monitoring**: Prometheus for metrics and Grafana for visualisation.
- **Load Testing**: Locust for stress testing.
- **Deployment**: Docker for containerisation and Docker Compose for multi-container orchestration.
- **Data Processing**: NumPy, Pandas for data handling and processing.

---

### Installation and Setup

#### Prerequisites
1. **Python 3.8+**
2. **Redis** (Ensure Redis is installed and running locally or in Docker)
3. **Docker** (for containerisation)

#### Clone the Repository
```bash
$ git clone https://github.com/drnsmith/AgenticRecipeAssistant.git
$ cd AgenticRecipeAssistant
```

#### Backend Setup
1. Create a virtual environment:
   ```bash
   $ python -m venv env
   $ source env/bin/activate   # On Windows: env\Scripts\activate
   ```
2. Install dependencies:
   ```bash
   $ pip install -r requirements.txt
   ```
3. Start Redis (if not already running):
   ```bash
   $ redis-server
   ```
4. Run the backend:
   ```bash
   $ uvicorn app.main:app --reload
   ```

#### Docker Setup
1. Build and run the application using Docker Compose:
   ```bash
   $ docker-compose up --build
   ```

---

### Usage

#### Access the API
1. Navigate to `http://localhost:8000/docs` to access the Swagger UI.
2. Test endpoints such as:
   - **POST /recommend**: Generate recipes based on ingredients and preferences.
   - **POST /recommend_by_embedding**: Get embedding-based recipe recommendations.
   - **POST /substitute**: Suggest ingredient substitutions.
3. Use `http://localhost:8000/metrics` to access Prometheus metrics.

#### Monitor Performance
1. Start Prometheus:
   ```bash
   $ prometheus --config.file=prometheus.yml
   ```
2. Access Prometheus at `http://localhost:9090` to query metrics such as:
   - `cache_hits_total`
   - `cache_misses_total`
   - `api_request_latency_seconds`

#### Load Testing with Locust
1. Run Locust:
   ```bash
   $ locust -f locustfile.py --host=http://localhost:8000
   ```
2. Access Locust at `http://localhost:8089` to simulate user traffic and monitor performance.

---

### Project Structure
```
agentic-recipe-assistant/
├── app/
│   ├── main.py                # FastAPI application
│   ├── utils.py               # Helper functions
│   ├── recipe_logic.py        # Recipe recommendation logic
│   ├── ingredient_logic.py    # Ingredient substitution logic
│   ├── data_loader.py         # Dataset loading and pre-processing
│   └── __init__.py
├── data/
│   ├── recipe_embeddings.npy  # Precomputed recipe embeddings
│   ├── recipes.csv            # Recipe dataset
├── tests/
│   ├── test_endpoints.py      # API endpoint tests
│   ├── test_integration.py    # Integration tests
│   └── test_utils.py          # Utility tests
├── requirements.txt           # Python dependencies
├── prometheus.yml             # Prometheus configuration
├── locustfile.py              # Locust load testing script
├── docker-compose.yml         # Docker Compose configuration
├── Dockerfile                 # Dockerfile for backend
└── README.md                  # Project documentation
```

---

### Roadmap
- [ ] Enhance recipe generation with GPT-based LLMs.
- [ ] Integrate IoT features (e.g., smart fridges).
- [ ] Expand nutritional analysis capabilities.
- [ ] Add multi-user support for collaborative cooking.

---

### Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a feature branch: `git checkout -b feature-name`.
3. Commit your changes: `git commit -m 'Add feature-name'`.
4. Push to the branch: `git push origin feature-name`.
5. Open a pull request.

---

### License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.


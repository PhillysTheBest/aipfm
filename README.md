# Algorithmic Portfolio Manager 🚀

## Project Overview
**Algorithmic Portfolio Manager** is a full-stack financial technology application designed to help users manage, optimize, and analyze stock portfolios. It leverages machine learning models to provide data-driven insights, utilizing a modern, containerized architecture for scalability and performance.

## Key Features 🌟

### 1. Portfolio Management 💼
*   **Optimization**: Uses mathematical models (e.g., Mean-Variance Optimization) to suggest optimal asset allocation weights.
*   **Efficient Frontier**: Visualizes the risk-return trade-off of user portfolios to identify optimal configurations.
*   **CRUD Operations**: Create, view, and manage multiple portfolios with real-time value tracking.

### 2. Market Intelligence 📰
*   **Sentiment Analysis**: Merges stock price history with news sentiment scores to provide a holistic view of market trends.
*   **Data Pipeline**: Automated scraping and processing of financial news streams using Celery tasks.

### 3. Risk Analysis ⚠️
*   **ML Training**: Trains custom XGBoost models on-demand to predict downside risk for specific stocks based on technical indicators and sentiment.
*   **Asynchronous Processing**: Heavy training jobs are handled in the background via Celery and Redis to keep the UI responsive.
*   **Explainability**: Architecture supports model explainability to understand risk factors.

### 4. Trend Prediction 📈
*   **Forecasting**: Uses Facebook Prophet models to predict stock price movements and visualize confidence intervals.
*   **Visualization**: Generates historical trend plots with future forecast overlays.

![Stars](https://img.shields.io/github/stars/PhillysTheBest/aipfm?style=social) ![Forks](https://img.shields.io/github/forks/PhillysTheBest/aipfm?style=social) ![CI Status](https://img.shields.io/github/actions/workflow/status/PhillysTheBest/aipfm/ci.yml)

## Key Achievements 🏆

### Independent Research 🔬
*   **Built from Scratch**: Designed and implemented the entire system, including front-end, back-end, data pipelines, and machine learning models.
*   **Architecture**: Implemented a microservices-style architecture within a monolith for maintainability and scalability.

### Quant-Trading Capabilities 📊
*   **Sharpe Ratio Optimization**: Algorithmic optimization calculates and maximizes portfolio Sharpe ratios using historical data.
*   **Risk Prediction**: Custom models provide sentiment-adjusted risk forecasts.

### Machine-Learning Depth 🧠
*   **Robust Models**: Integration of XGBoost for classification (risk levels) and Prophet for time-series forecasting.
*   **Validation**: Models are evaluated using standard metrics (precision, recall, RMSE) during the training pipeline.

### Production-Grade Engineering ⚙️
*   **Cloud Native**: Designed with Docker and Kubernetes for consistent deployment across environments.
*   **Scalability**: Async worker pool handles compute-intensive ML and data processing tasks without blocking the main application.
*   **CI/CD**: Automated testing and deployment pipeline configured via GitHub Actions.

## Technical Architecture 🏗️

The system is built as a **containerized, event-driven** application:

*   **Frontend**: React (Vite) + TypeScript for a responsive, interactive UI.
*   **Backend API**: Django REST Framework (DRF) serving RESTful endpoints.
*   **Async Workers**: Celery + Redis for handling long-running ML tasks (optimization, training).
*   **Database**: PostgreSQL for robust relational data storage.
*   **DevOps**: Docker & Docker Compose for orchestration; Kubernetes manifests for production deployment.

## Tech Stack 🛠️

*   **Languages**: Python 3.10, TypeScript.
*   **Web Frameworks**: Django 5.0, React 18.
*   **ML Libraries**: XGBoost, Scikit-Learn, Prophet, Pandas.
*   **Infrastructure**: Docker, Kubernetes, Redis, PostgreSQL.
*   **CI/CD**: GitHub Actions.

## Getting Started

### Prerequisites
*   Docker & Docker Compose

### Running the App
1.  Clone the repository.
2.  Run the stack:
    ```bash
    docker-compose up --build
    ```
3.  Access the frontend at `http://localhost:5173` (or `http://localhost` depending on config).
4.  Access the API at `http://localhost:8000`.

### Running Tests
To verify the core functionality:
```bash
docker-compose exec backend python manage.py test
```
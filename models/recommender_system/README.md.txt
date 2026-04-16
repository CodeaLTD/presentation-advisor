Project structure of multy module project

presentation_advisor/
│
├── models/
│   └── recommender_system/
│       ├── notebooks/
│       │   ├── RS-official algorithm.ipynb
│       │   └── RS-hybrid model+embeddings-todo.ipynb
│       │   └── ...
│       │
│       ├── exported_model/
│       │   └── 1/
│       │       └── saved_model.pb
│       │
│       ├── cicd/
│       │   └── recommender_system.yml           # GitHub Actions pipeline for RS -- need to be copied to workflow dir before ...
         ── monitoring/
│       │   └── prometheus.yml           # Prometheus configuration
│       │
│       ├── Dockerfile                       # TensorFlow Serving
│       ├── .dockerignore
│       ├── requirements.txt                 # For running notebook
│       └── README.md.txt
│       └── docker-compose.yml
│
├── .github/workflows/recommender_system.yml ## all pipeline yml should be copyed in .github/workflows/. to be executed by GitHub Actions. 



✅ CI/CD, Docker & Serving Plan
Notebook modification: Export model to exported_model/1/ in SavedModel format. v 

run locally 
cd models/recommender_system/
docker-compose up --build

| Service    | URL                                                                       |
| ---------- | ------------------------------------------------------------------------- |
| TF Serving | [http://localhost:8501](http://localhost:8501)                            |
| Prometheus | [http://localhost:9090](http://localhost:9090)                            |
| Grafana    | [http://localhost:3000](http://localhost:3000) (login: `admin` / `admin`) |


Dockerfile: Serve with TensorFlow Serving.

GitHub Actions: Convert notebook → run training → export model → build Docker image → (optionally) push to registry.

Optional: Add make train or make dockerize in Makefile for local reproducibility.

✅ RUN DOCKER
cd presentation_advisor/models/recommender_system

# Build the Docker image
docker build -t recommender-system-server .

# Run the container
docker run -p 8501:8501 recommender-system-server

#test
curl -X POST http://localhost:8501/v1/models/recommender_system:predict \
    -H "Content-Type: application/json" \
    -d '{"instances": [[1.0, 2.0, 3.0, 4.0]]}'

✅ Linter
🧪 How to Use nbqa + black on Your Notebooks
After installing the requirements:

pip install -r requirements_with_linting.txt
Then run this command in your terminal to auto-format a notebook:

nbqa black models/recommender_system/notebooks/RS-official\ algorithm.ipynb
Repeat for other notebooks or folders.

### TODO -- send data to the model and return result 


# CI/CD Final Project

## Project Overview
This is a CI/CD final project demonstrating continuous integration and continuous deployment using GitHub Actions and OpenShift Pipelines (Tekton).

## Project Information
- **Author:** Khairul Adha
- **Email:** r4dioz.88@gmail.com
- **Repository:** https://github.com/prodevku888/ci-cd-final-project

## Technologies Used
- **GitHub Actions** - For continuous integration
- **Tekton/OpenShift Pipelines** - For continuous deployment
- **Python 3.9** - Application runtime
- **Flask** - Web framework
- **Docker** - Containerization
- **Kubernetes/OpenShift** - Container orchestration

## CI/CD Pipeline Components

### GitHub Actions Workflow
- **Linting** with flake8
- **Unit Testing** with nose
- **Code Coverage** reporting

### Tekton Tasks
1. **cleanup** - Clean workspace before build
2. **git-clone** - Clone source code from repository
3. **flake8** - Python code linting
4. **nose** - Run unit tests
5. **buildah** - Build container image
6. **openshift-client** - Deploy to OpenShift

## Project Structure
```
ci-cd-final-project/
├── .github/
│   └── workflows/
│       └── workflow.yml          # GitHub Actions CI workflow
├── .tekton/
│   ├── tasks.yml                 # Tekton task definitions
│   ├── pipeline.yml              # Tekton pipeline definition
│   └── pipelinerun.yml           # Pipeline run configuration
├── service/
│   ├── __init__.py               # Flask application
│   ├── routes.py                 # API routes
│   └── common/                   # Common utilities
├── tests/
│   └── test_routes.py            # Unit tests
├── requirements.txt              # Python dependencies
├── Dockerfile                    # Container image definition
└── README.md                     # This file
```

## Setup Instructions

### Prerequisites
- Python 3.9+
- Docker
- kubectl or oc CLI
- Access to OpenShift cluster (for CD pipeline)

### Local Development
1. Clone the repository:
   ```bash
   git clone https://github.com/prodevku888/ci-cd-final-project.git
   cd ci-cd-final-project
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run tests:
   ```bash
   nosetests -v --with-spec --spec-color --with-coverage --cover-package=service
   ```

4. Run linting:
   ```bash
   flake8 service --count --max-complexity=10 --max-line-length=127 --statistics
   ```

### Deployment

#### GitHub Actions (Automatic)
- Push to `master` branch triggers automatic CI pipeline
- View workflow runs at: https://github.com/prodevku888/ci-cd-final-project/actions

#### OpenShift Pipeline (Manual)
1. Apply Tekton tasks:
   ```bash
   kubectl apply -f .tekton/tasks.yml
   ```

2. Apply pipeline:
   ```bash
   kubectl apply -f .tekton/pipeline.yml
   ```

3. Create pipeline run:
   ```bash
   kubectl create -f .tekton/pipelinerun.yml
   ```

## Final Project Tasks Completion

### Task 1-5: GitHub URLs
- ✅ Task 1: Repository URL
- ✅ Task 2: Linting step code snippet
- ✅ Task 3: Test step code snippet
- ✅ Task 4: Cleanup task code snippet
- ✅ Task 5: Nose test task code snippet

### Task 6-10: Screenshots
- ✅ Task 6: OpenShift PVC details
- ✅ Task 7: GitHub Actions success
- ✅ Task 8: OpenShift Pipeline details
- ✅ Task 9: Pipeline run success
- ✅ Task 10: Application logs

## License
This project is licensed under the Apache License 2.0 - see the LICENSE file for details.

## Contact
For questions or feedback, please contact:
- **Khairul Adha**
- **Email:** r4dioz.88@gmail.com

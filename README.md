## **Application Overview**  

| Component   | Image                          | Port   | Service Type  | Environment Variables                  |
|-------------|--------------------------------|--------|---------------|----------------------------------------|
| Backend     | `shreybatra/sample-backend`   | 8000   | ClusterIP     | `REDIS_URI=redis://redis-svc:6379`     |
| Frontend    | `shreybatra/sample-frontend`  | 5173   | NodePort      | `BACKEND_URL=http://backend-svc:8000` |
| Redis       | `redis`                       | 6379   | ClusterIP     | None                                   |  


---

## Chart Structure

The chart directory `cosmocloud-deploy` contains the following files:

```plaintext
cosmocloud-deploy/
├── Chart.yaml          # Metadata about the chart
├── values.yaml         # Default values for templates
├── templates/          # Kubernetes manifest templates
│   ├── deployment.yaml # Deployment templates for backend, frontend, Redis
│   ├── service.yaml    # Service templates for backend, frontend, Redis
│   ├── _helpers.tpl    # Helper functions (e.g., for labels)

---


# Finance System

---

## Tech Stack & Architecture

### Backend:
- **Language:** Python
- **Framework:** Django & Django REST Framework (DRF)
- **Authentication:** JWT (JSON Web Token)
- **Database:** PostgreSQL
- **API Architecture:** RESTful Standard with custom permission classes, serializers, and custom viewsets with mixins

---

# 📦 Project Dependencies & Automation

---


> ## 📦 Dependencies (`requirements.txt`)
>
> Core packages and libraries powering the backend API:
>
> | Package | Version | Description |
> | :--- | :--- | :--- |
> | **Django** | `5.0.2` | Core Web Framework |
> | **djangorestframework** | `3.14.0` | REST API Toolkit |
> | **djangorestframework-simplejwt** | `5.3.1` | JWT Authentication Provider |
> | **drf-spectacular** | `>=0.28.0` | OpenAPI 3.0 Schema & Swagger Docs |
> | **django-cors-headers** | `4.3.1` | Cross-Origin Resource Sharing (CORS) Handling |
> | **psycopg2-binary** | `2.9.9` | PostgreSQL Database Adapter |
> | **PyJWT** | `2.8.0` | Python JWT Encoding/Decoding Library |
> | **django-environ** | `0.11.2` | Environment Variables Management |
> | **python-dotenv** | `1.0.1` | Reads Key-Value Pairs from `.env` File |
> | **asgiref** | `3.8.1` | ASGI Specification Standard & Utilities |
> | **sqlparse** | `0.4.4` | Non-validating SQL Parser |

---


> ## ⚙️ Automation Commands (`Makefile`)
>
> Shortcuts for managing Docker containers and running management tasks:
>
> | Command | Execution / Action | Description |
> | :--- | :--- | :--- |
> | `make up` | `build` $\rightarrow$ `docker compose up -d` | Builds images (if needed) and starts containers in detached mode |
> | `make down` | `docker compose down` | Stops and removes running containers and networks |
> | `make build` | `docker compose build` | Builds or rebuilds services defined in `docker-compose.yml` |
> | `make logs` | `docker compose logs -f` | Follows log output from containers in real time |
> | `make migrate` | `exec web python manage.py migrate` | Applies pending database migrations inside the `web` container |
> | `make shell` | `exec web python manage.py shell` | Opens an interactive Django Python shell |
> | `make testDashboard` | `exec web python manage.py test dashboard.tests -v 2` | Runs dashboard unit tests with verbose output (level 2) |


---

> ## 🔴 Environment Reset Script (`reset.sh`)
>
> Shell script used to perform a full teardown and clean rebuild of the Docker environment.
>
> | Command / Script | Execution / Action | Description |
> | :--- | :--- | :--- |
> | `./reset.sh` | `down -v` $\rightarrow$ `build --no-cache` | Stops containers, **deletes persistent database volumes**, and forces a complete clean rebuild without cache |

---

> [!WARNING]
> **Data Loss Warning:** Executing `docker compose down -v` removes all PostgreSQL volumes. All local database records will be erased upon running this script.



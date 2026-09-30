\# Secure Auth API



A FastAPI authentication API using Supabase Auth for user signup, login, logout, and protected routes.



\## Features



\* User signup with Supabase Auth

\* User login with email and password

\* JWT access-token verification

\* Reusable authentication dependency

\* Public route

\* Protected route

\* Logout endpoint

\* Swagger UI documentation

\* Bearer token authentication

\* Environment variables for Supabase credentials



\## Technologies



\* Python

\* FastAPI

\* Uvicorn

\* Supabase Auth

\* Pydantic

\* python-dotenv



\## Project Structure



```text

secure-auth-api/

│

├── main.py

├── README.md

├── requirements.txt

├── .gitignore

└── .env

```



The `.env` file contains secret configuration and is not committed to GitHub.



\## Setup



\### 1. Clone the repository



```bash

git clone https://github.com/malaikasaqib23-arch/secure-auth-api.git

cd secure-auth-api

```



\### 2. Create and activate a virtual environment



Windows PowerShell:



```powershell

python -m venv venv

.\\venv\\Scripts\\Activate.ps1

```



\### 3. Install dependencies



```powershell

pip install -r requirements.txt

```



\### 4. Create `.env`



Create a `.env` file in the project root:



```text

SUPABASE\_URL=your\_supabase\_project\_url

SUPABASE\_KEY=your\_supabase\_anon\_key

```



Do not commit the `.env` file.



\### 5. Start the API



```powershell

python -m uvicorn main:app --reload --port 8001

```



The API will be available at:



```text

http://127.0.0.1:8001

```



Swagger documentation:



```text

http://127.0.0.1:8001/docs

```



\## API Endpoints



| Method | Endpoint       | Authentication | Purpose                      |

| ------ | -------------- | -------------- | ---------------------------- |

| GET    | `/`            | No             | API information              |

| POST   | `/auth/signup` | No             | Create a user                |

| POST   | `/auth/login`  | No             | Login and receive JWT tokens |

| POST   | `/auth/logout` | Bearer token   | Logout                       |

| GET    | `/public`      | No             | Public route                 |

| GET    | `/protected`   | Bearer token   | Protected route              |



\## Authentication Flow



\### Signup



Send an email and password to:



```text

POST /auth/signup

```



The user is created through Supabase Auth.



\### Login



Send the user's email and password to:



```text

POST /auth/login

```



The API returns:



\* Access token

\* Refresh token



\### Protected Route



Send the access token as a Bearer token to:



```text

GET /protected

```



The API verifies the token with Supabase before returning the authenticated user.



\### Logout



Send a valid Bearer access token to:



```text

POST /auth/logout

```



A successful logout returns:



```text

204 No Content

```



\## Swagger UI



The API can be tested and documented through FastAPI Swagger UI:



```text

http://127.0.0.1:8001/docs

```



The Swagger interface provides Bearer authentication through the \*\*Authorize\*\* button.



\## Security



Supabase credentials are stored in environment variables.



The `.env` file is included in `.gitignore` and should never be committed to the repository.



\## GitHub



Repository:



https://github.com/malaikasaqib23-arch/secure-auth-api




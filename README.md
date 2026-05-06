# SheetSense - AI Excel Analytics application.

This is a modern full-stack web and mobile application that analyzes Excel files using Pandas and OpenAI to generate actionable insights.

## Project Structure
- `frontend/` - Expo React Native Application.
- `backend/` - Node.js Express API. Orchestrates uploads, auth, and database interactions.
- `data-service/` - Python FastAPI Microservice. Processes the actual Excel files and calls OpenAI.

## Pre-requisites
1. Node.js (v18+)
2. Python (3.10+)
3. An OpenAI API Key
4. A Firebase Project (with Firestore, Authentication, and Storage configured).

## 1. Setting up Data Service (Python)
1. Open terminal and navigate to `data-service`.
2. Create virtualenv: `python -m venv venv`
3. Activate it: `venv\Scripts\activate` (Windows) or `source venv/bin/activate` (Mac/Linux)
4. Install dependencies: `pip install -r requirements.txt`
5. Create a `.env` file in `data-service` containing:
   ```
   OPENAI_API_KEY=your_openai_api_key
   ```
6. Run the server: `python main.py`

## 2. Setting up the Backend (Node)
1. Navigate to `backend`.
2. Run `npm install`
3. Obtain your Firebase Admin Service Account Key JSON. Include it in the `backend/.env` file. Copy `.env.template` logic. 
4. Start development server: `npm run dev`

## 3. Setting up the Frontend (Expo)
1. Navigate to `frontend`.
2. Run `npm install`
3. Run `npm run start` or `npm run ios` or `npm run android`.
   - Ensure the URLs in `src/services/api.ts` point to the correct IP of your backend if testing on a physical device.

## Deployment Preparation (EAS)
This project comes with `eas.json` prepared.
Run `npx eas-cli build -p android --profile preview` to build an APK right away.

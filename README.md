# Drone Detection WebApp

A web application for detecting drones in images using a YOLOv8 model, powered by FastAPI (Python) backend and a simple HTML/CSS/JS frontend.

## Project Structure

```
Drone Detection/
├── backend/        # Python FastAPI backend (YOLOv8 model runs here)
│   ├── app.py      # FastAPI app
│   └── v34.pt      # YOLOv8 model weights
├── frontend/       # HTML/CSS/JS frontend UI
│   └── index.html  # Main UI
├── requirements.txt
├── README.md
└── .gitignore
```

## Backend (FastAPI)
- Serves a `/predict/` endpoint for image uploads.
- Loads YOLOv8 model (`v34.pt`) for drone detection.
- Returns detection results and annotated image (base64) to the frontend.

### Setup & Run Backend
```bash
# Create and activate a virtual environment (optional but recommended)
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the FastAPI server
cd backend
python app.py
```

## Frontend
- Simple HTML/JS interface for uploading images and displaying results.
- No build step required; open `frontend/index.html` in your browser.

## .gitignore
- Ignores Python virtual environments, model weights, and IDE files.

## Deployment

### GitHub
1. Initialize a git repo and push to GitHub:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin <your-repo-url>
   git push -u origin main
   ```

### Firebase Hosting (Frontend Only)
1. Install Firebase CLI:
   ```bash
   npm install -g firebase-tools
   ```
2. Login and initialize:
   ```bash
   firebase login
   firebase init hosting
   # Set public directory to frontend
   # Configure as a single-page app: No
   # Overwrite index.html: No
   ```
3. Deploy:
   ```bash
   firebase deploy
   ```

> **Note:** The backend (FastAPI) must be deployed separately (e.g., on Render, Heroku, or a VM). Update the API URL in `frontend/index.html` if deploying backend elsewhere.

## License
MIT 
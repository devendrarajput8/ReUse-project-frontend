# ReUse Campus Frontend

React + Vite frontend prototype for the ReUse Campus college/hostel resource-sharing platform, based on the supplied project proposal.

## Structure
```text
ReUse_Campus_Frontend/
├── index.html
├── package.json
├── vite.config.js
├── .env.example
├── README.md
└── src/
    ├── main.jsx
    ├── App.jsx
    └── styles.css
```

## Run
Install Node.js LTS, then in this folder:
```bash
npm install
npm run dev
```
Open the local URL printed by Vite (usually http://localhost:5173). Build check: `npm run build`.

## Implemented in this UI prototype
- Student/admin role switch demo
- Search and filters by category, offer type, condition and location
- Sell, rent, donate/free and exchange listing creation
- Item details, view counts, interest requests and listing reports
- Saved favorites, editable listing availability and listing removal
- Per-contact demo conversations and persistent notifications
- Admin listing availability controls, report review and popular-listing activity
- Browser-local persistence for listings, favorites, conversations, notifications, profile and reports
- Popular item suggestions
- Optional call to the deployed FastAPI `POST /predict-category`

## Important
This is a frontend prototype. Its demo data and interactions are saved in the current browser using `localStorage`; they are not shared with other users or devices. The student/admin role switch is not authentication, and local reports, requests and messages do not reach a server. Connect these flows to your Express/MongoDB backend before production. Use backend JWT/bcrypt and role-based authorization, and enforce private data access on the server; hiding fields in React alone is not security.

For ML category suggestions, copy `.env.example` to `.env` and set `VITE_ML_API_URL` to your Render ML service URL. The app calls `/predict-category` with `{title, description}`. If the browser blocks the request, enable suitable CORS on FastAPI or proxy it through Express.

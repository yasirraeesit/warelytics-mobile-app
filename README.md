# QR Inventory Tracking & Analytics System — Mobile App (Expo)

Mobile-first warehouse operator app for scanning QR codes, viewing product details, and recording inventory movements (with basic offline support).

**Tech stack:** React Native (Expo) + TypeScript, Expo Camera/Barcode Scanner, React Navigation, Axios, AsyncStorage

## Repositories
- Backend API: `yasirraeesit/warelytics-backend`
- Client (web): `yasirraeesit/warelytics-client` (or rename your existing admin-dashboard repo)
- Mobile app (this repo): `yasirraeesit/warelytics-mobile-app`

## App Screens (Planned/Building)
- Login
- Home (Scan QR / Recent Scans / Product Lookup / Sync Pending)
- QR Scanner (camera scan + backend lookup)
- Product Action (Stock In / Stock Out / Transfer / Damage / Audit)
- Recent Scans
- Sync Pending Scans (offline queue retry)

## Offline Support (Basic)
If a movement submission fails (no network/server error), the app stores the pending action in AsyncStorage and allows retry from “Sync Pending Scans”.

## Local Setup
```bash
npm install
npm run start
```

## Configuration
During implementation the app will use an API base URL via config (e.g., `EXPO_PUBLIC_API_BASE_URL`).

## Project Plan
See `PROJECT.md`.

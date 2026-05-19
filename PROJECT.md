# QR Inventory Tracking & Analytics System — Mobile App Plan (Expo)

**Repo:** `warelytics-mobile-app`  
**Goal:** a mobile-first warehouse operator app for scanning QR codes, viewing product details, and submitting inventory movements (with basic offline queueing).

---

## Timeline (5 Weeks, overlaps backend)

### Phase 1 — App Skeleton & Auth (Week 1)
- React Navigation setup (stack + tabs)
- Login screen + token storage (AsyncStorage)
- Axios client:
  - base URL via env/config
  - attach JWT to requests
  - 401 handling (logout)

**Acceptance**
- Login → Home works
- Token persists across app reload

---

### Phase 2 — QR Scan Workflow (Week 2)
- Expo camera/barcode scanning screen
- Scan → backend lookup
- Show product details and route to action screen
- Recent scans list (by logged-in user)

**Acceptance**
- Invalid QR shows clear error and logs invalid scan attempt server-side

---

### Phase 3 — Movement Screens (Week 3)
Implement forms + validations:
- Stock In
- Stock Out (validate quantity)
- Transfer (select warehouse/zone/plant + quantity)
- Damage (remarks required)
- Audit (counted qty → creates audit adjustment if mismatch)

**Acceptance**
- Submissions create movement + update product quantity/location

---

### Phase 4 — Offline Queue (Week 4)
- If submission fails: store pending action in AsyncStorage
- “Sync pending scans” screen:
  - retries pending submissions
  - shows per-item success/failure

**Acceptance**
- Pending queue survives app restart and can be retried

---

### Phase 5 — UX Polish & Role Awareness (Week 5)
- Better loading states and error banners
- Show user name + role on Home
- Optional: role-based UI constraints (e.g., VIEWER no submit)
- Telemetry-ready logging (optional)


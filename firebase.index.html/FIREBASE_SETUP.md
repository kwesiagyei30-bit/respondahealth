# Responda Health v4 — Firebase Setup Guide
## 10 Pilot Participants · Free Forever · No Credits

---

## STEP 1 — Create your Firebase project (5 min)

1. Go to **console.firebase.google.com** → Sign in with your Google account
2. Click **"Add project"**
3. Name it: `responda-pilot` → Continue
4. Disable Google Analytics (not needed) → **Create project**
5. Wait ~30 seconds for it to create

---

## STEP 2 — Enable Email/Password Authentication

1. In your project → click **Authentication** (left sidebar)
2. Click **"Get started"**
3. Click **Email/Password** → toggle **Enable** → Save

---

## STEP 3 — Create Realtime Database

1. Click **Realtime Database** (left sidebar)
2. Click **"Create database"**
3. Choose location: **europe-west1** (closest to Ghana)
4. Select **"Start in test mode"** → Enable

> ⚠️ Test mode allows read/write for 30 days. Before going live, update the rules (see Step 6 below).

---

## STEP 4 — Seed the 5 Pilot Hospitals

1. In Realtime Database → click the **"+"** next to your database URL
2. Click **Import JSON**
3. Paste this entire JSON block:

```json
{
  "hospitals": {
    "KORLEBU": {
      "name": "Korle Bu Teaching Hospital",
      "region": "Greater Accra",
      "district": "Ablekuma South",
      "level": 3,
      "phone": "030 2670422",
      "lat": 5.5402,
      "lng": -0.228,
      "beds_emergency_available": 14,
      "beds_emergency_total": 40,
      "beds_icu_available": 3,
      "beds_icu_total": 12,
      "beds_general_available": 0,
      "beds_general_total": 120,
      "beds_maternity_available": 8,
      "beds_maternity_total": 30,
      "beds_paediatric_available": 5,
      "beds_paediatric_total": 20,
      "ct_scan": "operational",
      "mri": "maintenance",
      "blood_bank": "low_stock",
      "oxygen": "adequate",
      "oxygen_level": 78,
      "theatre": "operational",
      "generator": "operational",
      "blood_oneg": 4,
      "blood_opos": 22,
      "blood_apos": 18,
      "blood_bpos": 14,
      "notes": "MRI back ~18:00. O-neg low.",
      "last_updated": "2024-01-15T07:00:00.000Z",
      "updated_by_name": "Nurse Ama Osei"
    },
    "MILITARY37": {
      "name": "37 Military Hospital",
      "region": "Greater Accra",
      "district": "Liberation Rd",
      "level": 2,
      "phone": "030 2776111",
      "lat": 5.562,
      "lng": -0.198,
      "beds_emergency_available": 8,
      "beds_emergency_total": 35,
      "beds_icu_available": 2,
      "beds_icu_total": 8,
      "beds_general_available": 12,
      "beds_general_total": 80,
      "beds_maternity_available": 4,
      "beds_maternity_total": 15,
      "beds_paediatric_available": 6,
      "beds_paediatric_total": 18,
      "ct_scan": "operational",
      "mri": "operational",
      "blood_bank": "operational",
      "oxygen": "adequate",
      "oxygen_level": 85,
      "theatre": "operational",
      "generator": "operational",
      "blood_oneg": 12,
      "blood_opos": 30,
      "blood_apos": 25,
      "blood_bpos": 20,
      "notes": "",
      "last_updated": "2024-01-15T08:15:00.000Z",
      "updated_by_name": "Dr. Kofi Boateng"
    },
    "RIDGE": {
      "name": "Ridge Hospital",
      "region": "Greater Accra",
      "district": "Ridge",
      "level": 2,
      "phone": "030 2666940",
      "lat": 5.5595,
      "lng": -0.186,
      "beds_emergency_available": 0,
      "beds_emergency_total": 30,
      "beds_icu_available": 0,
      "beds_icu_total": 6,
      "beds_general_available": 0,
      "beds_general_total": 60,
      "beds_maternity_available": 2,
      "beds_maternity_total": 20,
      "beds_paediatric_available": 0,
      "beds_paediatric_total": 12,
      "ct_scan": "offline",
      "mri": "offline",
      "blood_bank": "low_stock",
      "oxygen": "low",
      "oxygen_level": 35,
      "theatre": "operational",
      "generator": "maintenance",
      "blood_oneg": 0,
      "blood_opos": 5,
      "blood_apos": 8,
      "blood_bpos": 6,
      "notes": "CT down. Full capacity.",
      "last_updated": "2024-01-15T08:30:00.000Z",
      "updated_by_name": "Admin Ridge"
    },
    "TEMAGEH": {
      "name": "Tema General Hospital",
      "region": "Greater Accra",
      "district": "Tema",
      "level": 2,
      "phone": "030 3202500",
      "lat": 5.6698,
      "lng": -0.0167,
      "beds_emergency_available": 22,
      "beds_emergency_total": 45,
      "beds_icu_available": 5,
      "beds_icu_total": 10,
      "beds_general_available": 35,
      "beds_general_total": 100,
      "beds_maternity_available": 12,
      "beds_maternity_total": 25,
      "beds_paediatric_available": 8,
      "beds_paediatric_total": 20,
      "ct_scan": "operational",
      "mri": "operational",
      "blood_bank": "operational",
      "oxygen": "adequate",
      "oxygen_level": 90,
      "theatre": "operational",
      "generator": "operational",
      "blood_oneg": 18,
      "blood_opos": 35,
      "blood_apos": 28,
      "blood_bpos": 22,
      "notes": "",
      "last_updated": "2024-01-15T07:45:00.000Z",
      "updated_by_name": "Sr. Mansa Tetteh"
    },
    "KATH": {
      "name": "Komfo Anokye Teaching Hospital",
      "region": "Ashanti",
      "district": "Kumasi",
      "level": 3,
      "phone": "032 2022301",
      "lat": 6.6885,
      "lng": -1.6244,
      "beds_emergency_available": 19,
      "beds_emergency_total": 50,
      "beds_icu_available": 7,
      "beds_icu_total": 15,
      "beds_general_available": 28,
      "beds_general_total": 150,
      "beds_maternity_available": 15,
      "beds_maternity_total": 40,
      "beds_paediatric_available": 10,
      "beds_paediatric_total": 30,
      "ct_scan": "operational",
      "mri": "operational",
      "blood_bank": "operational",
      "oxygen": "adequate",
      "oxygen_level": 88,
      "theatre": "operational",
      "generator": "operational",
      "blood_oneg": 20,
      "blood_opos": 40,
      "blood_apos": 35,
      "blood_bpos": 28,
      "notes": "",
      "last_updated": "2024-01-15T06:00:00.000Z",
      "updated_by_name": "Dr. Yaw Asante"
    }
  }
}
```

---

## STEP 5 — Create the 10 Participant Accounts

Go to **Authentication → Users → Add user** and create one account per row:

| # | Email | Password | Role |
|---|-------|----------|------|
| 1 | ama.osei@korlebu.gh | Responda@2024! | Hospital Staff |
| 2 | kofi.boateng@military.gh | Responda@2024! | Hospital Staff |
| 3 | mansa.tetteh@tema.gh | Responda@2024! | Hospital Staff |
| 4 | abena.ridge@ridge.gh | Responda@2024! | Hospital Staff |
| 5 | yaw.asante@kath.gh | Responda@2024! | Hospital Staff |
| 6 | yaw.mensah@ambulance.gh | Responda@2024! | Ambulance Driver |
| 7 | kweku.driver@ambulance.gh | Responda@2024! | Ambulance Driver |
| 8 | abena.asante@ghs.gh | Responda@2024! | Admin |
| 9 | kwame.darko@ghs.gh | Responda@2024! | Admin |
| 10 | nana.adjei@nhia.gh | Responda@2024! | Admin |

---

## STEP 6 — Add User Profiles to Database

After creating all 10 accounts, go to **Realtime Database → click "+" → Import JSON** and paste this (replace each USER_ID with the actual UID from Authentication → Users):

```json
{
  "users": {
    "REPLACE_AMA_UID": {
      "full_name": "Ama Osei",
      "email": "ama.osei@korlebu.gh",
      "role": "staff",
      "hospital": "KORLEBU",
      "staff_id": "PILOT-001"
    },
    "REPLACE_KOFI_UID": {
      "full_name": "Kofi Boateng",
      "email": "kofi.boateng@military.gh",
      "role": "staff",
      "hospital": "MILITARY37",
      "staff_id": "PILOT-002"
    },
    "REPLACE_MANSA_UID": {
      "full_name": "Mansa Tetteh",
      "email": "mansa.tetteh@tema.gh",
      "role": "staff",
      "hospital": "TEMAGEH",
      "staff_id": "PILOT-003"
    },
    "REPLACE_ABENA_R_UID": {
      "full_name": "Abena Mensah",
      "email": "abena.ridge@ridge.gh",
      "role": "staff",
      "hospital": "RIDGE",
      "staff_id": "PILOT-004"
    },
    "REPLACE_YAW_A_UID": {
      "full_name": "Yaw Asante",
      "email": "yaw.asante@kath.gh",
      "role": "staff",
      "hospital": "KATH",
      "staff_id": "PILOT-005"
    },
    "REPLACE_YAW_M_UID": {
      "full_name": "Yaw Mensah",
      "email": "yaw.mensah@ambulance.gh",
      "role": "ambulance",
      "vehicle_id": "GA-2847",
      "staff_id": "PILOT-006"
    },
    "REPLACE_KWEKU_UID": {
      "full_name": "Kweku Darko",
      "email": "kweku.driver@ambulance.gh",
      "role": "ambulance",
      "vehicle_id": "GA-1234",
      "staff_id": "PILOT-007"
    },
    "REPLACE_ABENA_A_UID": {
      "full_name": "Abena Asante",
      "email": "abena.asante@ghs.gh",
      "role": "admin",
      "staff_id": "PILOT-008"
    },
    "REPLACE_KWAME_UID": {
      "full_name": "Kwame Darko",
      "email": "kwame.darko@ghs.gh",
      "role": "admin",
      "staff_id": "PILOT-009"
    },
    "REPLACE_NANA_UID": {
      "full_name": "Nana Adjei",
      "email": "nana.adjei@nhia.gh",
      "role": "admin",
      "staff_id": "PILOT-010"
    }
  }
}
```

---

## STEP 7 — Get Your Firebase Config Values

1. Firebase Console → Project Settings (⚙️ gear icon) → **General** tab
2. Scroll down to **"Your apps"**
3. Click **"Add app"** → choose **Web (</>)**
4. Register app name: `responda-web` → Register
5. Copy the config object — you need these 4 values:
   - `apiKey`
   - `projectId`
   - `authDomain`
   - `databaseURL`

---

## STEP 8 — Deploy to Netlify

1. Go to **netlify.com** → your site → Deploys
2. Drag and drop **responda-firebase-deploy.zip**
3. Site updates in ~10 seconds

---

## STEP 9 — Connect the App

1. Open your Netlify URL on a phone
2. Tap **"Firebase Setup"** (or tap through splash)
3. Paste all 4 config values
4. Tap **"Save & Connect"**
5. Sign in with any participant account

---

## Database Rules (update before going live)

In Firebase Console → Realtime Database → Rules, paste:

```json
{
  "rules": {
    "hospitals": {
      ".read": "auth != null",
      ".write": "auth != null"
    },
    "users": {
      "$uid": {
        ".read": "$uid === auth.uid",
        ".write": "$uid === auth.uid"
      }
    },
    "update_log": {
      ".read": "auth != null",
      ".write": "auth != null"
    },
    "dispatch_log": {
      ".read": "auth != null",
      ".write": "auth != null"
    }
  }
}
```

---

## Free Tier Limits (Firebase Spark Plan)

| Resource | Free Limit | Your Usage (estimate) |
|----------|-----------|----------------------|
| Auth users | 10,000/month | 10 users ✅ |
| DB storage | 1 GB | ~1 MB ✅ |
| DB downloads | 10 GB/month | ~50 MB ✅ |
| DB connections | 100 simultaneous | 10 users ✅ |

**You will never hit these limits with a 10-person pilot.**

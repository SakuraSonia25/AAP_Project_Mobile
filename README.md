# AAP_Project (Consumer Mobile App)

## What it does
This mobile app is the consumer-facing side of the AAP project. It lets users sign in, manage their profile, use face verification, and find nearby bins through a mobile interface. The mobile app consumes APIs provided by the backend (AAP_Project_Website-master) for image classification, face verification, routing, and account services; it also displays web-hosted pages where appropriate.

## Why this matters
By enabling on-demand image classification at the point of deposit, users receive instant feedback on whether their items are accepted or not. This reduces bin contamination, guides users toward correct disposal, and improves the overall e-waste collection and recycling workflow.

## Project Background
### Problem Statement
Under the Resource Sustainability Act, e-waste is classified into regulated and non-regulated categories. However, the public frequently disposes of non-regulated items into designated bins for regulated e-waste, despite clear instructions. This leads to contamination of collection streams and inefficiencies in recycling operations.

The key challenge is to accurately identify deposited items and guide users to dispose of e-waste correctly at the point of disposal.

### Solution
- **Mobile app role:** Enables users to capture images of items prior to disposal, receive real-time classification results from the backend, and view contextual guidance (e.g., accepted vs. non-accepted items). The app also provides alternative disposal instructions and nearest-bin navigation.
- **Website / Backend role:** 
    - **Backend System (Core Engine):** Provides REST APIs and server-side services that power the system, including image classification, face verification, routing, user account handling, and bin-related logic. It processes incoming images, runs the classification models, and returns decisions to the client applications.
    - **Bin Web Interface (On-site Interface):** A lightweight web application deployed at e-waste bins that allows users to take or upload a photo of their item. The backend evaluates the image, and if the item is classified as regulated e-waste, the system triggers the bin to open; otherwise, it provides rejection feedback.
- **Image Detection Model:** Uses two specialized image classification models trained on different subsets of e-waste categories to improve overall coverage. Each model predicts a class label (including an “others” category for unsupported items), and the system selects the most confident prediction to determine whether an item is accepted or rejected.

## Features
- **User flows:** Login, registration, password recovery, profile editing, and face verification enrollment.
- **Image classification:** Capture or upload photos of items for instant classification feedback (regulated vs. non-regulated).
- **Nearest-bin locator:** View nearest e-waste bins on a map with distance and routing information.
- **Account management:** View and update profile details, manage face verification status, and track reward points.
- **Rewards program:** Browse and redeem gift catalogs, track redemption history.
- **Multi-language support:** Interface available in English, Czech, Malay, and Simplified Chinese.
- **Navigation UI:** Drawer and tab-based navigation for intuitive mobile experience.

## Tech Stack
- React Native
- Expo (managed React Native framework)
- JavaScript
- React Navigation (navigation library)
- React Native Maps (map display)
- Expo Location (location services)
- Axios / Fetch (API communication)
- OpenRouteService client (distance & routing)
- i18n (multi-language translations)
- CryptoJS (token generation)


## How to run (mobile)
1. Install dependencies in the project folder.
2. Run the project
```bash
npm install
npm run start
```
2. Start the Expo app and scan the QR code or run on a simulator.

## Issue with Drawer
```
1. Open the Drawer.js file found in /node_modules/react-navigation-drawer/lib/module/views/ folder
2. You will find interpolate in two places, replace the interpolate with interpolateNode in those two places.
```

## Related Repo
- Backend/Website Project: [AAP_Project_Website-master](../../AAP_Project_Website-master/AAP_Project_Website-master/README.md)

## Credits
- App Developers: Rin, Sonia
- ALBA Information & Games: Sean's group (SHSS FYP)
- Translation: Kikina (Czech), Neeza (Malay), Yu Hsi (Simplified Chinese)

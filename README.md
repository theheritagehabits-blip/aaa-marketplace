# AAA Marketplace

> हर सेवा, एक ऐप — Your city. Every service. One platform.

AAA Marketplace is a Progressive Web App (PWA) service marketplace for Bhilwara, India. It connects customers with local service providers across 80+ categories including home services, healthcare, beauty, transportation, and more.

## Tech Stack

| Category | Technology |
|----------|------------|
| **Framework** | React 18 (built with Vite) |
| **Styling** | Tailwind CSS |
| **Backend** | Supabase (Auth, Database, Realtime) |
| **Routing** | React Router v6 |
| **Maps** | Leaflet |
| **Error Tracking** | Sentry |
| **PWA** | Vite PWA Plugin (Workbox) |
| **Fonts** | Noto Sans, Noto Sans Devanagari |

## Project Structure

```
aaa-marketplace/
├── index.html              # Main HTML entry point (Hindi: lang="hi")
├── manifest.webmanifest     # PWA manifest
├── sw.js                   # Service worker (Workbox)
├── registerSW.js           # Service worker registration
├── favicon.svg             # App icon
├── icon-192.png           # PWA icon (192x192)
├── icon-512.png           # PWA icon (512x512)
├── 404.html               # Custom 404 page
├── assets/
│   ├── index-D6uLCB7C.js   # Main React bundle
│   ├── index-CPoM6NOa.js   # Sentry error tracking
│   └── index-CT1qUWHG.css  # Tailwind CSS bundle
├── banners/                # Promotional banner images
│   ├── assistant.jpg
│   ├── medicine.jpg
│   └── offer.jpg
├── icons3d/               # 80+ service category icons (3D style)
│   ├── ac.png
│   ├── cleaning.png
│   ├── electrician.png
│   └── ... (80+ icons)
└── services/              # Service category hero images
    ├── salon.jpg
    ├── plumber.jpg
    └── ...
```

## Features

### User Roles
- **Customer**: Browse services, place orders, manage bookings
- **Vendor**: Manage service requests, view earnings
- **Admin**: Analytics dashboard, order management, user management, catalog control

### Service Categories (80+)
- Home Services (AC, plumber, electrician, cleaning, carpenter)
- Healthcare (ambulance, medicine delivery, lab tests, nursing)
- Beauty & Wellness (salon, makeup, massage, spa)
- Transportation (driver, bike, car wash, tire)
- Food & Catering
- Events & Weddings
- And many more...

### Special Services
- 🏠 Home Assistant
- 🚗 Personal Driver
- 👨‍🍳 Cooking Service
- 🚑 Ambulance
- 💊 Medicine Delivery

### Key Features
- **Bilingual**: Hindi and English support
- **PWA**: Installable as mobile app
- **Offline Support**: Service worker caching
- **OTP Authentication**: Phone/email login with OTP
- **Social Login**: Google and Apple sign-in
- **Real-time Updates**: Live order status
- **Analytics Dashboard**: Admin insights and reporting
- **CSV Export**: Download orders and user reports

## Setup & Installation

### Prerequisites
- Node.js 18+
- npm or yarn
- Supabase account (for backend services)

### Environment Variables

Create a `.env` file with your Supabase credentials:

```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

### Development

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

### Deployment

This is a static site optimized for GitHub Pages deployment (served from `/aaa-marketplace/` path):

```bash
# Preview production build
npm run preview
```

The production build includes:
- Minified and code-split JavaScript
- Optimized CSS
- Service worker for offline support
- PWA manifest

## Deployment Notes

The app is configured to run under the `/aaa-marketplace/` subdirectory path (see `vite.config.js` base path). When deploying:

1. Build the project
2. Deploy the `dist` folder contents
3. Ensure the server serves `index.html` for all routes (SPA routing)

## Browser Support

- Chrome/Edge 90+
- Firefox 90+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## License

[Your license here]

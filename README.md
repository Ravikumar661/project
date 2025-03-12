# Coupon Distribution System

A secure and user-friendly system for distributing coupons to users with built-in abuse prevention mechanisms.

## Features

- Round-robin coupon distribution
- No login required for claiming coupons
- Double-layered abuse prevention:
  - IP address tracking
  - Browser cookie tracking
- One-hour cooldown period between claims
- Clear user feedback and waiting time information
- Beautiful, responsive UI

## Security Measures

1. **IP Address Tracking**
   - Each claim is recorded with the user's IP address
   - Claims from the same IP are restricted to once per hour
   - Uses the ipify API to reliably detect client IP addresses

2. **Cookie-Based Tracking**
   - Browser cookies track claim attempts
   - Provides a second layer of protection against abuse
   - Cookies expire after 24 hours

3. **Database Security**
   - Row Level Security (RLS) enabled
   - Secure policies for claim insertions
   - IP addresses stored securely

## Technical Implementation

- React + TypeScript for the frontend
- Supabase for the database and API
- Tailwind CSS for styling
- Vite for development and building

## Setup Instructions

1. Clone the repository
2. Install dependencies: `npm install`
3. Set up Supabase:
   - Create a new Supabase project
   - Run the migration in `supabase/migrations`
   - Set environment variables:
     ```
     VITE_SUPABASE_URL=your_supabase_url
     VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
     ```
4. Start the development server: `npm run dev`

## Deployment

The application can be deployed to any static hosting service (Netlify, Vercel, etc.) with the following build command:

```bash
npm run build
```

The build output will be in the `dist` directory.
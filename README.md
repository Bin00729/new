# Professional Portfolio Website

A full-stack portfolio website for website builders and graphics designers with admin dashboard, real-time updates, and bilingual support (English & Amharic).

## Features

- 🎨 **Modern Design** with animated background and smooth transitions
- 🔐 **Secure Admin Panel** with password protection (1234) and 3D login page
- 📱 **Fully Responsive** - works perfectly on mobile, tablet, and desktop
- 🌍 **Bilingual Support** - English and Amharic language support
- 🖼️ **Image Management** - Integration with Cloudinary for image storage
- 📦 **Database** - MongoDB for persistent data storage
- ⚡ **Real-time Updates** - Admin changes appear instantly without page refresh
- 📞 **Social Links** - Telegram, WhatsApp, and Instagram integration
- 🎯 **Project Showcase** - Display your best work with detailed descriptions

## Setup Instructions

### Prerequisites
- Node.js 16+ and npm/yarn
- MongoDB Atlas account
- Cloudinary account
- Modern web browser

### Installation

1. **Clone and Install Dependencies**
```bash
npm install
# or
yarn install
```

2. **Environment Variables**

Create a `.env.local` file in the root directory:

```
MONGODB_URI=your-mongodb-connection-string
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=your-cloud-name
CLOUDINARY_API_KEY=your-api-key
CLOUDINARY_API_SECRET=your-api-secret
JWT_SECRET=your-jwt-secret
NEXT_PUBLIC_ADMIN_SECRET=1234
```

**How to get these:**

- **MongoDB**: 
  - Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
  - Create a cluster and database
  - Copy your connection string

- **Cloudinary**:
  - Sign up at [Cloudinary](https://cloudinary.com/)
  - Get your Cloud Name, API Key, and API Secret from the dashboard

3. **Configure Cloudinary Upload Preset**

In `components/ProjectForm.tsx` and `components/ProfileForm.tsx`, update:
```jsx
uploadPreset="your-upload-preset"
```

Get your upload preset from Cloudinary Settings → Upload → Add upload preset

### Running the Application

**Development Mode:**
```bash
npm run dev
# or
yarn dev
```

Visit `http://localhost:3000`

**Production Build:**
```bash
npm run build
npm start
```

## Admin Dashboard Access

1. Look for the **P** logo in the top-left corner
2. Double-click on the logo
3. A 3D login page will appear
4. Enter password: **1234**
5. Access admin features:
   - **Dashboard** - View statistics
   - **Projects** - Add, edit, or delete projects
   - **Profile** - Update your information and social media
   - **Password** - Change admin password

## Features Guide

### User Section
- View your portfolio projects
- Access social media links (Telegram, WhatsApp, Instagram)
- See your location and bio
- Responsive design for all devices
- Language toggle (EN/አማ)

### Admin Section
- **Add Projects**: Upload project images to Cloudinary, add title, description, URL, and technologies
- **Manage Projects**: Edit or delete existing projects
- **Profile Settings**: Update email, social media usernames, location, and upload logo
- **Real-time Updates**: Changes appear instantly on the user side
- **Security**: Password-protected with 3D rotating login page

## Project Structure

```
portfolio-builder/
├── app/                    # Next.js app directory
│   ├── page.tsx           # Home page
│   ├── admin.tsx          # Admin dashboard
│   ├── layout.tsx         # Root layout
│   └── home.tsx           # Home page component
├── components/            # React components
│   ├── AnimatedBackground.tsx
│   ├── Navigation.tsx
│   ├── ProjectCard.tsx
│   ├── Admin3DLogin.tsx
│   ├── ProjectForm.tsx
│   └── ProfileForm.tsx
├── pages/                 # Next.js pages directory (for API)
│   ├── api/              # API routes
│   │   ├── projects.ts
│   │   ├── projects/[id].ts
│   │   ├── auth/login.ts
│   │   ├── admin/profile.ts
│   │   └── admin/change-password.ts
│   ├── _app.tsx
│   └── _document.tsx
├── lib/                   # Utility functions
│   ├── mongodb.ts         # Database connection
│   ├── models.ts          # MongoDB schemas
│   ├── auth.ts            # Authentication functions
│   ├── cloudinary.ts      # Cloudinary utilities
│   ├── store.ts           # Zustand stores
│   └── i18n.ts            # i18n configuration
├── public/
│   └── locales/           # Translation files
│       ├── en/common.json
│       └── am/common.json
├── styles/                # Global styles
│   └── globals.css
└── .env.local             # Environment variables
```

## Technologies Used

- **Frontend**: React 18, Next.js 14, TypeScript
- **Styling**: Tailwind CSS, Framer Motion
- **3D**: Three.js, React Three Fiber
- **Database**: MongoDB, Mongoose
- **Storage**: Cloudinary
- **i18n**: next-i18next, i18next
- **State Management**: Zustand
- **Authentication**: JWT, bcryptjs
- **Icons**: React Icons

## Default Sample Projects

The application comes with 4 sample projects:
1. Hotel Menu Digital
2. Cafe Management System
3. iHope Cafe Website
4. Cherries Hotel Booking

You can edit or delete these and add your own through the admin panel.

## Performance Optimization

- ✅ Optimized images with Next.js Image component
- ✅ Lazy loading for projects
- ✅ CSS animations instead of JavaScript where possible
- ✅ MongoDB connection pooling
- ✅ Cloudinary image optimization
- ✅ Mobile-first responsive design

## Security Features

- 🔐 Password-protected admin panel
- 🔐 JWT token authentication
- 🔐 API route protection
- 🔐 Environment variable protection
- 🔐 HTTPS ready for production

## Deployment

### Deploy to Vercel (Recommended)

1. Push your code to GitHub
2. Connect your repository to [Vercel](https://vercel.com)
3. Add environment variables in Vercel settings
4. Deploy with one click!

### Deploy to Other Platforms

- **Netlify**: Supported (configure build command: `npm run build`)
- **Heroku**: Supported
- **AWS, Azure, GCP**: Supported

## Troubleshooting

### MongoDB Connection Error
- Verify your connection string in `.env.local`
- Check IP whitelist in MongoDB Atlas
- Ensure database user has correct permissions

### Cloudinary Upload Issues
- Verify API credentials
- Check upload preset is configured
- Ensure folder structure is correct

### Admin Login Not Working
- Default password is `1234`
- Clear browser cache and cookies
- Check browser console for errors

### Images Not Loading
- Verify Cloudinary Cloud Name is correct
- Check image URLs in MongoDB
- Test Cloudinary connection

## Support & Contributions

For issues, questions, or contributions, please contact or create an issue.

## License

This project is open source and available under the MIT License.

---

**Made with ❤️ for Ethiopian developers**

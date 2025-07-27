# Deployment Guide for Finance Tracker

## Render Deployment (Backend)

### Step 1: Upload to GitHub
1. Create a new GitHub repository
2. Upload all files to the repository
3. Make sure the repository is public

### Step 2: Deploy to Render
1. Go to [render.com](https://render.com)
2. Sign up with GitHub
3. Click "New Web Service"
4. Connect your GitHub repository
5. Render will auto-detect it's a Node.js app

### Step 3: Configure Environment Variables
In Render dashboard, add these environment variables:
```
NODE_ENV=production
DB_TYPE=mysql
DB_HOST=your-mysql-host
DB_PORT=3306
DB_USERNAME=your-mysql-username
DB_PASSWORD=your-mysql-password
DB_DATABASE=your-mysql-database
JWT_SECRET=your-production-secret-key-here
JWT_EXPIRES_IN=24h
```

### Step 4: Deploy
1. Click "Create Web Service"
2. Wait for deployment to complete
3. Copy your Render URL (something like `https://finance-tracker.onrender.com`)

## MySQL Database Setup

### Option 1: Render MySQL (Recommended)
1. In Render dashboard, click "New Service"
2. Select "Database" → "MySQL"
3. Render will create a MySQL database
4. Copy the connection details from the "Connect" tab
5. Update your backend environment variables with these details

### Option 2: PlanetScale MySQL
1. Go to [planetscale.com](https://planetscale.com)
2. Create a free account
3. Create a new database
4. Get connection details from Settings → Database
5. Update environment variables

### Option 3: AWS RDS MySQL
1. Create AWS account
2. Set up RDS MySQL instance
3. Get connection details
4. Update environment variables

## Vercel Deployment (Frontend)

### Step 1: Deploy Frontend
1. Go to [vercel.com](https://vercel.com)
2. Sign up with GitHub
3. Click "New Project"
4. Import your GitHub repository
5. Set the root directory to `/frontend`

### Step 2: Configure Environment Variables
In Vercel dashboard, add:
```
VITE_API_URL=https://your-render-backend-url.onrender.com/api
```

### Step 3: Deploy
1. Click "Deploy"
2. Wait for deployment to complete
3. Copy your Vercel URL

## Testing Your Deployment

### Backend (Render)
- Visit your Render URL
- You should see: `{"message":"Personal Finance Tracker API","version":"1.0.0","status":"running"}`
- Visit `/api/docs` for API documentation
- **Note:** You'll need to set up MySQL database separately (see MySQL setup above)

### Frontend (Vercel)
- Visit your Vercel URL
- Register a new user
- Test all features

## Troubleshooting

### Backend Issues
- Check Render logs for errors
- Verify environment variables are set
- Make sure the repository is public
- Ensure MySQL database is accessible

### Frontend Issues
- Check if `VITE_API_URL` is set correctly
- Verify the backend URL is accessible
- Check browser console for errors

## File Structure for GitHub

Your repository should have this structure:
```
finance-tracker/
├── src/                    # Backend source code
├── frontend/              # Frontend React app
├── package.json           # Backend dependencies
├── render.yaml            # Render configuration
├── README.md              # Project documentation
├── DEPLOYMENT.md          # This file
└── .gitignore            # Git ignore rules
```

## Environment Variables Reference

### Backend (Render)
```
NODE_ENV=production
DB_TYPE=mysql
DB_HOST=your-mysql-host
DB_PORT=3306
DB_USERNAME=your-mysql-username
DB_PASSWORD=your-mysql-password
DB_DATABASE=your-mysql-database
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=24h
```

### Frontend (Vercel)
```
VITE_API_URL=https://your-backend-url.onrender.com/api
``` 
# Finance Tracker - Full Stack Application

A comprehensive personal finance tracking application built with React, Node.js, and TypeScript.

## Features

- **User Authentication** - Register, login, and role-based access control
- **Transaction Management** - Add, edit, delete, and categorize transactions
- **Financial Analytics** - Charts, trends, and spending analysis
- **Dashboard** - Real-time financial overview
- **Role-Based Access** - Admin, User, and Read-Only roles
- **Responsive Design** - Works on desktop and mobile

## Tech Stack

### Frontend
- React 18 with TypeScript
- Vite for fast development
- Tailwind CSS for styling
- Shadcn/ui components
- Recharts for data visualization
- React Router for navigation

### Backend
- Node.js with Express
- TypeScript for type safety
- TypeORM for database management
- JWT for authentication
- Rate limiting and security middleware
- Swagger API documentation

### Database
- MySQL (development and production)
- Redis for caching (optional)

## Quick Start

### Prerequisites
- Node.js 18+
- npm or yarn

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/finance-tracker.git
cd finance-tracker
```

2. **Install dependencies**
```bash
npm install
cd backend && npm install
cd ../frontend && npm install
```

3. **Set up environment variables**
```bash
# Backend (.env)
NODE_ENV=development
PORT=3001
DB_TYPE=mysql
DB_HOST=localhost
DB_PORT=3306
DB_USERNAME=root
DB_PASSWORD=your-mysql-password
DB_DATABASE=finance_tracker
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=24h
```

4. **Start development servers**
```bash
# Start both frontend and backend
npm run dev

# Or start separately
npm run dev:backend
npm run dev:frontend
```

5. **Access the application**
- Frontend: http://localhost:5173
- Backend API: http://localhost:3001
- API Docs: http://localhost:3001/api/docs

## Deployment

### Backend (Render)
1. Connect GitHub repository to Render
2. Create new Web Service
3. Set environment variables:
   ```
   NODE_ENV=production
   DB_TYPE=mysql
   DB_HOST=your-mysql-host
   DB_PORT=3306
   DB_USERNAME=your-mysql-username
   DB_PASSWORD=your-mysql-password
   DB_DATABASE=your-mysql-database
   JWT_SECRET=your-production-secret
   JWT_EXPIRES_IN=24h
   ```

### Frontend (Vercel)
1. Deploy to Vercel
2. Set environment variable:
   ```
   VITE_API_URL=https://your-backend-url.onrender.com/api
   ```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get user profile

### Transactions
- `GET /api/transactions` - Get all transactions
- `POST /api/transactions` - Create transaction
- `PUT /api/transactions/:id` - Update transaction
- `DELETE /api/transactions/:id` - Delete transaction

### Analytics
- `GET /api/analytics/overview` - Get financial overview
- `GET /api/analytics/trends` - Get spending trends
- `GET /api/analytics/categories` - Get category breakdown

### Categories
- `GET /api/categories` - Get all categories
- `POST /api/categories` - Create category
- `PUT /api/categories/:id` - Update category
- `DELETE /api/categories/:id` - Delete category

## User Roles

### Admin
- Full access to all features
- User management
- System analytics
- All CRUD operations

### User
- Personal transaction management
- Personal analytics
- Category management

### Read-Only
- View all transactions (system-wide)
- View analytics (system-wide)
- No modification permissions

## Environment Variables

### Backend
```
NODE_ENV=production
PORT=3001
DB_TYPE=sqlite|mysql
DB_HOST=localhost
DB_PORT=3306
DB_USERNAME=root
DB_PASSWORD=password
DB_DATABASE=finance_tracker
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=24h
REDIS_URL=redis://localhost:6379 (optional)
```

### Frontend
```
VITE_API_URL=https://your-backend-url.com/api
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

MIT License - see LICENSE file for details

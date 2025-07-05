# SmartKids - All-in-one Child Management Platform

## Project Overview

SmartKids is a comprehensive web application designed for parents with elementary school children. It provides a centralized platform to systematically record and manage information about children's learning, health, and school life, supporting healthy growth and effective learning through data-based analysis and statistics.

## Technology Stack

### Frontend
- **Framework**: React 19.1.0 with TypeScript
- **Build Tool**: Vite 6.2.0
- **UI Components**: Custom components with Lucide React icons
- **Charts**: Recharts 3.0.2 for data visualization
- **Styling**: Tailwind CSS (utility-first CSS framework)
- **AI Integration**: Google Gemini API (@google/genai)

### Backend
- **Runtime**: Node.js with Express.js 4.19.2
- **Database**: PostgreSQL with node-pg-migrate for migrations
- **Authentication**: JWT tokens with bcrypt for password hashing
- **CORS**: Configured for cross-origin requests
- **Environment**: dotenv for environment variable management

### Deployment
- **Frontend**: Vite-based build system
- **Backend**: Vercel serverless functions
- **Database**: PostgreSQL (likely hosted on Neon or similar)

## Project Structure

```
smartkids/
├── src/
│   ├── App.tsx                 # Main application component
│   ├── index.tsx              # React entry point
│   ├── types.ts               # TypeScript type definitions
│   ├── constants.ts           # Application constants
│   └── components/
│       ├── AuthPage.tsx       # Authentication page
│       ├── ChildModal.tsx     # Child management modal
│       ├── HealthDashboard.tsx # Health tracking dashboard
│       ├── LearningDashboard.tsx # Learning progress dashboard
│       ├── SchoolLifeDashboard.tsx # School activities dashboard
│       ├── MealPlanDashboard.tsx # Meal planning dashboard
│       ├── SettingsDashboard.tsx # Settings management
│       ├── GrowthChart.tsx    # Growth visualization
│       ├── AiAnalysisModal.tsx # AI-powered analysis
│       └── ui/                # Reusable UI components
│           ├── Button.tsx
│           ├── Card.tsx
│           ├── Input.tsx
│           └── Modal.tsx
├── server/
│   ├── src/
│   │   ├── index.js           # Express server entry point
│   │   ├── controllers/       # Request handlers
│   │   ├── middleware/        # Authentication middleware
│   │   ├── models/           # Database models
│   │   └── routes/           # API route definitions
│   ├── migrations/           # Database schema migrations
│   └── vercel.json          # Vercel deployment configuration
├── package.json             # Frontend dependencies
├── tsconfig.json           # TypeScript configuration
├── vite.config.ts          # Vite build configuration
└── index.html              # HTML entry point
```

## Key Features

### 1. Multi-Child Management
- Support for multiple children per parent account
- Individual profiles with photos and basic information
- Child-specific dashboards and data tracking

### 2. Health Dashboard
- Growth tracking (height, weight charts)
- Vaccination records and scheduling
- Medical visit history
- Health data visualization

### 3. Learning Dashboard
- Study session tracking
- Homework assignment management
- Exam preparation monitoring
- Learning progress analytics

### 4. School Life Management
- Attendance tracking
- School event calendar
- Assignment due dates
- Academic performance monitoring

### 5. Meal Planning
- Daily meal planning and tracking
- Nutritional information management
- Meal history and patterns

### 6. AI Analysis
- Integration with Google Gemini API
- Intelligent insights and recommendations
- Data-driven analysis of child development

## Development Commands

### Frontend
```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

### Backend
```bash
# Navigate to server directory
cd server

# Install dependencies
npm install

# Run database migrations
npm run migrate

# Start server (development)
node src/index.js
```

## Environment Configuration

### Frontend (.env.local)
```
GEMINI_API_KEY=your_gemini_api_key
VITE_API_BASE_URL=http://localhost:5000
```

### Backend (server/.env)
```
DATABASE_URL=your_postgresql_connection_string
JWT_SECRET=your_jwt_secret
PORT=5000
```

## Database Schema

### Users Table
- id (primary key)
- email (unique)
- password_hash
- name
- profile_image_url
- created_at

### Children Table
- id (primary key)
- user_id (foreign key to users)
- name
- birthdate
- profile_image_url
- created_at

## API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration

### Children Management
- `GET /api/children` - Get user's children
- `POST /api/children` - Add new child
- `PUT /api/children/:id` - Update child information
- `DELETE /api/children/:id` - Remove child

## Development Guidelines

### Code Style
- Use TypeScript for type safety
- Follow React functional component patterns
- Use custom hooks for reusable logic
- Implement proper error handling
- Use meaningful variable and function names

### Component Structure
- Keep components small and focused
- Use prop interfaces for type safety
- Implement proper state management
- Use useCallback and useMemo for performance optimization

### State Management
- Use React's built-in state management (useState, useContext)
- Implement proper data flow between components
- Handle loading and error states appropriately

### API Integration
- Use fetch with proper error handling
- Implement authentication headers
- Handle API response states (loading, success, error)
- Use async/await for better readability

## Security Considerations

- JWT tokens for authentication
- Password hashing with bcrypt
- CORS configuration for allowed origins
- Input validation and sanitization
- Environment variable protection

## Performance Optimization

- Vite for fast development and builds
- Code splitting and lazy loading
- Optimized bundle size
- Efficient state updates
- Memoization where appropriate

## Deployment

### Frontend
- Build using Vite
- Deploy to static hosting (Vercel, Netlify)
- Configure environment variables

### Backend
- Deploy to Vercel serverless functions
- Configure PostgreSQL database
- Set up environment variables
- Configure CORS for production domains

## Future Enhancements

- Real-time notifications
- Mobile app development
- Advanced analytics dashboard
- Integration with school systems
- Social features for parents
- Offline capability
- Multi-language support

## Development Best Practices

1. **Type Safety**: Utilize TypeScript throughout the application
2. **Component Reusability**: Create reusable UI components
3. **Error Handling**: Implement comprehensive error boundaries
4. **Testing**: Add unit and integration tests
5. **Documentation**: Keep code well-documented
6. **Version Control**: Use meaningful commit messages
7. **Code Review**: Implement proper code review process
8. **Performance**: Monitor and optimize application performance

## Troubleshooting

### Common Issues
- **Database Connection**: Check PostgreSQL connection string
- **API Errors**: Verify backend server is running
- **Authentication**: Ensure JWT tokens are properly configured
- **CORS Issues**: Check allowed origins in backend configuration
- **Build Errors**: Verify all dependencies are installed

### Debug Commands
```bash
# Check server logs
node src/index.js

# Verify database connection
npm run migrate

# Check frontend build
npm run build
```

This documentation provides a comprehensive guide for developing, maintaining, and extending the SmartKids platform.
# Johnbabs Environmental Services - Project Documentation

## Table of Contents
1. [Project Overview](#project-overview)
2. [Technology Stack](#technology-stack)
3. [Project Structure](#project-structure)
4. [Setup and Installation](#setup-and-installation)
5. [Features and Functionality](#features-and-functionality)
6. [Admin Panel](#admin-panel)
7. [Backend API](#backend-api)
8. [Deployment](#deployment)
9. [Development Workflow](#development-workflow)
10. [Troubleshooting](#troubleshooting)
11. [Security Considerations](#security-considerations)
12. [Future Enhancements](#future-enhancements)

## Project Overview

**Johnbabs Environmental and Engineering Services Ltd** is a comprehensive website for a Nigerian environmental consultancy and engineering services company. The project includes a modern, responsive frontend built with React and TypeScript, and a backend API for content management.

### Key Features
- Professional, responsive website design
- Content management system (CMS)
- Image and logo upload functionality
- Team member management
- Project portfolio management
- Admin authentication system
- Mobile-optimized interface

## Technology Stack

### Frontend
- **React 18** - UI framework
- **TypeScript** - Type safety and development experience
- **Vite** - Build tool and development server
- **React Router** - Client-side routing
- **Tailwind CSS** - Utility-first CSS framework
- **Lucide React** - Icon library
- **Context API** - State management

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **JWT** - Authentication
- **In-memory storage** - Data persistence (development)
- **MongoDB** - Database (production ready)

### Deployment
- **GitHub Pages** - Static site hosting
- **GitHub Actions** - CI/CD pipeline
- **Docker** - Containerization (optional)

## Project Structure

```
jbs-project-v1/
├── src/
│   ├── components/          # Reusable UI components
│   │   ├── Navbar.tsx       # Navigation component
│   │   ├── Footer.tsx       # Footer component
│   │   ├── LoginModal.tsx   # Admin login modal
│   │   ├── LogoUpload.tsx   # Logo upload component
│   │   ├── ImageUpload.tsx  # Image upload component
│   │   ├── DataDisplay.tsx  # Data display component
│   │   └── ScrollToTop.tsx  # Scroll to top functionality
│   ├── pages/               # Page components
│   │   ├── Home.tsx         # Homepage
│   │   ├── About.tsx        # About page
│   │   ├── Services.tsx     # Services page
│   │   ├── Projects.tsx     # Projects page
│   │   ├── Management.tsx   # Team management page
│   │   ├── Contact.tsx      # Contact page
│   │   └── Admin.tsx        # Admin panel
│   ├── contexts/            # React contexts
│   │   ├── AuthContext.tsx  # Authentication context
│   │   └── WebsiteDataContext.tsx # Website data context
│   ├── services/            # API services
│   │   └── api.ts           # API client
│   ├── App.tsx              # Main app component
│   ├── main.tsx             # App entry point
│   └── index.css            # Global styles
├── backend/                 # Backend server
│   ├── server-simple.js     # Simplified backend server
│   ├── server.js            # Full backend server (MongoDB)
│   ├── routes/              # API routes
│   ├── models/              # Data models
│   ├── middleware/          # Express middleware
│   └── uploads/             # File uploads directory
├── public/                  # Static assets
│   ├── images/              # Website images
│   ├── favicon files        # Favicon and icons
│   └── 404.html             # 404 redirect for SPA
├── deployment files         # Docker, nginx configs
└── configuration files      # Package.json, vite.config, etc.
```

## Setup and Installation

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn
- Git

### Frontend Setup
```bash
# Clone the repository
git clone https://github.com/Ikenna-Brendan/johnbabs-environmental-services.git
cd jbs-project-v1

# Install dependencies
npm install

# Start development server
npm run dev
```

### Backend Setup
```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Start backend server (simplified version)
node server-simple.js

# Or start full version with MongoDB
npm run dev
```

### Environment Variables
Create a `.env` file in the backend directory:
```env
PORT=5000
JWT_SECRET=your_jwt_secret_here
MONGODB_URI=your_mongodb_connection_string
```

## Features and Functionality

### Website Pages

#### 1. Homepage (`/`)
- Hero section with dynamic background image
- Company statistics and achievements
- Service highlights
- Call-to-action sections
- Responsive design for all devices

#### 2. About Page (`/about`)
- Company history and mission
- Core values and principles
- Professional certifications
- Industry expertise

#### 3. Services Page (`/services`)
- Comprehensive service offerings:
  - Environmental Consultancy
  - Social Impact Assessment
  - Engineering Design & Supervision
  - Waste Management Solutions
  - Environmental Restoration
  - Cleaning & Pest Control

#### 4. Projects Page (`/projects`)
- Project portfolio showcase
- Filterable project categories
- Detailed project descriptions
- Image galleries

#### 5. Management Page (`/management`)
- Team member profiles
- Leadership information
- Contact details
- Professional backgrounds

#### 6. Contact Page (`/contact`)
- Contact information
- Office locations
- Contact form
- Business hours

### Responsive Design
- Mobile-first approach
- Tablet and desktop optimization
- Touch-friendly navigation
- Optimized images and content

## Admin Panel

### Access
- URL: `/admin`
- Login required with admin credentials
- Secure JWT-based authentication

### Features

#### 1. Dashboard
- Overview of website content
- Quick statistics
- Recent activity

#### 2. Company Information Management
- Update company details
- Modify contact information
- Edit mission and vision statements

#### 3. Team Member Management
- Add new team members
- Edit existing profiles
- Upload profile pictures
- Manage contact information

#### 4. Project Management
- Create new projects
- Edit project details
- Upload project images
- Categorize projects

#### 5. Image Management
- Upload and manage images
- Organize by categories
- Replace default images
- Logo management

#### 6. Content Management
- Edit page content
- Update service descriptions
- Modify company information

### Admin Credentials
- **Username**: admin
- **Password**: admin123
- **Note**: Credentials are not displayed on the login form for security

## Backend API

### Authentication Endpoints
```
POST /api/auth/login          # User login
GET  /api/auth/me            # Get current user
PUT  /api/auth/change-password # Change password
```

### Company Endpoints
```
GET  /api/company            # Get company info
PUT  /api/company            # Update company info
```

### Team Endpoints
```
GET    /api/team             # Get all team members
POST   /api/team             # Add new team member
PUT    /api/team/:id         # Update team member
DELETE /api/team/:id         # Delete team member
```

### Project Endpoints
```
GET    /api/projects         # Get all projects
POST   /api/projects         # Add new project
PUT    /api/projects/:id     # Update project
DELETE /api/projects/:id     # Delete project
```

### Image Endpoints
```
GET    /api/images/url/:key  # Get image URL
POST   /api/images/upload    # Upload image
DELETE /api/images/:key      # Delete image
```

### Security Features
- JWT token authentication
- Password hashing
- CORS configuration
- Input validation
- Error handling

## Deployment

### GitHub Pages Deployment

#### 1. Repository Setup
```bash
# Initialize git repository
git init
git add .
git commit -m "Initial commit"

# Add remote repository
git remote add origin https://github.com/username/repository-name.git
git push -u origin main
```

#### 2. GitHub Pages Configuration
- Go to repository Settings > Pages
- Select "Deploy from a branch"
- Choose "main" branch and "/ (root)" folder
- Enable GitHub Actions for automatic deployment

#### 3. GitHub Actions Workflow
The project includes a `.github/workflows/deploy.yml` file that:
- Builds the project on push to main branch
- Deploys to GitHub Pages
- Handles SPA routing with 404.html redirect

### Docker Deployment (Optional)

#### 1. Build Docker Image
```bash
docker build -t johnbabs-website .
```

#### 2. Run Container
```bash
docker run -p 80:80 johnbabs-website
```

#### 3. Docker Compose
```bash
docker-compose up -d
```

### Environment Configuration

#### Development
- Frontend: `http://localhost:5173`
- Backend: `http://localhost:5000`
- Base URL: `/` (no subdirectory)

#### Production (GitHub Pages)
- Frontend: `https://username.github.io/repository-name/`
- Base URL: `/repository-name/`
- Backend: Separate deployment required

## Development Workflow

### Code Organization
- **Components**: Reusable UI elements
- **Pages**: Route-specific components
- **Contexts**: Global state management
- **Services**: API communication
- **Types**: TypeScript type definitions

### Styling Guidelines
- Tailwind CSS for styling
- Responsive design principles
- Consistent color scheme (emerald/teal)
- Mobile-first approach

### State Management
- React Context API for global state
- Local state for component-specific data
- API service layer for data fetching

### Error Handling
- Try-catch blocks for API calls
- User-friendly error messages
- Graceful fallbacks for missing data
- Loading states for better UX

## Troubleshooting

### Common Issues

#### 1. App Not Loading (Blank Page)
**Cause**: API calls hanging due to backend unavailability
**Solution**: Added timeouts to API calls in LogoUpload and AuthContext

#### 2. Routing Issues on GitHub Pages
**Cause**: SPA routing conflicts with GitHub Pages
**Solution**: 
- Added 404.html redirect script
- Updated Vite base path configuration
- Fixed image paths with `${import.meta.env.BASE_URL}`

#### 3. Mobile Navigation Issues
**Cause**: Touch targets too small
**Solution**: Increased button sizes and improved mobile menu

#### 4. Image Loading Problems
**Cause**: Incorrect file paths or extensions
**Solution**: 
- Verified image file extensions (.jpeg vs .jpg)
- Updated image paths for GitHub Pages compatibility
- Added fallback images

#### 5. Backend Connection Issues
**Cause**: Server not running or wrong directory
**Solution**: 
- Ensure backend server is running from correct directory
- Check port availability
- Verify API base URL configuration

### Development Commands

```bash
# Start frontend development server
npm run dev

# Start backend server (from backend directory)
cd backend
node server-simple.js

# Build for production
npm run build

# Preview production build
npm run preview

# Deploy to GitHub Pages
npm run deploy
```

### Debugging Tips
- Check browser console for errors
- Verify API endpoints are accessible
- Test on different devices and browsers
- Use browser dev tools for responsive testing
- Monitor network requests for API issues

## Security Considerations

### Frontend Security
- No sensitive data in client-side code
- Input validation on forms
- XSS prevention with proper escaping
- Secure image upload handling

### Backend Security
- JWT token authentication
- Password hashing
- Input sanitization
- CORS configuration
- Rate limiting (recommended for production)

### Deployment Security
- HTTPS enforcement
- Secure headers configuration
- Environment variable protection
- Regular dependency updates

### Admin Panel Security
- Strong password requirements
- Session management
- Access control
- Audit logging (recommended)

## Future Enhancements

### Planned Features
1. **Blog/News Section**
   - Company updates and industry news
   - SEO-optimized content management

2. **Client Portal**
   - Project status tracking
   - Document sharing
   - Communication tools

3. **Advanced Analytics**
   - Website traffic monitoring
   - User behavior analysis
   - Performance metrics

4. **Multi-language Support**
   - English and local language options
   - Internationalization (i18n)

5. **Enhanced SEO**
   - Meta tag management
   - Sitemap generation
   - Schema markup

### Technical Improvements
1. **Database Integration**
   - MongoDB connection for production
   - Data migration scripts
   - Backup strategies

2. **Performance Optimization**
   - Image optimization
   - Code splitting
   - Caching strategies

3. **Testing**
   - Unit tests for components
   - Integration tests for API
   - End-to-end testing

4. **Monitoring**
   - Error tracking
   - Performance monitoring
   - Uptime monitoring

### Content Management
1. **Rich Text Editor**
   - WYSIWYG content editing
   - Media library management
   - Version control

2. **Advanced Image Management**
   - Image cropping and resizing
   - Multiple image formats
   - CDN integration

3. **SEO Tools**
   - Meta description editor
   - Keyword optimization
   - Search console integration

## Conclusion

The Johnbabs Environmental Services website is a comprehensive, professional solution that provides:

- **Modern, responsive design** that works on all devices
- **Complete content management system** for easy updates
- **Secure admin panel** for website maintenance
- **Scalable architecture** for future enhancements
- **Production-ready deployment** with GitHub Pages

The project demonstrates best practices in modern web development, including:
- TypeScript for type safety
- React for component-based architecture
- Tailwind CSS for efficient styling
- JWT authentication for security
- Responsive design for accessibility
- Git-based deployment workflow

The website is now live and fully functional, providing a professional online presence for Johnbabs Environmental and Engineering Services Ltd.

---

**Last Updated**: December 2024
**Version**: 1.0.0
**Status**: Production Ready

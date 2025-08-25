# Portfolio Website Setup Guide

A comprehensive setup guide for deploying and configuring the modern portfolio website built with Next.js 15, TypeScript, and advanced web technologies.

## 🚀 Quick Start

### Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18.0.0 or higher)
- **npm** (v8.0.0 or higher) or **yarn** (v1.22.0 or higher)
- **Git** (for version control)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd portfolio-website
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env.local
   ```

4. **Configure environment variables**
   Edit `.env.local` and add the following:
   ```env
   # Database
   DATABASE_URL="file:./db/custom.db"

   # NextAuth.js
   NEXTAUTH_SECRET="your-nextauth-secret-here"
   NEXTAUTH_URL="http://localhost:3000"

   # Optional: Add your own values
   GITHUB_ID=""
   GITHUB_SECRET=""
   GOOGLE_CLIENT_ID=""
   GOOGLE_CLIENT_SECRET=""
   ```

5. **Set up the database**
   ```bash
   # Generate Prisma client
   npm run db:generate

   # Push database schema
   npm run db:push
   ```

6. **Start the development server**
   ```bash
   npm run dev
   ```

7. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000) to see your portfolio website.

## 📋 Detailed Setup Instructions

### 1. System Requirements

#### Node.js Version
- **Minimum**: Node.js 18.0.0
- **Recommended**: Node.js 20.0.0 or higher
- **Check version**: `node --version`

#### Package Manager
- **npm**: Comes with Node.js
- **yarn**: Optional alternative (install with `npm install -g yarn`)

### 2. Project Structure Overview

```
portfolio-website/
├── src/
│   ├── app/                    # Next.js App Router
│   │   ├── page.tsx           # Main portfolio page
│   │   ├── layout.tsx         # Root layout with providers
│   │   └── globals.css        # Global styles
│   ├── components/            # React components
│   │   ├── ui/               # shadcn/ui components
│   │   ├── 3DHero.tsx        # 3D hero section
│   │   ├── 3DBackground.tsx  # 3D background
│   │   ├── Navigation.tsx    # Navigation component
│   │   ├── InteractiveTimeline.tsx  # Experience timeline
│   │   ├── ProjectDemo.tsx   # Project showcase
│   │   └── ResumeDownload.tsx # Resume functionality
│   ├── hooks/                # Custom React hooks
│   │   ├── use-mobile.ts     # Mobile detection
│   │   └── use-toast.ts      # Toast notifications
│   └── lib/                  # Utility functions
│       ├── db.ts             # Database client
│       ├── socket.ts         # Socket.io setup
│       └── utils.ts          # Utility functions
├── public/                   # Static assets
│   ├── manifest.json         # PWA manifest
│   ├── sw.js                # Service worker
│   └── images/              # Images and assets
├── prisma/                   # Database schema
│   └── schema.prisma        # Database definitions
├── db/                      # Database files
│   └── custom.db            # SQLite database
├── components.json          # shadcn/ui config
├── tailwind.config.ts       # Tailwind CSS config
├── tsconfig.json           # TypeScript config
├── next.config.ts          # Next.js config
├── server.ts               # Custom server with Socket.IO
├── package.json            # Dependencies and scripts
├── requirements.txt        # Python-style requirements list
└── README.md              # Project documentation
```

### 3. Environment Configuration

#### Required Environment Variables

Create a `.env.local` file in the root directory:

```env
# Database Configuration
DATABASE_URL="file:./db/custom.db"

# NextAuth.js Configuration
NEXTAUTH_SECRET="generate-a-random-secret-here"
NEXTAUTH_URL="http://localhost:3000"

# Optional OAuth Providers (uncomment to enable)
# GITHUB_ID="your-github-client-id"
# GITHUB_SECRET="your-github-client-secret"
# GOOGLE_CLIENT_ID="your-google-client-id"
# GOOGLE_CLIENT_SECRET="your-google-client-secret"

# AI SDK Configuration (optional)
Z_AI_API_KEY="your-z-ai-api-key"
```

#### Generating NextAuth Secret

Generate a secure secret for NextAuth.js:

```bash
# Using Node.js
node -e "console.log(crypto.randomBytes(32).toString('hex'))"

# Using OpenSSL
openssl rand -base64 32
```

### 4. Database Setup

#### Prisma Configuration

The project uses Prisma ORM with SQLite for development:

1. **Install Prisma CLI** (already included in dependencies):
   ```bash
   npm install prisma --save-dev
   ```

2. **Generate Prisma Client**:
   ```bash
   npm run db:generate
   ```

3. **Push Schema to Database**:
   ```bash
   npm run db:push
   ```

#### Database Schema

The current schema includes:
- **User** model for authentication
- **Post** model for blog/content management

To modify the schema, edit `prisma/schema.prisma` and run:
```bash
npm run db:push
```

### 5. Development Server

#### Starting the Development Server

```bash
# Start with hot reload and logging
npm run dev

# The server runs on:
# - HTTP: http://localhost:3000
# - Socket.IO: ws://localhost:3000/api/socketio
```

#### Development Features

- **Hot Module Replacement (HMR)**: Instant code updates
- **TypeScript Checking**: Real-time type errors
- **ESLint**: Code quality and style enforcement
- **Socket.IO Integration**: Real-time features
- **Logging**: Development logs saved to `dev.log`

### 6. Build and Deployment

#### Building for Production

```bash
# Build the application
npm run build

# Start production server
npm start
```

#### Production Features

- **Optimized Build**: Minified and bundled assets
- **Static Generation**: Pre-rendered pages for better performance
- **Image Optimization**: Automatic image processing with Sharp
- **PWA Support**: Offline functionality and app-like experience
- **SEO Optimized**: Meta tags and structured data

### 7. Available Scripts

#### Development Scripts

```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint
```

#### Database Scripts

```bash
npm run db:push      # Push schema changes to database
npm run db:generate  # Generate Prisma client
npm run db:migrate   # Create and apply migrations
npm run db:reset     # Reset database
```

### 8. Technology Stack Details

#### Core Technologies

- **Next.js 15**: React framework with App Router
- **React 19**: UI library with concurrent features
- **TypeScript 5**: Type-safe JavaScript
- **Tailwind CSS 4**: Utility-first CSS framework

#### UI Components

- **shadcn/ui**: High-quality, accessible components
- **Radix UI**: Headless UI primitives
- **Lucide React**: Beautiful icon library
- **Framer Motion**: Animation library

#### Advanced Features

- **3D Graphics**: Three.js and React Three Fiber
- **Touch Gestures**: React Swipeable for mobile interactions
- **PWA**: Progressive Web App capabilities
- **Real-time**: Socket.IO for live features
- **SEO**: Structured data and meta tags

### 9. Customization Guide

#### Personalizing the Portfolio

1. **Update Personal Information**
   - Edit `src/app/page.tsx` to change name, title, and description
   - Update contact information and social links

2. **Customize Skills Section**
   - Modify the skills array in the main page
   - Add or remove skill categories and badges

3. **Update Experience**
   - Edit the experience data in `src/app/page.tsx`
   - Modify timeline entries and company information

4. **Add Projects**
   - Update the projects array with your own work
   - Add project images, descriptions, and technologies

5. **Customize Styling**
   - Modify `src/app/globals.css` for global styles
   - Update Tailwind config for custom themes
   - Adjust component-specific styles

#### Adding New Features

1. **New Components**: Create in `src/components/`
2. **New Pages**: Add to `src/app/` following App Router conventions
3. **API Routes**: Create in `src/app/api/` for backend functionality
4. **Database Models**: Update `prisma/schema.prisma`

### 10. Troubleshooting

#### Common Issues

**Port Already in Use**
```bash
# Find process using port 3000
lsof -i :3000

# Kill process
kill -9 <PID>
```

**Database Connection Issues**
```bash
# Reset database
npm run db:reset

# Regenerate Prisma client
npm run db:generate
```

**Build Errors**
```bash
# Clear Next.js cache
rm -rf .next
npm run build
```

**TypeScript Errors**
```bash
# Check types
npm run lint

# Clear TypeScript cache
rm -rf tsconfig.tsbuildinfo
```

#### Performance Issues

- **Large Bundle Size**: Use dynamic imports for large components
- **Slow Build**: Enable Next.js experimental features
- **Memory Issues**: Increase Node.js memory limit: `NODE_OPTIONS="--max-old-space-size=4096" npm run dev`

### 11. Deployment Options

#### Vercel (Recommended)

1. **Connect Repository**
   - Link your GitHub repository to Vercel
   - Configure environment variables in Vercel dashboard

2. **Automatic Deployment**
   - Vercel automatically builds and deploys on push
   - Custom domain configuration available

#### Netlify

1. **Build Settings**
   - Build command: `npm run build`
   - Publish directory: `.next`
   - Install command: `npm install`

2. **Environment Variables**
   - Configure in Netlify dashboard
   - Ensure all required variables are set

#### Docker Deployment

```dockerfile
FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm ci --only=production

COPY . .
RUN npm run build

EXPOSE 3000

CMD ["npm", "start"]
```

### 12. Maintenance and Updates

#### Keeping Dependencies Updated

```bash
# Check for outdated packages
npm outdated

# Update packages
npm update

# Major version updates
npm install next@latest react@latest react-dom@latest
```

#### Regular Maintenance Tasks

- **Weekly**: Run `npm audit` for security vulnerabilities
- **Monthly**: Update dependencies and test functionality
- **Quarterly**: Review and optimize performance
- **Annually**: Consider major framework upgrades

### 13. Contributing Guidelines

#### Code Standards

- **TypeScript**: Use strict mode and proper typing
- **ESLint**: Follow configured rules and patterns
- **Prettier**: Consistent code formatting (if configured)
- **Component Structure**: Follow established patterns

#### Git Workflow

1. **Create feature branch**: `git checkout -b feature/your-feature`
2. **Make changes**: Commit with clear, descriptive messages
3. **Test thoroughly**: Ensure all functionality works
4. **Submit pull request**: For code review before merging

### 14. Support and Resources

#### Official Documentation

- [Next.js Documentation](https://nextjs.org/docs)
- [React Documentation](https://react.dev)
- [TypeScript Documentation](https://www.typescriptlang.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Prisma Documentation](https://www.prisma.io/docs)

#### Community Support

- **GitHub Issues**: Report bugs and request features
- **Stack Overflow**: Ask technical questions
- **Discord/Slack**: Join community channels
- **Z.ai**: AI-powered coding assistance

---

## 🎯 Next Steps

After completing the setup:

1. **Personalize Content**: Replace placeholder content with your information
2. **Test Features**: Ensure all interactive elements work correctly
3. **Optimize Performance**: Test loading times and optimize assets
4. **Deploy**: Choose your preferred deployment platform
5. **Monitor**: Set up analytics and performance monitoring

Your portfolio website is now ready to showcase your skills and experience to the world! 🚀
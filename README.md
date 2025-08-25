🚀 Modern Portfolio Website
A stunning, feature-rich portfolio website built with Next.js 15, TypeScript, and cutting-edge web technologies. This project showcases advanced web development capabilities with 3D elements, smooth animations, PWA features, and a fully responsive design.

Portfolio Screenshot
TypeScript
Tailwind CSS
Framer Motion

🌟 Features
Core Features
🎨 Modern Design: Clean, professional UI with dark/light mode support
📱 Fully Responsive: Mobile-first design that works on all devices
⚡ High Performance: Optimized for speed with lazy loading and code splitting
🔍 SEO Optimized: Meta tags, structured data, and semantic HTML
♿ Accessible: WCAG compliant with proper ARIA labels and keyboard navigation
Advanced Features
🎮 3D Elements: Interactive 3D background using Three.js and React Three Fiber
👆 Touch Gestures: Swipe navigation support for mobile devices
📱 PWA Ready: Progressive Web App with offline functionality
🎭 Smooth Animations: Micro-interactions with Framer Motion
🔗 Interactive Timeline: Visual work experience timeline
📊 Project Showcase: Filterable project gallery with live demos
📄 Resume Download: One-click resume download functionality
💬 Real-time Features: Socket.IO integration for live updates
🎯 Contact Form: Functional contact form with validation
🚀 Quick Start
Prerequisites
Node.js 18.0.0 or higher
npm or yarn
Git
Installation
1. Clone the repository
   git clone https://github.com/yourusername/portfolio-website.git
   cd portfolio-website

2. Install dependencies
   npm install
   
3.Set up environment variables
  cp .env.example .env.local

  Then edit .env.local and add your configuration:

  DATABASE_URL="file:./db/custom.db"
  NEXTAUTH_SECRET="your-secret-here"
  NEXTAUTH_URL="http://localhost:3000"

4. Set up the database
   npm run db:generate
   npm run db:push

5.Start the development server
  npm run dev
  
6. Open your browser
   Navigate to http://localhost:3000

🛠️ Technology Stack

Core Framework
Next.js 15: React framework with App Router
React 19: UI library with concurrent features
TypeScript 5: Type-safe JavaScript
Tailwind CSS 4: Utility-first CSS framework

UI & Animation

shadcn/ui: High-quality, accessible components
Radix UI: Headless UI primitives
Framer Motion: Production-ready motion library
Lucide React: Beautiful icon library
next-themes: Dark/light mode support

3D & Interactive

Three.js: 3D graphics library
React Three Fiber: React renderer for Three.js
React Three Drei: Useful helpers for React Three Fiber
React Swipeable: Touch gesture library

Data & State

Prisma: Next-generation ORM
Zustand: Lightweight state management
TanStack Query: Server state management
React Hook Form: Performant forms
Zod: TypeScript-first schema validation

Backend & Real-time

NextAuth.js: Authentication solution
Socket.IO: Real-time bidirectional event-based communication
Prisma Client: Type-safe database client

Development Tools

ESLint: JavaScript linter
Tailwind CSS: Utility-first CSS framework
tsx: TypeScript execution
nodemon: Monitor for changes and restart server

🎨 Sections Overview

1. Hero Section

Animated name and title display
Call-to-action buttons
3D interactive background
Social media links

2. About Section

Personal introduction
Skills showcase with badges

Key achievements

3. Experience Section

Interactive timeline
Work history with company details
Role descriptions and dates

4. Projects Section

Filterable project gallery
Project cards with images and descriptions
Technology stack badges
Live demo modals
GitHub repository links

5. Skills Section

Categorized skill display
Progress bars for proficiency levels
Interactive hover effects

6. Contact Section

Contact form with validation
Social media links
Contact information
Email integration

📱 Responsive Design

The portfolio is fully responsive and optimized for:

Desktop: Full-featured experience with 3D elements
Tablet: Optimized layout with touch interactions
Mobile: Streamlined design with swipe gestures

🌐 PWA Features

Offline Support

Service worker for offline functionality
Cached assets for reliable performance
Offline fallback page
App-like Experience
Add to home screen capability
Custom app icons and splash screens
Full-screen mode support
Performance Optimizations
Lazy loading for images and components
Code splitting for faster initial load
Optimized bundle size

🚀 Deployment

Vercel (Recommended)

Push your code to GitHub
Connect your repository to Vercel
Configure environment variables
Deploy automatically on every push

Netlify

Build command: npm run build
Publish directory: .next
Configure environment variables
Connect your GitHub repository

Docker

FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["npm", "start"]

🎯 Customization

Personal Information

Update the following files with your information:

src/app/page.tsx: Main content and sections
src/components/Navigation.tsx: Navigation links
public/manifest.json: App metadata

Styling

src/app/globals.css: Global styles and custom CSS
tailwind.config.ts: Tailwind configuration
components.json: shadcn/ui configuration

Content

Replace placeholder images in public/images/
Update project data and experience
Customize color scheme and fonts

🔧 Available Scripts

# Development
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint

# Database
npm run db:push      # Push schema changes
npm run db:generate  # Generate Prisma client
npm run db:migrate   # Create and apply migrations
npm run db:reset     # Reset database

🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.


Development Workflow

Fork the repository
Create a feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request

📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

🙏 Acknowledgments

Next.js for the amazing React framework
Tailwind CSS for the utility-first CSS framework
shadcn/ui for the beautiful component library
Three.js for the 3D graphics capabilities
Framer Motion for the smooth animations

📧 Contact

Email: your.email@example.com
LinkedIn: linkedin.com/in/yourprofile
GitHub: github.com/yourusername
Twitter: @yourusername

⭐ If you find this project helpful, please consider giving it a star!

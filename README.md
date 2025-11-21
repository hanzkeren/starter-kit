# 🚀 Z.ai Next.js Starter Kit

A comprehensive, production-ready Next.js 15 starter kit with modern technologies, designed for rapid development with AI assistance from [Z.ai](https://chat.z.ai).

## 📋 Quick Start Guide

### 🛠️ Prerequisites
Before you begin, ensure you have:
- **Node.js 18+** installed
- **npm** or **yarn** package manager
- **Git** for version control

### 🚀 Getting Started

#### 1. **Install Dependencies**
```bash
npm install
```
This will install all required packages including Next.js 15, TypeScript, Tailwind CSS, and 40+ UI components.

#### 2. **Database Setup (Optional)**
If you want to use the database features:
```bash
# Generate Prisma client
npm run db:generate

# Push database schema (for development)
npm run db:push

# Run database migrations (for production)
npm run db:migrate
```

#### 3. **Start Development Server**
```bash
npm run dev
```
Your application will be available at [http://localhost:3000](http://localhost:3000)

#### 4. **Build for Production**
```bash
# Create production build
npm run build

# Start production server
npm start
```

## 🎯 Technology Stack

### Core Framework
- **⚡ Next.js 15** - React framework with App Router
- **📘 TypeScript 5** - Type-safe development
- **🎨 Tailwind CSS 4** - Utility-first CSS framework

### UI Components & Styling
- **🧩 shadcn/ui** - 40+ accessible components (Radix UI)
- **🎯 Lucide React** - Beautiful icon library
- **🌈 Framer Motion** - Animations and transitions
- **🎨 Next Themes** - Dark/light mode support

### Forms & Validation
- **🎣 React Hook Form** - Form management
- **✅ Zod** - Schema validation

### State Management & Data
- **🐻 Zustand** - Simple state management
- **🔄 TanStack Query** - Data fetching and caching
- **🌐 Axios** - HTTP client

### Database & Backend
- **🗄️ Prisma** - Modern ORM
- **🔐 NextAuth.js** - Authentication

### Advanced Features
- **📊 TanStack Table** - Data tables
- **🖱️ DND Kit** - Drag and drop
- **📊 Recharts** - Charts and visualizations
- **🌍 Next Intl** - Internationalization
- **🪝 ReactUse** - Essential React hooks

## 📁 Project Structure

```
zai/
├── 📄 README.md                    # This file - project guide
├── 📄 package.json                 # Dependencies and scripts
├── 📄 next.config.ts              # Next.js configuration
├── 📄 tailwind.config.ts          # Tailwind CSS config
├── 📄 tsconfig.json               # TypeScript configuration
├── 📄 components.json             # shadcn/ui component config
│
├── 📁 src/
│   ├── 📁 app/                    # Next.js App Router
│   │   ├── 📄 layout.tsx          # Root layout component
│   │   ├── 📄 page.tsx            # Home page
│   │   └── 📁 api/                # API routes
│   │
│   ├── 📁 components/             # React components
│   │   └── 📁 ui/                 # shadcn/ui components (40+)
│   │
│   ├── 📁 hooks/                  # Custom React hooks
│   │   ├── 📄 use-mobile.ts       # Mobile detection
│   │   └── 📄 use-toast.ts        # Toast notifications
│   │
│   └── 📁 lib/                    # Utilities
│       ├── 📄 utils.ts            # Utility functions
│       └── 📄 db.ts               # Database connection
│
├── 📁 prisma/
│   └── 📄 schema.prisma           # Database schema
│
└── 📁 public/                     # Static assets
    ├── 📄 logo.svg                # App logo
    └── 📄 robots.txt              # SEO file
```

## 🛠️ Available Scripts

```bash
# Development
npm run dev          # Start development server with hot reload
npm run lint         # Run ESLint for code quality

# Database
npm run db:generate  # Generate Prisma client
npm run db:push      # Push schema to database (dev)
npm run db:migrate   # Run database migrations (prod)
npm run db:reset     # Reset database

# Production
npm run build        # Create optimized production build
npm start            # Start production server
```

## 🎨 Using UI Components

### Import Components
```tsx
import { Button, Card, Input } from "@/components/ui";
import { useToast } from "@/hooks/use-toast";
```

### Available Components
This starter kit includes 40+ shadcn/ui components:

#### **Basic Components**
- `Button`, `Input`, `Textarea`, `Select`
- `Card`, `Badge`, `Avatar`, `Separator`
- `Label`, `Checkbox`, `Switch`, `Radio Group`

#### **Navigation**
- `Breadcrumb`, `Menubar`, `Navigation Menu`
- `Pagination`, `Tabs`

#### **Overlays & Dialogs**
- `Dialog`, `Sheet`, `Popover`, `Tooltip`
- `Alert Dialog`, `Hover Card`, `Drawer`

#### **Data Display**
- `Table`, `Skeleton`, `Progress`, `Calendar`
- `Carousel`, `Chart`, `Toggle`

#### **Feedback**
- `Alert`, `Toast`, `Sonner` (toast notifications)

## 🚀 Building Your First Feature

### 1. **Create a New Page**
```tsx
// src/app/about/page.tsx
export default function AboutPage() {
  return (
    <div className="container mx-auto py-8">
      <h1 className="text-2xl font-bold">About Us</h1>
      <p className="mt-4 text-gray-600">Learn more about our company.</p>
    </div>
  );
}
```

### 2. **Add a Component**
```tsx
// src/components/FeatureCard.tsx
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

export function FeatureCard({ title, description }: {
  title: string;
  description: string;
}) {
  return (
    <Card>
      <CardHeader>
        <CardTitle>{title}</CardTitle>
      </CardHeader>
      <CardContent>
        <p>{description}</p>
      </CardContent>
    </Card>
  );
}
```

### 3. **Use Database (Optional)**
```tsx
// src/app/api/users/route.ts
import { PrismaClient } from '@prisma/client';

const prisma = new PrismaClient();

export async function GET() {
  const users = await prisma.user.findMany();
  return Response.json(users);
}
```

## 🤖 AI Development with Z.ai

This starter kit is optimized for AI-assisted development:

### **What Z.ai Can Help With:**
- **🏗️ Component Generation**: "Create a responsive dashboard card component"
- **🎨 UI Design**: "Add a dark mode toggle with smooth animation"
- **📊 Data Features**: "Build a data table with sorting and filtering"
- **🔧 Bug Fixes**: "Fix the TypeScript error in the form component"
- **📝 Documentation**: "Add JSDoc comments to the utility functions"

### **Getting Help:**
1. Visit [chat.z.ai](https://chat.z.ai)
2. Describe what you want to build
3. Copy-paste the generated code into your project
4. Ask for modifications or improvements

## 🌍 Deployment

### **Vercel (Recommended)**
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

### **Docker**
```bash
# Build image
docker build -t my-app .

# Run container
docker run -p 3000:3000 my-app
```

### **Traditional Server**
```bash
npm run build
npm start
```

## 🔧 Customization

### **Adding New UI Components**
```bash
# Install new shadcn/ui component
npx shadcn-ui@latest add [component-name]
```

### **Environment Variables**
Create `.env.local`:
```env
DATABASE_URL="postgresql://..."
NEXTAUTH_SECRET="your-secret"
NEXTAUTH_URL="http://localhost:3000"
```

---

## 🤝 Need Help?

- **📚 Documentation**: Check component code in `src/components/ui/`
- **🤖 AI Assistant**: Visit [chat.z.ai](https://chat.z.ai) for coding help
- **🐛 Issues**: Check console for errors and ask Z.ai for solutions

**Happy coding! 🚀**

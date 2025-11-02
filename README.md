# Professional Dashboard

A **complete professional dashboard** built entirely with **Tailwind CSS** and **React/Next.js**.  
It can be easily integrated into any React or Next.js project.

---

## ✨ Features

### 🎨 Design & UI

- **Fully Responsive** — Perfect on mobile, tablet, and desktop
- **Dark/Light/System Mode** — With a theme switcher
- **Professional Design** — Clean and modern UI
- **Pure Tailwind CSS** — No external UI libraries

### 🔐 Authentication

- **Login System** — Email and password support
- **Forgot Password Flow** — Includes OTP verification
- **OTP Component** — Supports paste on all devices

### 📊 Dashboard Features

- **Sidebar Navigation** — Collapsible and expandable
- **Responsive Header** — User profile dropdown included
- **Mobile Menu** — With blur background
- **Data Table** — Search and pagination supported

### 🔍 Search & Pagination

- **URL-Based Search** — Server-side pagination support
- **Reusable Pagination Component** — Works across pages
- **Debounced Search** — Performance optimized

### 👥 Role-Based Access

- **Admin, Manager, User Roles** — Fully customizable
- **Permission System** — Separate access for each role
- **Protected Routes** — Prevents unauthorized access

### 📱 Mobile Optimization

- **Touch-Friendly** — All interactions optimized for mobile
- **Responsive Layout** — Adapts to all screen sizes
- **Fast Loading** — Minimal bundle size

---

## 🚀 Getting Started

### Installation

```bash
# Clone or download
git clone <repository-url>
cd professional-dashboard

# Install dependencies
npm install

# Run development server
npm run dev
```

Then open your browser and navigate to [http://localhost:3000](http://localhost:3000).

### Demo Credentials

**Admin Account:**

```
Email: admin@example.com
Password: admin123
```

**Manager Account:**

```
Email: manager@example.com
Password: manager123
```

**User Account:**

```
Email: user@example.com
Password: user123
```

---

## 📁 Project Structure

```plaintext
professional-dashboard/
├── app/
│   ├── layout.tsx                 # Root layout
│   ├── page.tsx                   # Home page (redirect)
│   ├── globals.css                # Global styles and theme
│   ├── login/
│   │   └── page.tsx              # Login page
│   ├── forgot-password/
│   │   └── page.tsx              # Forgot password page
│   └── dashboard/
│       ├── layout.tsx             # Dashboard layout
│       ├── page.tsx               # Dashboard home
│       ├── users/
│       │   └── page.tsx           # User list
│       ├── analytics/
│       │   └── page.tsx           # Analytics page
│       ├── reports/
│       │   └── page.tsx           # Reports page
│       ├── settings/
│       │   └── page.tsx           # Settings page
│       ├── profile/
│       │   └── page.tsx           # Profile page
│       └── unauthorized/
│           └── page.tsx           # Access denied page
├── components/
│   ├── icons.tsx                  # Custom SVG icons
│   └── dashboard/
│       ├── layout.tsx             # Dashboard layout component
│       ├── sidebar.tsx            # Sidebar navigation
│       ├── header.tsx             # Header component
│       ├── pagination.tsx         # Pagination component
│       ├── search-bar.tsx         # Search bar component
│       ├── data-table.tsx         # Data table component
│       └── protected-route.tsx    # Protected route component
├── providers/
│   └── theme-provider.tsx         # Theme provider
├── hooks/
│   └── use-auth.ts                # Authentication hook
├── lib/
│   ├── auth.ts                    # Authentication utilities
│   └── constants.ts               # Constants and demo data
├── package.json                   # Dependencies (latest versions)
├── tsconfig.json                  # TypeScript config
├── next.config.mjs                # Next.js config
├── postcss.config.mjs             # PostCSS config
├── .eslintrc.json                 # ESLint config
└── README.md                      # This file
```

---

## 🎯 Core Components

### 1. **Sidebar**

- Collapse/Expand functionality
- Role-based menu filtering
- Active link highlighting
- Mobile drawer mode with blur background

### 2. **Header**

- Theme switcher (Light/Dark/System)
- User profile dropdown
- Logout functionality
- Mobile menu toggle

### 3. **Pagination**

- URL-based pagination
- Smart page number display
- Jump to first/last page
- Responsive design

### 4. **SearchBar**

- Debounced search
- URL parameter sync
- Clear button
- Real-time filtering

### 5. **DataTable**

- Generic type support
- Custom render functions
- Loading state
- Empty state

### 6. **ProtectedRoute**

- Role-based access check
- Automatic redirect
- Loading state

---

## 🎨 Theme Customization

Defined in `app/globals.css`:

```css
@theme inline {
  --color-primary: #3b82f6;
  --color-primary-dark: #1e40af;
  --color-primary-light: #60a5fa;

  --color-background: #ffffff;
  --color-background-secondary: #f9fafb;
  --color-foreground: #111827;

  /* Dark mode */
  --color-dark-background: #0f172a;
  --color-dark-background-secondary: #1e293b;
  --color-dark-foreground: #f1f5f9;

  /* Accent colors */
  --color-success: #10b981;
  --color-warning: #f59e0b;
  --color-error: #ef4444;
}
```

---

## 🔐 Authentication Flow

### Login

1. Enter email and password
2. User data saved to `localStorage`
3. Redirected to dashboard

### Forgot Password

1. Enter email
2. Receive OTP (demo: any 6 digits)
3. Set a new password
4. Redirect to login page

---

## 👥 Role-Based Access

### Admin

- Access all pages
- Manage users
- Access settings

### Manager

- View Dashboard, Users, Analytics, and Reports
- No access to settings

### User

- View Dashboard and Profile only

---

## 📦 Dependencies (Latest Versions)

```json
{
  "dependencies": {
    "next": "^15.5.4",
    "react": "^19.1.0",
    "react-dom": "^19.1.0",
    "next-themes": "^0.4.6",
    "lucide-react": "^0.454.0",
    "date-fns": "^4.1.0"
  },
  "devDependencies": {
    "typescript": "^5",
    "tailwindcss": "^4.1.9",
    "@tailwindcss/postcss": "^4.1.9"
  }
}
```

---

## 🎓 Code Quality

- ✅ TypeScript support (latest)
- ✅ ESLint configured
- ✅ Semantic HTML
- ✅ ARIA attributes
- ✅ Performance optimized
- ✅ No build errors
- ✅ No lint errors

---

## 🔧 Customization Guide

### Add a New Page

```tsx
// app/dashboard/new-page/page.tsx
"use client";

import { ProtectedRoute } from "@/components/dashboard/protected-route";

export default function NewPage() {
  return (
    <ProtectedRoute requiredRoles={["admin"]}>
      <div className="space-y-6">
        <h1 className="text-3xl font-bold">New Page</h1>
        {/* Content here */}
      </div>
    </ProtectedRoute>
  );
}
```

### Add a Navigation Item

Edit the `SIDEBAR_ITEMS` array in `lib/constants.ts`:

```tsx
export const SIDEBAR_ITEMS = [
  // ... existing items
  {
    id: "new-page",
    label: "New Page",
    icon: "YourIcon",
    href: "/dashboard/new-page",
    roles: ["admin"],
  },
];
```

### Customize Role Permissions

Edit `rolePermissions` in `lib/auth.ts`:

```tsx
export const rolePermissions: Record<UserRole, string[]> = {
  admin: ["view_dashboard", "manage_users", "new_permission"],
  manager: ["view_dashboard", "view_users"],
  user: ["view_dashboard"],
};
```

---

## 🐛 Troubleshooting

### Stuck on Login Page?

- Check localStorage: `localStorage.getItem('user')`
- Inspect browser console for errors

### Theme Not Changing?

- Check localStorage: `localStorage.getItem('theme')`
- Refresh browser

### Pagination Not Working?

- Check URL parameters: `?page=1&search=query`
- Verify data length

### npm install Errors?

- Delete `node_modules`
- Run `npm cache clean --force`
- Reinstall with `npm install`

---

## 🚀 Deployment

### Deploy to Vercel

```bash
npm run build
vercel deploy
```

### Other Platforms

```bash
npm run build
# Output: .next folder
```

---

## 📝 License

This project is **open-source** and **free to use**.

## 🤝 Contribution

Suggestions and pull requests are welcome!

---

**Happy Coding! 🚀**
**Husneara!**


For more details, check [SETUP.md](./SETUP.md) and [QUICK_REFERENCE.md](./QUICK_REFERENCE.md).

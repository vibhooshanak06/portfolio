# Portfolio Website
A modern, elegant portfolio website featuring a clean dark theme, smooth animations, and contemporary UI patterns.

## 🎨 Design Features

- **Dark-First Design**: Beautiful dark theme (#0A0A0F) with subtle gradients
- **Modern Typography**: Inter font family for clean, professional look
- **Smooth Animations**: Subtle transitions and hover effects throughout
- **Glassmorphism**: Frosted glass effects on navigation and cards
- **Responsive Layout**: Fully responsive across all devices
- **Clean UI Components**: Card-based layouts with elegant borders

## 🎯 Color Scheme (Nivora Style)

- **Primary**: Indigo (#6366F1)
- **Accent**: Emerald (#10B981)
- **Background**: Deep Dark (#0A0A0F)
- **Secondary BG**: (#111118)
- **Card BG**: (#16161F)
- **Text Primary**: White (#FFFFFF)
- **Text Secondary**: Gray (#A1A1AA)

## 📦 Tech Stack

- Vue.js 3
- Vue Router 4
- SCSS for styling
- Font Awesome 6 icons
- Inter font family (Google Fonts)

## 🚀 Getting Started

### Installation

```bash
# Install dependencies
npm install

# Run development server
npm run serve

# Build for production
npm run build
```

## 📁 Project Structure

```
src/
├── components/
│   ├── Navbar.vue          # Modern navigation with glassmorphism
│   └── Footer.vue          # Clean footer with social links
├── views/
│   ├── Home.vue           # Hero section with featured work
│   ├── About.vue          # About page with timeline
│   ├── Experience.vue     # Work experience
│   ├── Skills.vue         # Technical skills showcase
│   ├── Projects.vue       # Project portfolio
│   └── Contact.vue        # Contact form
├── router/
│   └── index.js           # Vue Router configuration
├── styles/
│   └── global.scss        # Global styles with Nivora design system
├── App.vue                # Main app component
└── main.js               # App entry point
```

## ✨ Key Features

### Navigation
- Fixed navbar with blur backdrop
- Smooth scroll behavior
- Active route indicators
- Mobile-responsive hamburger menu

### Home Page
- Hero section with gradient background
- Availability badge with pulse animation
- Stats section with gradient numbers
- Featured work showcase
- Skills overview grid

### Components
- Hover effects with smooth transitions
- Card components with border animations
- Button variants (primary, outline, ghost)
- Responsive grid layouts

### Animations
- Fade in up animations
- Scroll indicators
- Hover transforms
- Smooth color transitions

## 🎨 Customization

### Update Colors
Edit `src/styles/global.scss`:

```scss
:root {
  --primary: #6366F1;
  --accent: #10B981;
  --bg-primary: #0A0A0F;
  // ... customize other colors
}
```

### Update Content
- **Home.vue**: Update hero text, featured projects, skills
- **About.vue**: Modify personal story, values, timeline
- **Projects.vue**: Add your projects
- **Skills.vue**: Update technical skills
- **Contact.vue**: Update contact information

### Typography
The portfolio uses Inter font. To change:
1. Update Google Fonts link in `public/index.html`
2. Update font-family in `src/styles/global.scss`

## 📱 Responsive Design

- Desktop: Full layout with multi-column grids
- Tablet (< 968px): Adjusted layouts
- Mobile (< 640px): Single column, stacked elements

## 🌐 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## 🎯 Design Inspiration

This portfolio is inspired by [Nivora](https://nivora.framer.website/), featuring:
- Minimalist dark aesthetic
- Subtle gradient accents
- Clean typography
- Smooth micro-interactions
- Professional spacing and layout

## 📄 License

This project is open source and available under the MIT License.

---

**Built with ❤️ using Vue.js** | Inspired by Nivora Design


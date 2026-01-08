# Vue.js Portfolio

A stunning, responsive portfolio website built with Vue.js featuring a beautiful purple theme, dark/light mode toggle, and smooth animations.

## Features

- 🎨 **Beautiful Purple Theme** - Elegant gradient design with purple color scheme
- 🌙 **Dark/Light Mode** - Toggle between themes with smooth transitions
- 📱 **Fully Responsive** - Works perfectly on all devices
- ✨ **Smooth Animations** - CSS animations and transitions throughout
- 🚀 **Modern Tech Stack** - Vue.js 3, Vue Router, SCSS
- 📄 **Multiple Pages** - Home, About, Experience, Skills, Interests, Projects, Contact
- 🎯 **Perfect UI/UX** - Clean, modern, and user-friendly interface

## Pages

1. **Home** - Hero section with introduction and featured projects
2. **About** - Personal story, values, timeline, and fun facts
3. **Experience** - Work experience, education, certifications, and skills progress
4. **Skills** - Technical skills, tools, and proficiency levels
5. **Interests** - Hobbies, interests, and activities outside of coding
6. **Projects** - Academic and personal projects showcase
7. **Contact** - Contact form and social links

## Tech Stack

- **Frontend**: Vue.js 3
- **Routing**: Vue Router 4
- **Styling**: SCSS with CSS custom properties
- **Icons**: Font Awesome
- **Fonts**: Google Fonts (Poppins)

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd portfolio
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm run serve
   # or
   npm run dev
   ```

4. **Build for production**
   ```bash
   npm run build
   ```

## Project Structure

```
src/
├── components/
│   ├── Navbar.vue          # Navigation component
│   └── Footer.vue          # Footer component
├── views/
│   ├── Home.vue           # Home page
│   ├── About.vue          # About page
│   ├── Experience.vue     # Experience page
│   ├── Skills.vue         # Skills page
│   ├── Interests.vue      # Interests page
│   ├── Projects.vue       # Projects page
│   └── Contact.vue        # Contact page
├── router/
│   └── index.js           # Vue Router configuration
├── styles/
│   └── global.scss        # Global styles and variables
├── App.vue                # Main app component
└── main.js               # App entry point
```

## Customization

### Colors
The color scheme is defined in `src/styles/global.scss` using CSS custom properties:

```scss
:root {
  --primary-purple: #8B5CF6;
  --secondary-purple: #A78BFA;
  --accent-purple: #C4B5FD;
  --dark-purple: #6D28D9;
  --light-purple: #EDE9FE;
  // ... other colors
}
```

### Content
Update the content in each Vue component to match your personal information:

- **Personal Info**: Update name, title, description in `Home.vue`
- **About**: Modify story, values, timeline in `About.vue`
- **Experience**: Add your work experience and education in `Experience.vue`
- **Skills**: Update your technical skills and tools in `Skills.vue`
- **Projects**: Add your projects in `Projects.vue`
- **Contact**: Update contact information in `Contact.vue`

### Animations
The portfolio includes several CSS animations:
- `fadeInUp`, `fadeInLeft`, `fadeInRight` - Entrance animations
- `float` - Floating animation for elements
- `pulse` - Pulsing effect
- Hover effects on cards and buttons

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Performance

- Optimized images and assets
- Efficient CSS with custom properties
- Smooth animations with CSS transforms
- Responsive design with mobile-first approach

## License

This project is open source and available under the [MIT License](LICENSE).

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Support

If you like this portfolio template, please give it a ⭐ on GitHub!

---

**Made with ❤️ using Vue.js**
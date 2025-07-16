# 🏴‍☠️ Flags Game

A modern and interactive flag guessing game built with Vue 3 and Vite. Test your knowledge of world flags by identifying countries from their flag images!

<img width="1338" height="921" alt="image" src="https://github.com/user-attachments/assets/cefe11be-74a4-4489-aaa4-6214e5a749f9" />



## ✨ Features

- **🎯 Interactive Gameplay**: Guess countries from flag images with multiple choice options
- **📊 Real-time Score Tracking**: Keep track of correct and incorrect answers
- **🎨 Modern UI/UX**: Beautiful, responsive design that works on all devices
- **🌍 Global Flag Database**: Uses FlagCDN API for high-quality flag images
- **📱 Fully Responsive**: Optimized for desktop, tablet, and mobile devices
- **⚡ Fast Performance**: Built with Vue 3 and Vite for optimal performance
- **🎮 Engaging Experience**: Sweet alerts for feedback and smooth animations

## 🚀 Technologies Used

- **Vue 3** - Progressive JavaScript framework
- **Vite** - Fast build tool and development server
- **FlagCDN API** - High-quality flag images from around the world
- **SweetAlert2** - Beautiful, responsive, customizable alert dialogs
- **CSS3** - Modern styling with flexbox and responsive design

## 📋 Prerequisites

Before running this project, make sure you have the following installed:

- **Node.js** (version 16 or higher)
- **npm** or **yarn** package manager

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/flags-game.git
   cd flags-game
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start the development server**
   ```bash
   npm run dev
   # or
   yarn dev
   ```

4. **Open your browser**
   Navigate to `http://localhost:5173` to see the application running.

## 🏗️ Build for Production

To create a production build:

```bash
npm run build
# or
yarn build
```

The built files will be in the `dist` directory.

## 🎮 How to Play

1. **Start the Game**: The game loads with a random country flag
2. **Read Instructions**: Check the instructions panel on the left
3. **Make Your Guess**: Click on one of the three country options (1, 2, or 3)
4. **Get Feedback**: Receive immediate feedback with beautiful alerts
5. **Track Your Score**: Monitor your progress with the score panel
6. **Continue Playing**: New flags appear automatically after each correct answer

## 🌐 API Integration

This project uses the **FlagCDN API** to display high-quality flag images:

- **API Endpoint**: `https://flagcdn.com/256x192/{country-code}.png`
- **Image Quality**: 256x192 pixels for optimal display
- **Country Codes**: ISO 3166-1 alpha-2 country codes
- **No API Key Required**: Free to use with no authentication needed

### Example Usage:
```javascript
// Flag image URL format
const flagUrl = `https://flagcdn.com/256x192/${countryCode}.png`
```

## 📁 Project Structure

```
flags-game/
├── public/
│   └── vite.svg
├── src/
│   ├── components/
│   │   ├── FlagCard.vue          # Flag display component
│   │   ├── InstructionsCard.vue   # Game instructions
│   │   ├── OptionCard.vue         # Answer options
│   │   ├── Score.vue              # Score tracking
│   │   └── footer.vue             # Footer component
│   ├── data.js                    # Country and flag data
│   ├── App.vue                    # Main application component
│   ├── main.js                    # Vue application entry point
│   └── style.css                  # Global styles
├── index.html
├── package.json
├── vite.config.js
└── README.md
```

## 🎨 Key Components

### FlagCard.vue
- Displays the current flag image
- Responsive design with proper aspect ratio
- Integrates with FlagCDN API

### InstructionsCard.vue
- Shows game instructions
- Sticky positioning on desktop
- Responsive layout

### OptionCard.vue
- Interactive answer buttons
- Hover effects and animations
- Click handlers for game logic

### Score.vue
- Real-time score tracking
- Separate counters for correct/incorrect answers
- Responsive design

## 📱 Responsive Design

The application is fully responsive and optimized for:

- **Desktop** (1024px+): Side-by-side layout with sticky instructions
- **Tablet** (768px - 1024px): Adjusted spacing and sizing
- **Mobile** (480px - 768px): Stacked layout for better usability
- **Small Mobile** (<480px): Compact design with smaller elements

## 🔧 Development

### Available Scripts

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Lint code
npm run lint
```

### Customization

- **Add New Countries**: Modify the `flags_and_countries` object in `src/data.js`
- **Change Styling**: Update CSS variables and component styles
- **Modify Game Logic**: Edit the game logic in `src/App.vue`

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Gabriel Penke**
- LinkedIn: [Gabriel Penke](https://www.linkedin.com/in/gabriel-penke-953771206/)
- GitHub: [@yourusername]([https://github.com/yourusername](https://github.com/GabrielPenke292))

## 🙏 Acknowledgments

- **FlagCDN** for providing high-quality flag images
- **Vue.js** team for the amazing framework
- **Vite** team for the fast build tool
- **SweetAlert2** for beautiful alert dialogs

## 📞 Support

If you have any questions or need help with the project, feel free to:

- Open an issue on GitHub
- Contact the author via LinkedIn
- Check the documentation above

---

**Happy Gaming! 🎮🏴‍☠️**

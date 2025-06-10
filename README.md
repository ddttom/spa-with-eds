# SPA with Adobe Edge Delivery Services

A lightweight, high-performance Single Page Application built with vanilla JavaScript and modern ES modules for Adobe Edge Delivery Services (EDS). This project demonstrates how to build dynamic, interactive experiences while maintaining excellent performance scores through modern web development practices.

## 🚀 Features

- **Framework-less Architecture**: Pure vanilla JavaScript with ES modules
- **Adobe EDS Integration**: Leverages EDS query-index and .plain.html endpoints
- **Performance-First**: Optimized for perfect Lighthouse scores
- **Progressive Enhancement**: Mobile-first approach with desktop enhancements
- **Modern JavaScript**: ES6+ features without TypeScript complexity
- **Responsive Design**: Adapts seamlessly across all device sizes
- **Lazy Loading**: Optimized image loading for better performance

## 🏗️ Architecture Principles

- **Hybrid Approach**: Pure EDS for landing pages, SPA functionality for interactive components
- **Content-First**: Each piece of content is a full EDS page with its own URL
- **Security Hardened**: Proper application security without heavy dependencies
- **Minimal Build Steps**: No complex build processes or preprocessors
- **Clear Organization**: Well-structured modules and comprehensive documentation

## 📦 Project Structure

```
spa-with-eds/
├── blocks/
│   └── slide-builder/          # Interactive slide gallery component
│       ├── slide-builder.js    # Main component logic
│       ├── slide-builder.css   # Component styles
│       └── README.md           # Component documentation
├── .eslintrc.js               # ESLint configuration
├── .gitignore                 # Git ignore rules
├── .hintrc                    # Webhint configuration
└── .markdownlint.json         # Markdown linting rules
```

## 🛠️ Development Requirements

- **Modern JavaScript**: ES modules without TypeScript
- **Pure CSS**: No preprocessors or build-heavy frameworks
- **Simplicity Focus**: Minimal dependencies and build steps
- **Performance Oriented**: Lazy loading and efficient DOM manipulation
- **Security First**: Proper application hardening practices
- **Documentation**: Comprehensive code documentation and testing

## 🚦 Getting Started

### Prerequisites

- Modern browser with ES6+ support
- Adobe Edge Delivery Services setup
- Basic understanding of EDS concepts

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ddttom/spa-with-eds.git
   cd spa-with-eds
   ```

2. Set up your EDS environment according to Adobe's documentation

3. Configure your content structure:
   - Create slide pages in your Google Drive
   - Set up query-index spreadsheet
   - Publish your pages

### Usage

Add blocks to your EDS pages:

```html
<div class="slide-builder"></div>
```

The component will automatically:
- Fetch data from your query-index endpoint
- Load content progressively based on device capabilities
- Optimize images with WebP support
- Provide interactive slide navigation

## 🎯 Components

### Slide Builder Block

A responsive slide gallery component that demonstrates:
- **Content Management**: Uses EDS pages as slide content
- **Performance**: Lazy loading and conditional content fetching
- **Interactivity**: Click-to-expand functionality
- **Responsive**: Mobile-first design with desktop enhancements

See [`blocks/slide-builder/README.md`](blocks/slide-builder/README.md) for detailed documentation.

## 🔧 Configuration

### ESLint Setup

The project uses ESLint for code quality:

```bash
npm run lint
```

### Browser Support

- Modern browsers with ES6+ support
- Intersection Observer API
- WebP detection for progressive enhancement
- DOMParser for content extraction

## 📈 Performance

This project prioritizes performance through:

- **Zero Framework Overhead**: Pure vanilla JavaScript
- **Lazy Loading**: Images load only when needed
- **Progressive Enhancement**: Essential features for all, enhancements for capable devices
- **Efficient DOM Manipulation**: Minimal reflows and repaints
- **Optimized Assets**: WebP images with fallbacks

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details on:

- Code style and standards
- Development workflow
- Testing requirements
- Pull request process

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔒 Security

For security concerns, please review our [Security Policy](SECURITY.md) and report vulnerabilities responsibly.

## 📚 Documentation

- [Slide Builder Component](blocks/slide-builder/README.md)
- [Contributing Guidelines](CONTRIBUTING.md)
- [Code of Conduct](CODE_OF_CONDUCT.md)
- [Security Policy](SECURITY.md)

## 🌟 Acknowledgments

- Adobe Edge Delivery Services team for the excellent platform
- The web standards community for modern JavaScript practices
- Contributors who help improve this project

---

Built with ❤️ using vanilla JavaScript and modern web standards.

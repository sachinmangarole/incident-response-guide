# Contributing to Production Incident Response Guide

First off, thank you for considering contributing to this project! 🎉

This guide is built by engineers, for engineers. Every contribution—whether it's fixing a typo, adding a new debugging technique, or sharing your incident war story—makes this resource better for the entire community.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Style Guidelines](#style-guidelines)
- [Commit Message Guidelines](#commit-message-guidelines)
- [Pull Request Process](#pull-request-process)
- [Community](#community)

---

## 📜 Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inspiring community for all. Please be respectful and constructive in all interactions.

### Our Standards

**Examples of behavior that contributes to a positive environment:**

- ✅ Using welcoming and inclusive language
- ✅ Being respectful of differing viewpoints and experiences
- ✅ Gracefully accepting constructive criticism
- ✅ Focusing on what is best for the community
- ✅ Showing empathy towards other community members

**Examples of unacceptable behavior:**

- ❌ Trolling, insulting/derogatory comments, and personal or political attacks
- ❌ Public or private harassment
- ❌ Publishing others' private information without explicit permission
- ❌ Other conduct which could reasonably be considered inappropriate

---

## 🤝 How Can I Contribute?

There are many ways to contribute to this project:

### 1. 🐛 Report Bugs

Found a bug? Please create an issue with:

- **Clear title** describing the problem
- **Steps to reproduce** the issue
- **Expected behavior** vs **actual behavior**
- **Screenshots** (if applicable)
- **Browser/Device information**

**Example:**
```
Title: Mobile navigation menu not closing on phase selection

Steps to reproduce:
1. Open the guide on mobile (iPhone 14, Safari)
2. Tap the menu button to open phase selector
3. Select a different phase
4. Menu remains open instead of closing

Expected: Menu should close after selection
Actual: Menu stays open
```

### 2. 💡 Suggest Enhancements

Have an idea to make this guide better? Open an issue with:

- **Clear description** of the enhancement
- **Why it would be useful** to the community
- **Possible implementation** approach (optional)
- **Examples or mockups** (if applicable)

### 3. 📝 Improve Documentation

- Fix typos or grammatical errors
- Clarify confusing sections
- Add more examples or real-world scenarios
- Improve code comments
- Translate content to other languages

### 4. 🔧 Add New Features

Great ideas for new features:

- Additional incident response phases or sub-steps
- New debugging techniques and tools
- Integration examples (PagerDuty, Slack, etc.)
- Dark/light theme toggle
- Downloadable PDF version
- Video walkthroughs
- Interactive demos or simulations

### 5. 🎨 Improve Design

- Enhance mobile responsiveness
- Improve accessibility (ARIA labels, keyboard navigation)
- Add animations or micro-interactions
- Create new color themes
- Optimize performance

### 6. 🌍 Translate

Help make this guide accessible to non-English speakers:

- Translate the entire guide to your language
- Create language-specific versions
- Add i18n support

---

## 🚀 Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- A text editor (VS Code, Sublime Text, etc.)
- Basic knowledge of HTML, CSS, and JavaScript
- Git installed on your machine

### Fork and Clone

1. **Fork the repository** by clicking the "Fork" button at the top right
2. **Clone your fork** to your local machine:

```bash
git clone https://github.com/sachinmangarole/incident-response-guide.git
cd incident-response-guide
```

3. **Add upstream remote** to stay in sync with the original repo:

```bash
git remote add upstream https://github.com/sachinmangarole/incident-response-guide.git
```

4. **Create a new branch** for your contribution:

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/your-bug-fix
```

---

## 💻 Development Workflow

### Local Development

Since this is a static HTML page, development is straightforward:

1. **Open `index.html`** in your browser
2. **Make changes** to the HTML/CSS/JavaScript
3. **Refresh the browser** to see your changes
4. **Test on multiple devices** (use browser dev tools for mobile simulation)

### Testing Checklist

Before submitting your PR, please ensure:

- ✅ **Visual testing**: Check on desktop, tablet, and mobile
- ✅ **Browser compatibility**: Test on Chrome, Firefox, Safari, Edge
- ✅ **Responsive design**: All breakpoints work correctly
- ✅ **Functionality**: All interactive elements work as expected
- ✅ **Accessibility**: Keyboard navigation works, proper ARIA labels
- ✅ **Performance**: Page loads quickly, no console errors
- ✅ **Code quality**: Clean, commented, follows style guidelines

### Browser Testing Matrix

| Browser | Desktop | Mobile |
|---------|---------|--------|
| Chrome | ✅ | ✅ |
| Firefox | ✅ | ✅ |
| Safari | ✅ | ✅ |
| Edge | ✅ | N/A |

---

## 🎨 Style Guidelines

### HTML

- Use **semantic HTML5** elements
- Keep structure **clean and logical**
- Add **comments** for complex sections
- Use **proper indentation** (2 spaces)

```html
<!-- Good -->
<section class="content-section">
  <h2>Section Title</h2>
  <p>Content here</p>
</section>

<!-- Avoid -->
<div class="content-section"><h2>Section Title</h2><p>Content here</p></div>
```

### CSS

- Follow **mobile-first** approach
- Use **CSS custom properties** for theming when possible
- Keep selectors **specific but not overly nested**
- Add **comments** for complex styles
- Use **consistent spacing** (2 spaces)

```css
/* Good */
.content-section {
  padding: clamp(1rem, 3vw, 2rem);
  background: #1e293b;
  border-radius: 0.75rem;
}

/* Avoid deeply nested selectors */
.container .content .section .header .title {
  font-size: 2rem;
}
```

### JavaScript

- Use **modern ES6+** syntax
- Keep functions **small and focused**
- Add **descriptive comments**
- Use **camelCase** for variables and functions
- Handle **errors gracefully**

```javascript
// Good
function toggleStep(phaseIndex, stepIndex) {
  const content = document.getElementById(`content-${phaseIndex}-${stepIndex}`);
  const toggle = document.getElementById(`toggle-${phaseIndex}-${stepIndex}`);
  
  if (!content || !toggle) {
    console.error('Element not found');
    return;
  }
  
  content.classList.toggle('active');
  toggle.textContent = content.classList.contains('active') ? '−' : '+';
}

// Avoid
function t(p,s){var c=document.getElementById('content-'+p+'-'+s);c.classList.toggle('active');}
```

### Content Guidelines

When adding or editing content:

- Use **clear, concise language**
- Write in **active voice**
- Include **real-world examples** when possible
- Add **specific tools and commands**
- Keep **consistent tone** (professional but approachable)

---

## 📝 Commit Message Guidelines

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification.

### Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation changes
- **style**: Code style changes (formatting, missing semi-colons, etc.)
- **refactor**: Code refactoring without changing functionality
- **perf**: Performance improvements
- **test**: Adding or updating tests
- **chore**: Maintenance tasks

### Examples

```bash
# Good commit messages
feat(diagnose): add Kubernetes debugging commands
fix(mobile): resolve phase selector not closing on selection
docs(readme): add troubleshooting section
style(css): improve mobile responsive breakpoints
refactor(js): simplify phase navigation logic

# Include description for complex changes
feat(accessibility): add keyboard navigation support

Added keyboard shortcuts for phase navigation:
- Arrow keys to move between phases
- Enter to expand/collapse steps
- Escape to close mobile menu

Fixes #42
```

---

## 🔀 Pull Request Process

### Before Submitting

1. **Sync with upstream** to avoid conflicts:

```bash
git fetch upstream
git rebase upstream/main
```

2. **Test thoroughly** using the checklist above

3. **Update documentation** if needed (README, inline comments)

4. **Check for console errors** and fix them

### Submitting Your PR

1. **Push to your fork**:

```bash
git push origin feature/your-feature-name
```

2. **Create Pull Request** on GitHub with:

   - **Clear title** describing the change
   - **Detailed description** of what and why
   - **Screenshots** for visual changes
   - **Related issues** (e.g., "Fixes #123")
   - **Testing notes** for reviewers

### PR Template

```markdown
## Description
Brief description of what this PR does.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Code refactoring

## Testing
- [ ] Tested on desktop
- [ ] Tested on mobile
- [ ] Tested on multiple browsers
- [ ] No console errors

## Screenshots (if applicable)
[Add screenshots here]

## Related Issues
Fixes #(issue number)

## Additional Notes
Any additional context or notes for reviewers.
```

### Review Process

1. **Automated checks** will run (if configured)
2. **Maintainers** will review your PR
3. **Address feedback** if changes are requested
4. **Merge** once approved by a maintainer

**Typical review time:** 1-3 business days

---

## 🏅 Recognition

Contributors will be:

- Listed in the **Contributors** section of the README
- Acknowledged in **release notes**
- Given credit for their specific contributions

### Hall of Fame

We maintain a list of top contributors based on:

- Number of merged PRs
- Impact of contributions
- Community engagement

---

## 💬 Community

### Where to Get Help

- **GitHub Issues**: For bugs and feature requests
- **Discussions**: For questions and general discussion
- **Email**: For private inquiries (your.email@example.com)

### Staying Updated

- **Watch the repository** to get notified of new issues and PRs
- **Star the repo** to show your support
- **Follow the maintainers** for updates

---

## 📚 Additional Resources

### Learning Resources

- [MDN Web Docs](https://developer.mozilla.org/) - HTML, CSS, JavaScript reference
- [Google SRE Book](https://sre.google/books/) - Incident management best practices
- [GitHub Guides](https://guides.github.com/) - Git and GitHub tutorials

### Similar Projects

- [PagerDuty Incident Response](https://response.pagerduty.com/)
- [Google SRE Incident Management](https://sre.google/sre-book/managing-incidents/)
- [Atlassian Incident Handbook](https://www.atlassian.com/incident-management)

---

## ❓ Questions?

Don't hesitate to ask! We're here to help:

- **Open an issue** with your question
- **Start a discussion** in GitHub Discussions
- **Email us** at your.email@example.com

---

## 🙏 Thank You!

Every contribution makes this guide more valuable for engineers around the world. Whether you're fixing a typo or adding a major feature, your effort is appreciated! 

**Happy contributing!** 🚀

---

<div align="center">

**Together, we make incident response better for everyone.**

[View the Guide](https://sachinmangarole.github.io/incident-response-guide/) • [Report a Bug](https://github.com/sachinmangarole/incident-response-guide/issues) • [Suggest a Feature](https://github.com/sachinmangarole/incident-response-guide/issues)

</div>
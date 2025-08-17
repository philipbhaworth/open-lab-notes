# Open Lab Notes

A technical documentation and lab notes site built with **MkDocs Material**, covering homelab experiments, systems administration, high-performance computing, containerization, networking, storage, and infrastructure automation.

## 🛠️ Built With

- **[MkDocs](https://www.mkdocs.org/)** - Static site generator focused on documentation
- **[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)** - Modern, responsive theme
- **[MkDocs Blog Plugin](https://github.com/liang2kl/mkdocs-blog-plugin)** - Blog functionality with scheduling
- **Python 3.x** - Runtime environment
- **Markdown** - Content format
- **Cloudflare Pages** - Hosting and deployment

## 📁 Project Structure

```
open-lab-notes/
├── .venv/                      # Python virtual environment (not committed)
├── .gitignore                  # Git ignore file
├── mkdocs.yml                  # MkDocs configuration
├── README.md                   # This file
└── docs/                       # All content lives here
    ├── index.md                # Homepage - site welcome and navigation
    ├── about.md                # About page - personal story and philosophy
    ├── assets/
    │   └── images/
    │       └── avatar.jpg      # Profile picture for about page
    ├── stylesheets/
    │   └── extra.css           # Custom CSS for avatar and styling
    ├── infrastructure/         # Documentation: HPC, networking, storage
    │   └── index.md            # Section landing page
    ├── automation/             # Documentation: containers, IaC, orchestration
    │   └── index.md            # Section landing page
    ├── systems/                # Documentation: Linux admin, server management
    │   └── index.md            # Section landing page
    └── notes/                  # Blog section - lab notes and experiments
        ├── index.md            # Blog landing page
        └── posts/              # Individual blog posts with date-based filenames
            └── YYYY-MM-DD-post-title.md
```

### Content Organization

**Documentation (`docs/infrastructure/`, `docs/automation/`, `docs/systems/`)**
- Reference material and how-to guides
- Always available, not date-based
- Professional, instructional tone
- Organized by technology domain

**Lab Notes (`docs/notes/posts/`)**
- Time-based experiments and discoveries
- Blog-style posts with scheduling capability
- Personal learning journey and real-time notes
- Conversational, exploratory tone

## ⚡ Quick Start

### Prerequisites (macOS with Homebrew)

```bash
# Install Python 3 if not already installed
brew install python

# Verify Python installation
python3 --version
```

### Local Development Setup

```bash
# Clone the repository
git clone https://github.com/philipbhaworth/open-lab-notes.git
cd open-lab-notes

# Create and activate Python virtual environment
python3 -m venv .venv
source .venv/bin/activate

# Install dependencies
pip install mkdocs-material mkdocs-blog-plugin mkdocs-git-revision-date-localized-plugin mkdocs-glightbox mkdocs-minify-plugin mkdocs-rss-plugin

# Start local development server
mkdocs serve

# View the site
open http://127.0.0.1:8000
```

### Common Development Commands

```bash
# Activate virtual environment (run this first each time)
source .venv/bin/activate

# Start development server with auto-reload
mkdocs serve

# Build static site for deployment
mkdocs build

# Clean build directory
mkdocs build --clean

# View help
mkdocs --help

# Deactivate virtual environment when done
deactivate
```

## 📝 Content Creation

### Adding Documentation

Create new `.md` files in the appropriate section:
```bash
# Infrastructure guides
docs/infrastructure/storage-setup.md
docs/infrastructure/networking-guide.md

# Automation guides  
docs/automation/kubernetes-deployment.md
docs/automation/puppet-configuration.md

# Systems guides
docs/systems/linux-hardening.md
docs/systems/performance-tuning.md
```

### Adding Blog Posts

Create posts in `docs/notes/posts/` with date-based filenames:

```markdown
---
date: 2025-01-20              # Can be future date for scheduling
authors:
  - philip
categories:
  - homelab                   # Allowed: homelab, automation, infrastructure, systems, learning
  - automation
tags:
  - kubernetes
  - docker
draft: false                  # Set to true to hide
---

# Your Post Title

Your content here...
```

**File naming convention:**
```
docs/notes/posts/2025-01-20-kubernetes-experiment.md
docs/notes/posts/2025-02-01-storage-migration.md
```

## 🚀 Deployment

The site can be deployed using **Cloudflare Workers** (recommended) or Cloudflare Pages.

### Option 1: Cloudflare Workers (Recommended)

**Build & Deploy Commands:**
- **Build command**: `mkdocs build --clean`
- **Deploy command**: `npx wrangler pages deploy site`
- **Output directory**: `site`

**Setup:**
1. Install Wrangler CLI: `npm install -g wrangler`
2. Login to Cloudflare: `wrangler login`
3. Create project: `wrangler pages create open-lab-notes`
4. Deploy: `npx wrangler pages deploy site`

### Option 2: Cloudflare Pages (Alternative)

**Build Settings:**
- **Build command**: `mkdocs build --clean`
- **Output directory**: `site`
- **Framework preset**: None

The site automatically deploys when changes are pushed to the main branch.

## 🎨 Features

- **📱 Responsive design** - Works on all devices
- **🌙 Dark/light mode** - Automatic theme switching
- **🔍 Full-text search** - Across all content
- **📅 Blog scheduling** - Future posts automatically go live
- **⏱️ Reading time** - Estimated time for blog posts
- **🏷️ Tags and categories** - Organized content discovery
- **🖼️ Image lightbox** - Click to zoom images
- **📋 Code copy buttons** - Easy code snippet copying
- **⚡ Fast loading** - Optimized and minified
- **📖 Table of contents** - Auto-generated for longer content
- **🔗 Edit on GitHub** - Direct editing links

## 🧰 Development Tools

**Recommended:**
- **VS Code** with Markdown extensions
- **Python 3.x** (latest stable)
- **Git** for version control
- **Homebrew** (macOS) for package management

**VS Code Extensions:**
- Markdown All in One
- Python
- YAML

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

This is a personal documentation site, but if you find errors or have suggestions:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📞 Contact

- **GitHub**: [@philipbhaworth](https://github.com/philipbhaworth)
- **LinkedIn**: [Philip Haworth](https://www.linkedin.com/in/philiphaworth/)
- **Website**: [openlabnotes.dev](https://openlabnotes.dev)
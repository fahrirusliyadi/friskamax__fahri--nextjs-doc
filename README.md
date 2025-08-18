# Portfolio Template Documentation

This repository contains the documentation for the Portfolio Template.

## Building the Documentation

To build and serve the documentation locally:

1. Install MkDocs:
   ```bash
   pip install mkdocs
   ```

2. Serve the documentation locally:
   ```bash
   mkdocs serve
   ```

3. Open your browser to http://localhost:8000 to view the documentation.

## Building for Production

To build the documentation for production:

```bash
mkdocs build
```

This will generate a static site in the `site/` directory that can be deployed to any static hosting service.

## Project Structure

```
├── docs/                  # Documentation source files
│   ├── index.md           # Home page
│   ├── project-structure.md # Project structure documentation
│   ├── setup.md           # Setup and development environment
│   ├── content-customization.md # Content customization guide
│   ├── adding-projects.md # How to add new projects
│   ├── component-customization.md # Component customization guide
│   ├── styling.md         # Styling and theme customization
│   └── deployment.md      # Deployment guide
├── mkdocs.yml             # MkDocs configuration
├── site/                  # Built documentation (generated)
└── README.md              # This file
```

## Contributing

To contribute to the documentation:

1. Fork the repository
2. Create a new branch for your changes
3. Make your changes in the `docs/` directory
4. Test your changes locally with `mkdocs serve`
5. Submit a pull request

## License

This documentation is licensed under the MIT License. See the LICENSE file for details.
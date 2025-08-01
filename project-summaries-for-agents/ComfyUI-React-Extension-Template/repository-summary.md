# ComfyUI React Extension Template - Repository Summary

## Repository Overview

**Purpose**: A minimal, production-ready template for creating React/TypeScript-based frontend extensions for ComfyUI, with complete boilerplate setup including internationalization, testing, and automatic publishing workflows.

**Repository**: https://github.com/Comfy-Org/ComfyUI-React-Extension-Template  
**Organization**: Comfy-Org  
**Primary Language**: TypeScript  
**License**: GNU General Public License v3.0  
**Created**: May 19, 2025  
**Last Updated**: June 6, 2025  

## Technology Stack

### Core Technologies
- **React 18.2.0**: UI component framework
- **TypeScript 5.4.2**: Type-safe JavaScript
- **Vite 5.2.10**: Build tool and dev server
- **Jest 29.7.0**: Unit testing framework
- **React Testing Library**: Component testing utilities

### Key Dependencies
- **@comfyorg/comfyui-frontend-types 1.20.2**: Official ComfyUI TypeScript definitions
- **i18next**: Internationalization framework with React bindings
- **ESLint 9.27.0**: Code linting with TypeScript support
- **Prettier 3.5.3**: Code formatting

### Build Tools
- **Vite**: Development server with HMR, production builds
- **TypeScript Compiler**: Type checking and transpilation
- **GitHub Actions**: Automated build and publishing workflow

## Directory Structure

```
ComfyUI-React-Extension-Template/
   __init__.py                 # Python entry point for ComfyUI integration
   pyproject.toml              # Project metadata for ComfyUI Registry
   README.md                   # Comprehensive documentation
   LICENSE                     # GNU GPLv3 license
   .github/                    # GitHub configurations
      workflows/
          react-build.yml     # Automated build/publish workflow
   dist/                       # Built extension files (generated)
      example_ext/            # Compiled React application
      locales/                # Internationalization files
   ui/                         # React application source
       package.json            # NPM dependencies and scripts
       tsconfig.json           # TypeScript configuration
       vite.config.ts          # Build configuration
       eslint.config.js        # ESLint configuration
       jest.config.js          # Jest testing configuration
       public/
          locales/            # Translation files
              en/main.json    # English translations
              zh/main.json    # Chinese translations
       src/
           main.tsx            # Extension entry point
           App.tsx             # Main React component
           App.css             # Component styles
           index.css           # Global styles
           setupTests.ts       # Test environment setup
           __tests__/          # Unit tests
           utils/
               i18n.ts         # i18n configuration
```

## Development Workflow

### Essential Commands

```bash
# Initial setup
cd ui
npm install

# Development mode with hot reload
npm run watch

# Production build
npm run build

# Run tests
npm test
npm run test:watch

# Code quality
npm run lint
npm run lint:fix
npm run typecheck
npm run format
```

### Installation Methods

1. **ComfyUI Manager** (Recommended for users):
   - Search for "React Extension Template" in Manager
   - Click Install

2. **Manual Installation** (For development):
   ```bash
   cd ComfyUI/custom_nodes
   git clone https://github.com/Comfy-Org/ComfyUI-React-Extension-Template.git
   cd ComfyUI-React-Extension-Template/ui
   npm install
   npm run build
   ```

### Publishing to ComfyUI Registry

1. **Setup Registry Account**: Create account at https://registry.comfy.org
2. **Update pyproject.toml**: Set unique name and PublisherId
3. **Publish**: `comfy-cli publish` with API key
4. **Automated Publishing**: Push version update to trigger GitHub Action

## Critical Development Guidelines

### ComfyUI Extension Integration

1. **Python Integration** (`__init__.py`):
   - Registers static routes for serving React app assets
   - Handles locale file routing at `/locales/`
   - Uses `nodes.EXTENSION_WEB_DIRS` for standard ComfyUI integration
   - Attempts to read project name from `pyproject.toml` via `comfy_config`

2. **React Entry Point** (`main.tsx`):
   - Waits for ComfyUI app initialization before mounting
   - Registers extension with `app.registerExtension`
   - Creates sidebar tab with `app.extensionManager.registerSidebarTab`
   - Includes example implementations of all major ComfyUI APIs

3. **Build Configuration** (`vite.config.ts`):
   - Custom plugin `rewriteComfyImports` for development mode
   - External scripts (`/scripts/app.js`, `/scripts/api.js`) not bundled
   - Outputs to `../dist/example_ext/` directory
   - Splits React into vendor chunk for better caching

### API Design Principles

- **Type Safety**: All ComfyUI interactions use official TypeScript definitions
- **Lazy Loading**: App component loaded lazily for performance
- **Error Boundaries**: Graceful handling of initialization failures
- **Internationalization**: Built-in support for multiple languages

### Git and PR Guidelines

- **Commit Pattern**: Recent history shows PR-based development
- **Automated Workflows**: GitHub Actions for build and publish on version updates
- **Version Management**: Version in `pyproject.toml` triggers publishing

## Architecture & Patterns

### Core Architectural Concepts

1. **Extension Registration Pattern**:
   - Extensions register via `app.registerExtension` with unique name
   - Multiple API integrations in single registration object
   - Lifecycle managed by ComfyUI extension manager

2. **React Integration Strategy**:
   - React apps mounted into ComfyUI-provided DOM containers
   - State management local to React components
   - Communication with ComfyUI via window.app API

3. **Build Pipeline**:
   - TypeScript � JavaScript transpilation
   - Vite bundles React app with code splitting
   - Static assets served by ComfyUI Python server

### Extension/Plugin System

The template demonstrates all major ComfyUI extension APIs:

1. **Sidebar Tabs**: Custom panels in the UI sidebar
2. **Bottom Panel Tabs**: Additional UI panels at bottom
3. **Commands**: Programmatic actions with keybindings
4. **Menu Items**: Integration with top menu bar
5. **About Page Badges**: Links in the about dialog
6. **Toast Notifications**: User feedback system
7. **Graph Manipulation**: Direct workflow control

### State Management

- React component state for UI-specific data
- ComfyUI app state accessed via `window.app`
- No global state management library included (can be added)

### Communication Patterns

- **ComfyUI � Extension**: Event listeners, API callbacks
- **Extension � ComfyUI**: Direct API calls via window.app
- **Inter-component**: Standard React props and hooks

## Common Development Tasks

### Adding a New Feature

1. Create React component in `src/components/`
2. Import and use in `App.tsx` or create new tab
3. Add translations to `public/locales/*/main.json`
4. Register any new commands/keybindings in `main.tsx`
5. Run `npm run build` to compile
6. Test in ComfyUI interface

### Creating Custom Sidebar Tab

```typescript
const sidebarTab = {
  id: 'your-extension-id',
  icon: 'pi pi-icon',
  title: 'Your Extension',
  tooltip: 'Description',
  type: 'custom' as const,
  render: (element: HTMLElement) => {
    const container = document.createElement('div')
    element.appendChild(container)
    ReactDOM.createRoot(container).render(<YourComponent />)
  }
}
window.app.extensionManager.registerSidebarTab(sidebarTab)
```

### Testing Procedures

1. **Unit Tests**: Jest + React Testing Library
   - Mock ComfyUI window.app object provided
   - Test components in isolation
   - Run: `npm test`

2. **Integration Testing**:
   - Build extension: `npm run build`
   - Install in ComfyUI
   - Verify all registered features work

### Deployment Process

1. **Development**: Use `npm run watch` for live reload
2. **Testing**: Run unit tests and manual testing
3. **Building**: `npm run build` creates production bundle
4. **Publishing**: Update version in `pyproject.toml` and push

### Troubleshooting Guide

- **Extension not loading**: Ensure `npm run build` was run
- **Locale not found**: Check `dist/locales/` exists
- **Type errors**: Run `npm run typecheck` to diagnose
- **Build failures**: Clear `dist/` and rebuild

## Key Files for Claude Code

### Priority Files to Read

1. **`ui/src/main.tsx`**: Extension registration and ComfyUI API usage examples
2. **`__init__.py`**: Python integration and static file serving
3. **`ui/vite.config.ts`**: Build configuration and ComfyUI script handling
4. **`ui/src/App.tsx`**: Example React component with ComfyUI interaction
5. **`pyproject.toml`**: Project metadata and publishing configuration

### Configuration Files

- **`ui/package.json`**: Dependencies and available scripts
- **`ui/tsconfig.json`**: TypeScript compiler options
- **`.github/workflows/react-build.yml`**: CI/CD automation

### Development Patterns

1. **Always build before testing**: The extension requires compiled code in `dist/`
2. **Use TypeScript types**: Import from `@comfyorg/comfyui-frontend-types`
3. **Handle initialization**: Wait for window.app before registering
4. **Follow React best practices**: Hooks, functional components, proper effects
5. **Internationalize from start**: Use i18n for all user-facing text

## External Resources

- [ComfyUI JS Extension Documentation](https://docs.comfy.org/custom-nodes/js/javascript_overview)
- [ComfyUI Registry Documentation](https://docs.comfy.org/registry/publishing)
- [ComfyUI Frontend Repository](https://github.com/Comfy-Org/ComfyUI-Frontend)
- [Official ComfyUI Frontend Types](https://www.npmjs.com/package/@comfyorg/comfyui-frontend-types)

## Summary for AI Development

This repository provides a complete, production-ready template for creating React-based ComfyUI extensions. It includes all necessary boilerplate for TypeScript development, internationalization, testing, and automated publishing. The template demonstrates best practices for integrating with ComfyUI's extension system and provides examples of all major API features.

When developing extensions using this template:
1. Start by understanding the example implementation in `main.tsx` and `App.tsx`
2. Follow the established patterns for registering extension features
3. Use the provided TypeScript types for type-safe ComfyUI interaction
4. Build and test frequently during development
5. Leverage the automated publishing workflow for releases

The template is actively maintained by the Comfy-Org organization and follows ComfyUI's evolving frontend architecture.
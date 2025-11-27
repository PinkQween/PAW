# Contributing to PAW

## Adding New Components

PAW uses git submodules to manage components. To add a new component:

### 1. Create the Component Repository

```bash
# Create a new repository on GitHub
gh repo create PinkQween/PAW-<component-name> --public \
  --description "Component description here"

# Clone and set up the component
git clone git@github.com:PinkQween/PAW-<component-name>.git
cd PAW-<component-name>
```

### 2. Initialize as Swift Package

```bash
# Create Package.swift and directory structure
swift package init --type library --name PAW<ComponentName>
```

### 3. Add Component Documentation

Create a README.md explaining:
- Component purpose and responsibilities
- Integration points with other PAW components
- Setup and development instructions

### 4. Add as Submodule to Main PAW Repository

```bash
# From the main PAW directory
git submodule add git@github.com:PinkQween/PAW-<component-name>.git <component-name>
git add .gitmodules <component-name>
git commit -m "Add <component-name> component"
git push
```

### 5. Update Main PAW README

Add the component to the Components section in the main README.md.

## Development Workflow

### Working on a Component

```bash
# Clone PAW with all submodules
git clone --recursive git@github.com:PinkQween/PAW.git
cd PAW/<component-name>

# Make changes
# Commit and push to component repository
git add .
git commit -m "Your changes"
git push

# Update main PAW repo to reference new commit
cd ..
git add <component-name>
git commit -m "Update <component-name> to latest"
git push
```

## Code Standards

- Follow Swift API Design Guidelines
- Write comprehensive tests
- Document public APIs
- Use meaningful commit messages

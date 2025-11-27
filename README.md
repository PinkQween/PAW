# PAW - Purr-Accessible Webnames

A DNS alternative that makes the web more accessible.

## Overview

PAW (Purr-Accessible Webnames) is a DNS alternative protocol designed to provide an accessible naming system for web resources. PAW works **alongside** traditional DNS, not as a replacement, seamlessly integrating with HTTP traffic for enhanced name resolution.

### Technical Specifications

- **Primary Protocol**: TCP on port 96
- **Future Support**: UDP on port 96 (planned)
- **Primary Language**: Swift
- **Integration**: Non-invasive, works alongside existing DNS

## Architecture

PAW is built as a modular system with multiple components working together:

### Components

- **[resolver/](resolver/)** - System integration component that resolves PAW names alongside DNS for HTTP traffic
  - Repository: [PAW-resolver](https://github.com/PinkQween/PAW-resolver)
  - Integrates with computer networking without overwriting DNS configuration
  - Provides seamless PAW name resolution for HTTP requests

### Future Components

Additional components will be added as git submodules to support the complete PAW ecosystem (protocol servers, clients, registries, etc.).

## Project Structure

This repository uses git submodules to organize components. Each component is a separate repository that can be developed and versioned independently.

### Cloning with Submodules

```bash
# Clone with all submodules
git clone --recursive git@github.com:PinkQween/PAW.git

# Or if already cloned, initialize submodules
git submodule update --init --recursive
```

## Getting Started

Each component has its own README with specific setup instructions. Navigate to the component directory for details.

## License

TBD

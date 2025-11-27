# PAW Architecture

## Overview

PAW is designed as a modular system where each component is developed as an independent Swift package in its own repository, integrated into the main PAW repository as git submodules.

## Design Principles

1. **Non-Invasive Integration**: PAW works alongside existing DNS infrastructure, not as a replacement
2. **Modular Components**: Each component is independently versioned and maintained
3. **Swift-First**: Primary development language is Swift for macOS/iOS integration
4. **Port 96**: Uses TCP port 96 for PAW protocol (UDP support planned)

## Component Architecture

### Resolver

The resolver component integrates with system networking to intercept and resolve PAW names for HTTP traffic.

**Key responsibilities:**
- Intercept HTTP requests before DNS resolution
- Query PAW name servers on port 96
- Fallback to traditional DNS when PAW name doesn't exist
- Seamless integration without system DNS configuration changes

### Future Components

Additional components to be developed:

- **Server**: PAW name server implementation
- **Client**: CLI/GUI clients for PAW name resolution
- **Registry**: PAW name registration and management
- **Protocol**: Core protocol definitions and shared utilities

## Integration Flow

```
HTTP Request → Resolver (checks PAW) → PAW Server (port 96) → Resolution
                    ↓ (if not found)
                DNS Fallback → Traditional DNS → Resolution
```

## Development

Each component should:
- Be a valid Swift package with Package.swift
- Include comprehensive tests
- Document its API and integration points
- Follow Swift best practices and conventions

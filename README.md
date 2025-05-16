# h3xsh Traefik Middleware

⚠️ **UNDER ACTIVE DEVELOPMENT** ⚠️ 

**Disclaimer:** This plugin is a work in progress and is not recommended for production environments without thorough testing. Use at your own risk.

## About

This plugin is a multi-purpose security and tracing middleware for Traefik that provides:

1. **Request Tracing** - Generate unique IDs for distributed tracing
2. **Service Authentication** - Validate API keys for service-to-service communication

## Quick Start

```yaml
# cli static config 

--experimental.plugins.h3xsh-traefik-middleware.version=v0.2.0
--experimental.plugins.h3xsh-traefik-middleware.modulename=github.com/h3xsh/traefik-middleware

```


```yaml
# Dynamic configuration
http:
  middlewares:
    h3xsh-traefik-middleware:
      plugin:
        h3xsh-traefik-middleware:
          trace:
            enabled: true
            headerName: "X-Request-Trace-Id"
          auth:
            enabled: true
            removeKeyNameOnSuccess: false
            removeKeyValueOnSuccess: true
            errorResponseType: plain
            errorMessage: "oh oh"
            keys:
              - name: "service-a" 
                value: "api-key-123"
```

## Features (TBD)


## Comming soon
- **IP Access Control** - Allow or deny requests based on IP address/range
- Custom response error

## Todos
- add tests

## License

[MIT License](LICENSE)
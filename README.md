# Neon Inference Plugin: Locale

Request step that injects the user's locale into a BrainForge inference
pipeline: current time and a weather forecast for a resolved location.

Entry point group: `brainforge.inference.request_steps`

| Step id | Class |
| --- | --- |
| `neon.locale` | `AmbientContextStep` |

```yaml
pipeline:
  request:
    - id: neon.locale
      config:
        mcp_url: https://mcp.neonaiservices2.com/mcp
        default_location: Renton, WA, USA
        timeout: 5.0
```

`transaction.request_context` may include `location` or `client_ip`.
The step writes `transaction.request_step_context["neon.locale"]`.

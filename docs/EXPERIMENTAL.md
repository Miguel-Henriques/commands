## Experimental ideas

### Command config

```yaml
Command:
  - Id: Commands.terraform_init_backend
    OnError: Abort # Continue | Abort
  - Run: export AWS_PROFILE=personal
```

### Integrations

Integrate as a Claude Code Mod.

### Community-driven command bundles

Commands is composable. We can build mechanisms to easily install and distribute command bundles.

```sh
brew install recipe commands-aws-sso
```

### Secrets

Commands can cache secrets so commands can run faster, e.g. API Keys, Connection strings. What are the implied security risks ?

### Command Variants

```yaml
Command: vite build --target $TARGET 
Variants:
  DEV:
    TARGET: dev.env
```

### Command Name

Required. Used to display the command in the TUI. Max 40 characters. No spaces or special characters allowed.

```yaml
Name: <User friendly name of the command>
```
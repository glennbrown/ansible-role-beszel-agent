# Ansible Role: Beszel Agent

This Ansible role installs the Beszel agent on MacOS systems using Homebrew.

## Requirements

- Ansible 2.9 or later
- MacOS target system
- Homebrew installed on the target system

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
# State of the Beszel agent package (present/absent)
beszel_agent_state: present

# Homebrew tap for Beszel agent
beszel_agent_tap: henrygd/beszel

# Package name for Beszel agent
beszel_agent_package: beszel-agent
```

Required variables that must be provided:

```yaml
# SSH public key for Beszel agent authentication
beszel_agent_sshkey: "ssh-rsa AAAA..."

# Authentication token for Beszel agent
beszel_agent_token: "your-beszel-token"
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: localhost
  roles:
    - role: gbrown.beszel_agent
      vars:
        beszel_agent_sshkey: "ssh-rsa AAAA..."
        beszel_agent_token: "your-beszel-token"
```

To install a specific version or remove the agent:

```yaml
- hosts: localhost
  roles:
    - role: gbrown.beszel_agent
      vars:
        beszel_agent_state: absent  # To remove the agent
```

## License

MIT

## Author Information

This role was created by Glenn Brown.

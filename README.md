# demo-packer-aap

This is a repository to build a packer image to build the Ansible Automation Platform (AAP)

## 🔐 Secure Token Handling for Red Hat Automation Hub

To access private content from Red Hat Automation Hub via `ansible-galaxy`, a token is required. This token is used in `ansible.cfg` but should **never be committed to source control**.

Instead, create a `.env.local` file in the project root with the following:

```ini
# .env.local
HUB_OFFLINE_TOKEN=your-access-token-here # e.g. "ey...."
```

This file is automatically loaded by the Makefile when running targets like make aap_demo. 
🔒 Make sure .env.local is listed in .gitignore to avoid committing sensitive credentials.
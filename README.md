# CortexAI Plugins

CortexAI's agent core is modular.  
Plugins let you inject new commands without forking the main repo or needing to modify any of the main code and, literally, the sky's the limit.

## Why Plugins in an Agent with System Access?
CortexAI's agent has user level permissions (meaning it inherits your permissions) to the entire system: it can run terminal commands, access files, launch apps, and execute scripts as part of it's core functionality. However, plugins exist to structure this power into specialized, reusable tools that the AI can reason over predictably, rather than improvising ad hoc executions that risk errors, inconsistencies, or security oversights during autonomous missions.​

By encapsulating complex workflows (e.g., a GraphQL recon plugin chaining web requests with custom parsing), plugins let the agent select and orchestrate them dynamically via ToolRegistry, improving explainability, audit trails, and compliance with OWASP standards without bloating the core. This modularity also fosters community contributions. Users add niche tools (like Burp integrations) without risking system wide changes, keeping the agent focused on high level reasoning while leveraging its full access safely.​

In essence, plugins turn broad system access into intelligent, modular capabilities: the agent could spawn nmap directly, but a dedicated plugin ensures scoped, logged runs with AI analysis, reducing false positives and enhancing remediation guidance. This design balances raw power with structured extensibility, making CortexAI adaptable for ethical hacking without compromising reliability.​

## Quick Start

### Prerequisites
- Node.js >=14 installed.
- CortexAI (install via `npm install` and `npm start` from the main repo).
- Basic .env setup in `~/.cortexai/.env` for API keys.

### Installing Plugins
Plugins are self-contained JS modules with a `manifest.json`.

Add them to your CLI via:

1. **Copy to Local Dir**: Place the plugin folder in `~/.cortexai/plugins/`. The CLI auto-loads on startup

2. **NPM Install (for Packaged Plugins)**: Plugins are npm-compatible

3. **That's it, your done.**: The agent autoloads everytime you start it.
### Testing Plugins Standalone
Use the included `test-runner.js` found in the main repo to validate without the CLI

Browse `plugins/official/` for code and manifests. 

### Community Plugins
Submit yours via PR to `plugins/community/`! Examples to inspire:
- Custom recon for GraphQL endpoints.
- Burp Suite integration hook.
- Offline vuln scanner using local tools
- Hell, idk. Whatever you can think of

## Contributing
Love extending pentest tools? Help build the ecosystem!
- Fork the repo and add your plugin to `plugins/community/` (include manifest.json, index.js, README.md with examples).
- Test with `node test-runner.js your-plugin/`.
- PR with a clear description and label as "plugin-submission".

## All contributions under MIT credit you in the manifest!

## License
MIT License—free to use, modify, distribute. See [LICENSE](LICENSE).

## Get Involved
- Star/fork the repo to show support.
- Report bugs or request features [here](https://github.com/theelderemo/cortexai-plugins/issues).
- For the main repo go [here](https://github.com/theelderemo/cortexai)

Built with ❤️ for the security community. Questions? Open an issue!

# jxscout

**jxscout** is a powerful security tool designed for security researchers to analyze and uncover vulnerabilities in JavaScript code. It seamlessly integrates with proxies like Burp Suite or Caido, capturing and organizing static assets locally for deep analysis.

## 🚀 Key Features

- **Project & Asset Organization**: Automatically organizes discovered assets (HTML, JS) into intuitive project-based folder structures.
- **Advanced Project Metrics**: New **Project Module** to track project health, asset counts, and security findings at a glance.
- **Smart Bookmarking**: Enhanced **Bookmarks Module** for tagging and tracking interesting code blocks and endpoints.
- **Chunk Discovery**: High-concurrency detection and pre-fetching of Webpack and Vite chunks.
- **Code Beautification**: Real-time beautification of minified JavaScript for better readability.
- **Source Map Reconstruction**: Automated reversal of application source code when `.map` files are discovered.
- **AST Analysis**: Integrated AST analysis to highlight potential vulnerabilities (integrated with the VSCode Extension).
- **Modern Build System**: Now utilizing **rsbuild** for lightning-fast module processing.

## 🎬 Demo

Experience **jxscout** in action:

https://github.com/user-attachments/assets/64f161c3-46b0-41a9-8b34-706cc795a034

## 🛠️ Installation & Setup

### Requirements

- **Golang**: [Install Go](https://go.dev/doc/install) (Project core)
- **Bun** (>=1.2.12): [Install Bun](https://bun.sh/docs/installation) (Module execution)

### Part 1. Installing the CLI

Install the **jxscout** CLI directly from the fork:

```bash
go install github.com/h0tak88r/jxscout/cmd/jxscout@latest
```

Alternatively, download a pre-compiled binary from the [Releases](https://github.com/h0tak88r/jxscout/releases) page.

![jxscout](docs/jxscout.png)

Run the `install` command within the CLI to automatically set up dependencies like `prettier`:
```bash
jxscout install
```

### Part 2. Proxy Integration

**jxscout** relies on traffic from your proxy. Install the appropriate plugin:

- **Caido**: [jxscout-caido](https://github.com/h0tak88r/jxscout-caido)
- **Burp Suite**: [jxscout-burp](https://github.com/h0tak88r/jxscout-burp)

Once configured, assets will be saved to your `~/jxscout` directory by default.

### Part 3. VSCode Extension

The **jxscout VSCode Extension** provides a visual frontend for AST analysis results, presenting a navigable tree of discovered endpoints and secrets.

![VSCode Integration](docs/vscode.png)

Check out the [VSCode Extension Repository](https://github.com/h0tak88r/jxscout-vscode) for setup instructions.

## 📖 Usage

Start the tool by simply running:
```bash
jxscout
```

### Available Commands

| Command | Shortcut | Description |
|---------|----------|-------------|
| `assets` | `la` | List assets for the current project |
| `caido-auth`| `ca` | Authenticate with Caido for overrides |
| `config` | `cf` | View or update configuration |
| `guide` | `g` | Interactive walkthrough |
| `logs` | `l` | Toggle real-time logs panel |
| `override` | `o` | Toggle local content overrides |

### Project Management

Organize your research by target:
```bash
config project-name=target_name scope=*target.com*
```

## 🛠️ Development

This fork introduces a modernized build process using **rsbuild**.

### Building from source

```bash
make install
make build
go build -o jxscout cmd/jxscout/main.go
```

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/h0tak88r/jxscout/issues).

## 🛡️ License

This project is licensed under the GNU General Public License. See the [COPYING](COPYING) file for details.

## ⚠️ Disclaimer

This tool is for educational and authorized security testing purposes only. The author is not responsible for any misuse or damage caused by this software.


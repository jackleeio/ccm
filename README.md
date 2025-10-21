# CCM - Claude Code Router Model Switcher

A simple command-line tool to quickly switch between AI models in Claude Code Router.

## Features

- 🔄 Quick model switching between Claude Sonnet 4.5 and GLM-4.6
- 🚀 Automatic server restart after model change
- 📋 Current model status display
- 💾 Automatic configuration backup

## Installation

1. Clone this repository:
```bash
git clone https://github.com/jackleeio/ccm.git
cd ccm
```

2. Copy the script to your bin directory:
```bash
cp ccm ~/bin/ccm
chmod +x ~/bin/ccm
```

3. Make sure `~/bin` is in your PATH:
```bash
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

## Usage

### Switch Models

**Switch to Claude Sonnet 4.5:**
```bash
ccm -c
```

**Switch to GLM-4.6:**
```bash
ccm -g
```

### Check Current Model

**Show current model status:**
```bash
ccm
```

## Configuration

The script automatically detects and modifies the Claude Code Router configuration file at:
```
~/.claude-code-router/config.json
```

Before making any changes, it creates a backup at:
```
~/.claude-code-router/config.json.bak
```

## Supported Models

| Option | Model | Provider |
|--------|-------|----------|
| `-c` | Claude Sonnet 4.5 | OpenRouter |
| `-g` | GLM-4.6 | OpenRouter |

## Requirements

- Claude Code Router installed
- `ccr` command available for service restart
- Bash shell

## How It Works

1. **Backup**: Creates a backup of your current configuration
2. **Update**: Modifies all model-related fields in the config:
   - `default`
   - `background`
   - `think`
   - `longContext`
3. **Restart**: Automatically restarts the Claude Code Router service

## Troubleshooting

### Configuration file not found
```
❌ 配置文件不存在: /Users/username/.claude-code-router/config.json
```
Make sure Claude Code Router is installed and has been run at least once.

### Service restart fails
Ensure the `ccr` command is available in your PATH and you have proper permissions to restart the service.

## License

MIT License - feel free to use and modify as needed.

## Contributing

Pull requests are welcome! Please feel free to submit a Pull Request.
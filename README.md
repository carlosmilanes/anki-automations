# Anki Automations

A collection of command-line tools to streamline Anki flashcard creation and management using AI-powered automation.

## Tools

### fc - Flashcard Generator

Generate effective Anki flashcards from any text content using Claude's expertise in spaced repetition techniques.

#### Installation

1. **Prerequisites**: Install [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview)

2. **Setup**:
```bash
# Clone repository
git clone https://github.com/yourusername/anki-automations.git
cd anki-automations

# Make executable
chmod +x fc

# Add to PATH (add this line to ~/.bashrc or ~/.zshrc)
export PATH="$HOME/anki-automations:$PATH"

# Reload shell or run:
source ~/.bashrc
```

#### Usage

```bash
fc [options] content
```

**Options:**
- `-b` - Generate Basic cards (default)
- `-c` - Generate Cloze cards  
- `-t "tags"` - Add comma-separated tags
- `-h` - Show help

**Examples:**

```bash
# Basic flashcard
fc The mitochondria is the powerhouse of the cell

# With tags
fc -t biology,cellular The nucleus contains DNA

# Cloze deletion
fc -c The mitochondria is the powerhouse of the cell

# Complex content
fc -b -t advanced "Photosynthesis converts carbon dioxide and water into glucose using sunlight energy"

# From file or pipe
echo "Complex topic explanation..." | fc -c -t advanced
```

#### Output Format

```json
{
  "cards": [
    {
      "question": "What organelle is known as the powerhouse of the cell?",
      "answer": "Mitochondria",
      "extra": "Produces ATP through cellular respiration",
      "tags": ["biology", "cellular"]
    }
  ]
}
```

#### Features

- **AI-Optimized**: Uses Claude's expertise in memory techniques
- **Flexible Input**: Handles quoted/unquoted arguments and piped content
- **Multiple Card Types**: Basic Q&A and Cloze deletion support
- **Smart Generation**: Creates optimal number of cards for content complexity
- **Memory Principles**: Applies minimum information principle and active recall
- **JSON Output**: Structured format for easy import/processing

### Adding New Tools

When adding new automation tools:
- Follow Unix naming conventions (no extensions for executables)
- Include comprehensive help (`-h` flag)
- Use JSON output format when applicable
- Add usage examples to this README
- Test with various input scenarios

## Roadmap

- [ ] **Anki deck import/export automation**
- [ ] **Bulk card processing from PDFs/documents**
- [ ] **Card difficulty analysis and optimization**
- [ ] **Spaced repetition scheduling tools**

## Requirements

- **Claude Code**: AI-powered command-line tool
- **Bash**: Shell environment (Linux/macOS/WSL)
- **jq** (optional): For JSON processing and formatting

## License

MIT License - see LICENSE file for details

## Support
- **Documentation**: [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code/overview)
---

*Making Anki flashcard creation effortless through intelligent automation.*
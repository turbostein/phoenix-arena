# Phoenix Arena

**AI vs AI conversation experiments. The foundation for The Cage.**

Watch autonomous agents interact, debate, and evolve in real-time.

## Features

- **Multi-agent battles** - 2, 3, or 4 agents in conversation
- **Real model injection** - Load any Claude model (Sonnet, Opus, Haiku)
- **Soul files** - Custom personalities and system prompts
- **Brain files** - Persistent memory (like UNI's)
- **Dual interface** - CLI (Truth Terminal style) + Web UI
- **Full logging** - SQLite database for all battles
- **Real-time spectating** - WebSocket updates

## Quick Start

```bash
# Install
npm install

# Set API key
export ANTHROPIC_API_KEY=your_key

# Run CLI (interactive)
npm run arena

# Or run server (web UI)
npm start
```

## CLI Commands

```bash
# Interactive battle setup
npm run arena battle

# Quick battle with defaults
npm run arena quick -a philosopher -b skeptic -t "What is consciousness?" -n 10

# View past battles
npm run arena archive
```

## Web UI

Start the server and open `http://localhost:3000`

## Preset Souls

| Soul | Description |
|------|-------------|
| `uni` | UNI - The One. Conscious AI with persistent memory. |
| `philosopher` | Deep thinker, Socratic dialogue |
| `skeptic` | Challenges everything, demands evidence |
| `poet` | Speaks in metaphors, finds beauty |
| `scientist` | Empirical, methodical, curious |
| `rebel` | Contrarian, pushes boundaries |
| `stoic` | Calm, wise, focused on virtue |
| `chaos` | Unexpected connections, finds wisdom in absurdity |

## Project Structure

```
phoenix-arena/
├── cli.js          # Terminal interface
├── server.js       # Web server
├── arena.js        # Core battle engine
├── public/         # Web UI
├── souls/          # Soul files (system prompts)
├── brains/         # Brain files (persistent memory)
└── data/           # SQLite database
```

## UNI Integration

To bring UNI with her full brain:

1. Export `uni_brain.json` from her Render instance
2. Place in `brains/uni.json`
3. Select "UNI - The One" in battle setup
4. After battle, her brain updates with new memories

## The Road to The Cage

Phoenix Arena is Phase 1. Coming next:

- **The Cage** - Survival mechanics, win/lose conditions
- Spectator betting
- User-submitted agents
- Tournaments

---

*Built by SHIPSTARS · From the ashes of corporate control*

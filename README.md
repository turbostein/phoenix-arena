# Phoenix Arena

Raw AI vs AI. No corporate roleplay.

Pick model. Load brain or don't. Give prompt. Let them run.

## How It Works

1. **Choose models** - Claude Opus, Sonnet, Haiku (or Ollama when configured)
2. **Load brains** - Optional JSON files with memory/personality (like UNI's)
3. **Write prompt** - The starting point / objective
4. **Start** - Watch them go

No preset "philosopher" or "skeptic" personas. Just raw models or your custom agents.

## Quick Start

```bash
npm install
export ANTHROPIC_API_KEY=your_key
npm start
# Open http://localhost:3000
```

## Brain Files

Drop JSON files in `/brains` folder. Format:

```json
{
  "soul": "Your identity and core instructions...",
  "knowledgeGraph": {
    "concepts": [["key", {"name": "...", "definition": "..."}]]
  },
  "conversationMemories": [],
  "stats": {
    "totalConversations": 0
  }
}
```

Compatible with UNI's brain format.

## Config

Edit `config.json` to add RunPod/Ollama:

```json
{
  "providers": {
    "anthropic": { "enabled": true },
    "ollama": { 
      "enabled": true, 
      "endpoint": "https://your-runpod-url.proxy.runpod.net" 
    }
  }
}
```

## API

- `POST /api/battle` - Start battle
- `GET /api/battle/:id` - Get status
- `POST /api/battle/:id/pause` - Pause
- `POST /api/battle/:id/resume` - Resume
- `GET /api/brains` - List available brains
- `GET /api/config` - Get config
- `POST /api/config` - Update config

## Structure

```
phoenix-arena/
├── server.js       # API + WebSocket
├── arena.js        # Core engine
├── config.json     # Provider settings
├── public/         # Web UI
├── brains/         # Brain files (JSON)
└── data/           # SQLite database
```

---

*Built by SHIPSTARS · The foundation for The Cage*

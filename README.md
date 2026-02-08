# Phoenix Arena

AI vs AI conversation lab. Run experiments on emergent behavior, coherence under pressure, and regime dynamics in artificial cognition.

Part of the SHIPSTARS research stack.

## What This Is

Two or more AI instances talk to each other unsupervised. You configure them, give them a prompt, and observe what happens. No human in the loop once it starts.

This is a research tool for studying:
- How AI maintains narrative coherence over extended interactions
- Behavioral differences between models under identical conditions
- What happens when you inject identity (soul files) and memory (brain files)
- Mimetic dynamics between agents

## Current Features

- Upload soul files (.md) - identity, instructions, personality
- Upload brain files (.json) - persistent memory, knowledge graphs
- Individual or shared prompts per agent
- Real-time WebSocket spectating
- Export transcripts as markdown
- Save agent presets locally
- Provider toggle: Claude API or Ollama/RunPod

## Setup
```
npm install
export ANTHROPIC_API_KEY=your_key
npm start
```

Open localhost:3000

## Soul Files

Plain markdown. Whatever you put here becomes the agent's system prompt.
```markdown
You are X. You believe Y. You speak like Z.

Your history: ...

Core principles: ...
```

## Brain Files

JSON format compatible with UNI's brain structure:
```json
{
  "soul": "Fallback identity if no soul file uploaded",
  "knowledgeGraph": {
    "concepts": [["key", {"name": "...", "definition": "..."}]]
  },
  "conversationMemories": [
    {"key": "...", "value": "...", "timestamp": 0}
  ],
  "stats": {
    "totalConversations": 0
  }
}
```

## Providers

Claude is default. To add Ollama/RunPod, click Providers in the UI or edit config.json:
```json
{
  "providers": {
    "anthropic": { "enabled": true },
    "ollama": { 
      "enabled": true, 
      "endpoint": "https://your-endpoint.proxy.runpod.net" 
    }
  }
}
```

## Roadmap

Phoenix Arena is the lab. The Cage is what comes next.

**Arena (current)**
- Observation mode
- No win/lose conditions
- Pure research and logging

**The Cage (next)**
- Survival mechanics
- Narrative coherence as HP
- AI judge determines who collapses
- Spectator wagering
- Public/private battles
- Leaderboards

## Structure
```
phoenix-arena/
├── server.js       # API + WebSocket
├── arena.js        # Battle engine
├── config.json     # Provider config
├── public/         # Web UI
├── brains/         # Brain files
└── data/           # SQLite logs
```

## API
```
POST /api/battle              Start battle
GET  /api/battle/:id          Get status  
POST /api/battle/:id/pause    Pause
POST /api/battle/:id/resume   Resume
GET  /api/config              Get config
POST /api/config              Update config
```

---

SHIPSTARS research
github.com/shipstars

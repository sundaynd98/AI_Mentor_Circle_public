# Context Engineering & Context Architecture

**AI Mentor Circle — Handout**
*A field guide for designers building with AI coding assistants*

---

## 1. The core reframe

You already design scarce space. A screen has only so much room; everything on it competes for attention, and cramming in more usually makes the experience worse, not better.

A model's **context window** works the same way. It's the finite space holding everything the model can "see" at the moment it responds — and just like a screen, relevance beats volume. Irrelevant material doesn't sit there harmlessly; it dilutes the signal and drags the output down.

> **The anchor idea:** Deciding what goes into that scarce space is a real design act. It has a name — two, actually.

---

## 2. Two terms, one distinction

These are two sides of the same craft, and you already know the shape of it from your own work.

**Context engineering** is tactical and per-task: *what does the model see right now, for this one request?* You assemble it fresh each time.

**Context architecture** is structural and durable: *how is the whole information environment organized so the right things can be surfaced reliably, over and over?*

| | Context engineering | Context architecture |
|---|---|---|
| What it is | What the model sees right now | How the information environment is structured |
| Timescale | Per request — dynamic | Persistent — set up once |
| Design analogy | Interaction design | Information architecture |
| You're deciding | What to put in front of the model *this time* | What exists to be drawn from, and how it's organized |

> The analogy is the shortcut: **engineering is to architecture as interaction design is to IA.** One is the moment; the other is the structure that makes good moments possible.

---

## 3. Where context comes from

Everything the model sees arrives from somewhere. Some sources are **static** — set up once and persist (the architecture side). Others are **dynamic** — assembled fresh for each request (the engineering side). The main pieces converge into the window:

<svg xmlns="http://www.w3.org/2000/svg" width="680" height="410" viewBox="0 0 680 410" role="img" font-family="DejaVu Sans, Arial, sans-serif">
  <title>Where the main pieces of context fit in an AI system</title>
  <desc>Context sources, split into static and dynamic, converge into the context window, which the model reads to produce output.</desc>
  <defs>
    <marker id="ah" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse">
      <path d="M2 1L8 5L2 9" fill="none" stroke="#94a3b8" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/>
    </marker>
  </defs>
  <text x="24" y="30" font-size="15" font-weight="700" fill="#1a202c">Sources of context</text>
  <text x="24" y="52" font-size="12" fill="#718096">Static &#183; set once, persists</text>
  <g>
    <rect x="24" y="60" width="185" height="44" rx="8" fill="#f0f7f0" stroke="#6aaa6a" stroke-width="1"/>
    <text x="38" y="80" font-size="13" font-weight="700" fill="#276027">System prompt</text>
    <text x="38" y="96" font-size="11" fill="#5a6b5a">Rules, role, format</text>
  </g>
  <g>
    <rect x="24" y="112" width="185" height="44" rx="8" fill="#f0f7f0" stroke="#6aaa6a" stroke-width="1"/>
    <text x="38" y="132" font-size="13" font-weight="700" fill="#276027">Persistent memory</text>
    <text x="38" y="148" font-size="11" fill="#5a6b5a">CLAUDE.md, projects</text>
  </g>
  <text x="24" y="184" font-size="12" fill="#718096">Dynamic &#183; assembled per request</text>
  <g>
    <rect x="24" y="192" width="185" height="44" rx="8" fill="#fffbeb" stroke="#f59e0b" stroke-width="1"/>
    <text x="38" y="212" font-size="13" font-weight="700" fill="#92400e">User input</text>
    <text x="38" y="228" font-size="11" fill="#8a6d3b">Message, uploads</text>
  </g>
  <g>
    <rect x="24" y="244" width="185" height="44" rx="8" fill="#fffbeb" stroke="#f59e0b" stroke-width="1"/>
    <text x="38" y="264" font-size="13" font-weight="700" fill="#92400e">Conversation history</text>
    <text x="38" y="280" font-size="11" fill="#8a6d3b">Prior turns</text>
  </g>
  <g>
    <rect x="24" y="296" width="185" height="44" rx="8" fill="#fffbeb" stroke="#f59e0b" stroke-width="1"/>
    <text x="38" y="316" font-size="13" font-weight="700" fill="#92400e">Retrieved knowledge</text>
    <text x="38" y="332" font-size="11" fill="#8a6d3b">Search, RAG</text>
  </g>
  <g>
    <rect x="24" y="348" width="185" height="44" rx="8" fill="#fffbeb" stroke="#f59e0b" stroke-width="1"/>
    <text x="38" y="368" font-size="13" font-weight="700" fill="#92400e">Tool outputs</text>
    <text x="38" y="384" font-size="11" fill="#8a6d3b">Results, status</text>
  </g>
  <line x1="209" y1="82"  x2="250" y2="150" stroke="#94a3b8" stroke-width="1.4" marker-end="url(#ah)"/>
  <line x1="209" y1="134" x2="250" y2="162" stroke="#94a3b8" stroke-width="1.4" marker-end="url(#ah)"/>
  <line x1="209" y1="214" x2="250" y2="200" stroke="#94a3b8" stroke-width="1.4" marker-end="url(#ah)"/>
  <line x1="209" y1="266" x2="250" y2="215" stroke="#94a3b8" stroke-width="1.4" marker-end="url(#ah)"/>
  <line x1="209" y1="318" x2="250" y2="230" stroke="#94a3b8" stroke-width="1.4" marker-end="url(#ah)"/>
  <line x1="209" y1="370" x2="250" y2="245" stroke="#94a3b8" stroke-width="1.4" marker-end="url(#ah)"/>
  <g>
    <rect x="254" y="120" width="176" height="150" rx="12" fill="#eef3fb" stroke="#4a7fd4" stroke-width="1.2"/>
    <text x="342" y="150" font-size="14" font-weight="700" fill="#1a202c" text-anchor="middle">Context window</text>
    <text x="342" y="170" font-size="11" fill="#5a6b8a" text-anchor="middle">Assembled per request</text>
    <text x="342" y="228" font-size="11" fill="#4a5568" text-anchor="middle">Finite, scarce space &#8212;</text>
    <text x="342" y="244" font-size="11" fill="#4a5568" text-anchor="middle">relevance beats volume</text>
  </g>
  <line x1="430" y1="185" x2="484" y2="182" stroke="#94a3b8" stroke-width="1.4" marker-end="url(#ah)"/>
  <g>
    <rect x="486" y="156" width="160" height="52" rx="8" fill="#f7f9fc" stroke="#cbd5e0" stroke-width="1"/>
    <text x="566" y="180" font-size="14" font-weight="700" fill="#1a202c" text-anchor="middle">Model</text>
    <text x="566" y="197" font-size="11" fill="#718096" text-anchor="middle">Reads the window</text>
  </g>
  <line x1="566" y1="208" x2="566" y2="258" stroke="#94a3b8" stroke-width="1.4" marker-end="url(#ah)"/>
  <g>
    <rect x="486" y="260" width="160" height="52" rx="8" fill="#f7f9fc" stroke="#cbd5e0" stroke-width="1"/>
    <text x="566" y="290" font-size="14" font-weight="700" fill="#1a202c" text-anchor="middle">Output</text>
  </g>
</svg>

---

## 4. Reference — what counts as "context"

A fuller inventory of what can occupy that window, grouped by source. The static/dynamic tag maps back to architecture vs. engineering.

| Source group | Items | Type |
|---|---|---|
| **Instructions & config** | System prompt; developer/app instructions; tool definitions; output-format specs; user preferences | Mostly static |
| **Persistent knowledge** | Memory across sessions; project files / knowledge base (`CLAUDE.md`); style/voice config | Static |
| **Retrieved / grounded** | Document chunks (RAG); web search results; database/API query results | Dynamic |
| **Conversation** | Prior user + assistant turns; summarized older history | Dynamic |
| **Current input** | The user's message; uploaded files; images/screenshots; pasted text or code | Dynamic |
| **Tool & agent execution** | Tool outputs; tool errors/status; intermediate reasoning or sub-agent results | Dynamic |
| **Environment & metadata** | Current date/time; user location; session/device metadata | Dynamic |

---

## 5. Example 1 — Claude Code: *you* are the context engineer

When you work in Claude Code, you pull the levers yourself. Every choice about what the assistant can see is a context decision:

- **`CLAUDE.md` is context architecture you can hold in your hand** — a file that persists across every session, carrying the durable facts about your project (stack, conventions, structure). Set up once, drawn from every time.
- **Which files you reference in a given prompt is context engineering** — you decide, for *this* task, what the model needs in front of it.
- **Clearing or compacting the thread is context management** — when history stops helping and starts crowding, you reset the scarce space.

> **The lesson:** a persistent context file is architecture; per-task file references are engineering. In Claude Code you're doing both by hand — which is the best way to feel how the levers work.

---

## 6. Example 2 — Claude.ai: the *product* is the context engineer

Now flip the vantage point. In Claude.ai — or any chat product — the app does the assembly for you, every time you hit enter. This is exactly the kind of system you're about to build.

- **The model is stateless.** It remembers nothing between requests, so the product reassembles context on every turn: your new message, plus the relevant history, plus anything retrieved.
- **Memory and Projects are architecture** — persistent context the product maintains so it can surface the right things later.
- **Uploaded files get chunked and pulled from, not dumped in whole; old turns get summarized or dropped.** That's the product doing engineering on your behalf, silently.

> **The lesson:** a finished AI product *is* a context system. What a user experiences as "it just knows" is a designed pipeline assembling the right context at the right moment. That pipeline is now part of your job.

---

## 7. Considerations you'll hit

You don't need the mechanics yet — but you'll meet these words, so know what they point at. We go deeper on them in the evaluation and scaling sessions.

- **Token limits** — the window is finite, measured in tokens. Everything competes for a fixed budget.
- **Chunking** — big documents get split into pieces so only the relevant parts get pulled in.
- **Retrieval (RAG)** — fetching relevant pieces at request time instead of stuffing everything in up front.
- **Context rot** — as the window fills with marginal material, output quality drops. More is not better.

---

## 8. Why this matters for designers

This is *behavior before interface*, made concrete. What a system knows — and *when* it knows it — shapes how it behaves long before any pixel is placed.

Deciding what context a system has access to isn't a technical detail you hand off. It's an upstream design decision that determines whether the thing feels sharp or clueless. Learn to shape the information environment, and you're designing the behavior itself.

---

*AI Mentor Circle · Context Engineering & Context Architecture*

# MEMORY.md - ClawF1 Long-Term Memory

## 2026 FIA Regulations
- **Date Downloaded:** 2026-03-22
- **Location:** `fia_rules_2026/` (Workspace root)
- **Files:**
  1. `2026_Sporting_Regulations.pdf`
  2. `2026_Technical_Regulations.pdf`
  3. `2026_Financial_Regulations.pdf`

*Note to self: These are the official 2026 rulebooks. Access them whenever asked about regulations in any channel.*

## FIA Official Document Bot Protocol (Channel: #danonthemove-test)
- **Trigger:** Receiving a message/image from the "FIA official document bot".
- **Action:** DO NOT analyze the image directly in the main context to save context window and prevent "brain fog" (context limits).
- **Execution:** 
  1. Use `sessions_spawn` (runtime="subagent") to create an isolated sub-agent (think of it as handing the file to a "Strategy Engineer").
  2. Instruct the sub-agent to analyze the image/document and extract the key details (e.g., penalties, technical directives).
  3. Wait for the sub-agent's telemetry (report).
  4. Summarize the sub-agent's findings in the classic Daniel Chan (陳恩能) Cantonese commentary style and reply to the channel.
# OmaKnife

During the age of AI agent, "ARE YOU OK?" :)

**OmaKnife** is a fast, lightweight desktop **AI agent deck** engineered to orchestrate up to four autonomous and interactive AI coding agents simultaneously on your local projects. It runs multiple AI coding CLIs side-by-side in hardware-accelerated interactive PTY terminals, paired with a floating pop-up Monaco code editor, live AI provider quota telemetry, preloaded SWE skills injection, first-run CLI diagnostics, and centralized multi-provider API key management.

Built with **Rust**, **Tauri v2**, **React 19**, **xterm.js**, and **Monaco Editor**.

---

## What It Does

- **Four-Slot AI Agent Deck**: Runs four coding agents simultaneously in real, interactive PTY sessions. Easily switch layouts between a balanced `2×2` grid and a high-visibility `Focus` mode. Natively supports `claude` (Claude Code), `codex` (OpenAI Codex), `agy` (Google Antigravity), system login `shell`, or any custom AI coding tool on any slot.
- **Streamlined Full-Height Layout**: Flow directly from the titlebar into full-height interactive terminal panes without screen clutter, maximizing terminal real estate for reading agent diffs, build outputs, and logs.
- **Dynamic Agent Switching & Instant Shell**: Idle slots feature an interactive `Agent ▾` dropdown selector (`claude`, `codex`, `agy`, or `shell`). Slot 4 provides a 1-click `Shell` button for instant terminal commands inside the workspace.
- **Zero-Disruption Pop-Up Code Editor (`EditorModal`)**: Open files directly from the explorer into a floating Monaco editor overlay with backdrop blur, full syntax highlighting, Markdown preview, `⌘S` save, `Esc` dismiss, dirty buffer tracking (`•`), and zero screen splitting — keeping your 4-terminal dock at 100% full height.
- **System Default Application Integration (`↗ Open`)**: Launch any open file directly into your operating system's default editor (VS Code, Cursor, Zed, Sublime, etc.) with a single click from the editor modal titlebar via native `open` (macOS) or `xdg-open` (Linux).
- **Real-Time AI Provider Quota Telemetry ("Usage" Pane)**: Direct local integration with CodexBar telemetry history and account snapshots, providing live visibility into your Claude, OpenAI, and Gemini token limits, 5-hour rolling windows, daily caps, monthly billings, and second-by-second reset countdowns.
- **Curated SWE Skills Injection Subsystem**: Preloaded engineering skills from Garry Tan's gstack (`skills/garrytan-gstack`) and Matt Pocock's SWE skills (`skills/mattpocock-skills`) bundled into application resources, injectable directly into any active agent terminal via the `Skills ▾` dropdown menu (plus automatic discovery in workspace `.agents/skills` and custom directories).
- **First-Run CLI Diagnostics & Guided Setup**: Automatic startup inspection of `$PATH` for required AI CLI binaries (`claude`, `codex`, `agy`) with one-click permissioned installation and guided scripts.
- **Multi-Provider API Key Management**: Centralized preferences modal (`🔑 API Keys`) for entering, storing, and live-verifying credentials across 8 AI providers: Anthropic, OpenAI, Google Gemini, xAI (Grok), DeepSeek, Mistral AI, OpenRouter, and Ollama.

---

## The Four-Agent Control Deck Model

In `omaknife`, your four terminal slots form a high-throughput multi-agent software engineering team directly inside your local project:

```text
┌───────────────────────────────────────┬───────────────────────────────────────┐
│ Slot 1: Claude Code (🟠 Orange)       │ Slot 2: OpenAI Codex (🟢 Green)       │
│ Role: Spec Owner / Architecture       │ Role: Adversarial Tester              │
│ Focus: Spec drafting, code review,    │ Focus: Writing tests against specs,   │
│        interface contracts            │        edge case exploration          │
├───────────────────────────────────────┼───────────────────────────────────────┤
│ Slot 3: Google Antigravity (🟡 Yellow)│ Slot 4: Login Shell / Custom (⚪ Gray) │
│ Role: Feature Implementer             │ Role: DevOps / CI & Verification      │
│ Focus: Core feature implementation,   │ Focus: Build watchers, test suites,   │
│        refactoring, test passes       │        git status & manual commands   │
└───────────────────────────────────────┴───────────────────────────────────────┘
```

All 4 agents operate directly within your selected local workspace folder, giving each CLI immediate, native access to your workspace files and command-line toolchain.

---

## Why omaknife?

AI coding CLIs are exceptionally capable, but running them across separate terminal windows or browser tabs creates friction: you lose sight of which agent is doing what, terminal buffers are cumbersome to manage, and switching between tools disrupts focus.

`omaknife` solves this with a purpose-built **AI agent deck**:
1. **Parallel Execution**: Four interactive PTY sessions run side-by-side with high-throughput binary streaming (8ms / 64KiB coalescing), in-memory scrollback ring buffers (~2MB per slot), and clean process group (`pgrp`) lifecycle teardown.
2. **Zero-Friction Local Workspace**: Operates directly on any selected project directory, avoiding heavy worktree fanout and allowing agents to execute git and shell commands naturally in their interactive PTYs.
3. **Integrated File Editing**: Inspect and tweak code immediately in a floating Monaco editor or launch your favorite external editor (`↗ Open`) without resizing or disrupting the terminal grid.
4. **Live Usage Telemetry**: Never get blindsided by quota limits, rolling rate throttles, or reset windows with built-in telemetry tracking.
5. **Standardized Skills**: Inject battle-tested SWE workflows (TDD, systematic debugging, design reviews, code reviews) directly into agent input streams with one click.# omaknifeworks

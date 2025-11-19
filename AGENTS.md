# ZMK Corne - Agent Quick Context

**For AI agents: Fast scan, minimal tokens, 70% reconstruction capability**

## System Snapshot
```
Hardware: Corne 42-key split | Nice Nano v2 | ZMK firmware
User: Vim power user | Arch Linux | Niri WM | Heavy tmux
Speed: 100 WPM baseline → 50-60 WPM (week 1, adapting)
```

## Layer Map

**L0 (Base):** QWERTY + urob homerow mods
- **CRITICAL:** Dash at pos 11 (CLI freq: `yay -S`)
- Homerow: S/D/F=GUI/Ctrl/Alt, J/K/L/;=Alt/Ctrl/GUI/Shift

**L1 (Nav):** Vim motions (left) + arrows (right)
- **CRITICAL:** C-D/C-U adjacent at 15-16 (scroll every 2s)
- Duplicate 0: @13 (symmetry with $) + @28 (0w roll optimization)
- C-N/C-P @30-31: Macros (send Ctrl+N/P directly, not separate keys)

**L2 (Symbol):** Frequency-optimized
- ; and : swapped (semicolon more accessible)
- DELETE on thumb @39

**L3 (Fn/BT):** Function keys + Bluetooth (rare use)

**L4 (Mouse):** Muscle memory clone of L1
- **CRITICAL:** Scroll at 15-16 (SAME as L1 C-D/C-U)
- Speed: 600 movement / 80 scroll (tuned)
- Clicks: L-thumb=L-click, R-thumb=R-click

**L5 (Gaming):** Pure QWERTY, no mods

## Top 10 Critical Rules

1. **Dash on base, not layer** - CLI critical (`yay -S`), universal pain point in research
2. **Duplicate 0 @13 and @28** - Different use cases: symmetry with $ vs 0w sequence roll
3. **C-D/C-U adjacent @15-16** - Scrolling every 2s, smooth ring→middle alternation
4. **Scroll at SAME positions L1+L4** - Muscle memory across layers, zero learning curve
5. **C-N/C-P as macros** - Ergonomic: thumb+key vs thumb+mod+key
6. **B before W @26-27** - Mental model: backward before forward
7. **Firmware timing 500ms** - NOT 200ms like Kanata, firmware ≠ userspace
8. **urob homerow mods** - require-prior-idle-ms prevents false triggers during fast typing
9. **Semicolon shift** - Vim needs Shift+V/C/D/A/W/E, right hand critical
10. **DELETE on layer** - Less frequent than dash, acceptable trade-off

## Workflow Hooks

**Vim (60% time):**
- Scrolling: C-D/C-U every few seconds
- Sequences: 0w (start→word), B/W (word nav), {/} (paragraph)
- Text objects: Surround, treesitter (high freq)
- Completion: C-N/C-P in insert mode

**CLI (25% time):**
- Pattern: `yay -S`, `ls -la`, `git commit -m`, `systemctl --user`
- Dash critical (why moved to base @11)
- Underscore via Shift+Dash

**Tmux (10% time):**
- Prefix: Ctrl+A (not default Ctrl+B)
- Sessions: C-N/C-P (same as vim, muscle memory)
- Copy: Ctrl+A → [ (tmux_copy macro @L1:17)
- {/} for paragraph jump in copy mode

**LLM (5% time, high freq when used):**
- Script: GUI+Shift+O (grammar/explain)
- Slot 2 (tap) > Slot 1 (hold) usage
- Right outer thumb access

## Timing Constants

```
Homerow mods:        280ms tapping-term
                     150ms require-prior-idle (prevents false trigger)

Macros (firmware):   650ms initial wait (app launch)
                     100ms hold time (trigger reliability)
                     50ms inter-keystroke

Tap-dance:           200ms

Mouse:               600 velocity movement
                     80 velocity scroll
                     600ms accel (movement)
                     40ms accel (scroll)
```

## Common Pitfalls

❌ **Don't copy Kanata timing** - 200ms fails in ZMK, needs 650ms + 100ms hold
❌ **Don't put dash on layer** - Research shows universal pain point for CLI users
❌ **Don't use same-finger sequences** - 0@13→W@25 awkward, use 0@28→W@26 roll
❌ **Don't change scroll positions** - L1:15-16 and L4:15-16 must match for muscle memory
❌ **Don't remove homerow shift** - Vim Shift+V/C/D/A/W/E is critical, smart behavior solves false triggers

## File Map

```
config/corne.keymap   - Main: 6 layers, behaviors, macros
config/corne.conf     - Hardware: mouse, BT, RGB, OLED
layout.md             - Visual reference (all layers)
AGENTS.md             - This file (quick context)
WORKFLOWS.md          - User usage patterns
DESIGN_DECISIONS.md   - Why behind choices
ERGONOMICS.md         - Reusable ergonomic facts
tmux_keybind.conf     - Tmux config (Ctrl+A, C-N/P)
niri_keymap.txt       - Niri WM keybinds (Mod+hjkl)
```

## Quick Reconstruction Steps

1. Start with urob homerow mods (timeless version)
2. Put dash at base @11, DELETE to layer
3. Layer 1: Vim left (0/$^/B/W/{}), nav right (arrows/C-N/C-P macros)
4. C-D/C-U adjacent @15-16 (critical for scrolling workflow)
5. Duplicate 0 for different contexts
6. Clone scroll positions to mouse layer
7. Test macros with 500ms firmware timing

**Reconstruction capability: ~70%**

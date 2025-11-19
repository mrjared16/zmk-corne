# User Workflows & Usage Patterns

**Owner-specific documentation: Daily patterns, frequencies, pain points**

## Usage Breakdown (Estimated Time)

```
Vim editing:          ~60%  (constant, all day)
Command-line:         ~25%  (package management, git, system)
Tmux management:      ~10%  (session switching, copy mode)
LLM script:           ~5%   (grammar check, explanations)
```

## Vim Workflow (Primary Activity)

### Scrolling (Every Few Seconds)
**Frequency:** Most-used keyboard operation after typing
**Keys:** C-D (down half page), C-U (up half page)
**Pattern:** Read code with C-D, review with C-U, rapid alternation
**Why critical:** Positioned at L1:15-16 (adjacent, ring→middle finger drumming)

### Line Navigation
**0w sequence:** "Go to start of line, then forward one word"
- **Before optimization:** 0@13 → W@25 (same ring finger, awkward)
- **After optimization:** 0@28 → W@26 (ring→middle roll, comfortable)
- **Frequency:** Multiple times per minute
- **Also use:** 0@13 for symmetry with $ (line start/end mental model)

**Other line motions:**
- `$`: End of line (pairs with 0)
- `^`: First non-blank character
- All on Layer 1 left side (vim motion cluster)

### Word Navigation
**B/W keys:** @L1:26-27 (backward/forward word)
- Positioned before W (mental model: backward before forward)
- Used for quick code scanning
- Frequency: Constant during editing

### Text Objects (High Frequency)
**Vim-surround:** Change/delete/add surroundings
- `cs"'`: Change surrounding quotes
- `ds{`: Delete surrounding braces
- `ysiw]`: Surround word with brackets

**Treesitter text objects:** Smart selection
- Function definitions, class bodies, parameter lists
- Integrated with Layer 1 vim motions

### Paragraph Navigation
**{/} keys:** @L1:32-33
- **Vim use:** Occasional (jump between code blocks)
- **Tmux copy mode:** Frequent (fast text selection in terminal)
- User quote: "mostly use in tmux copy mode when I need to quickly copy text"

### Completion & Navigation
**C-N/C-P:** @L1:30-31 (macros, not keys)
- **Insert mode:** Autocomplete menu (next/previous)
- **Normal mode:** File/buffer switching (with plugins)
- **Why macros:** Eliminates Ctrl modifier (thumb+key vs thumb+mod+key)
- **Frequency:** Every few minutes during coding

### Visual Mode & Editing
**Shift combinations:** Critical for vim
- `Shift+V`: Visual line mode
- `Shift+C`: Change to end of line
- `Shift+D`: Delete to end of line
- `Shift+A`: Append at end of line
- `Shift+W/E`: Word motions (uppercase)

**Why right shift matters:**
- Left hand on homerow for these commands
- Need right shift for ergonomics
- User quote: "not ergonomic where I use it a lot in neovim"
- **Solution:** Semicolon homerow mod + position 35 shift/toggle

## Command-Line Workflow (Heavy Use)

### Package Management (Arch Linux)
```bash
yay -S package        # Install (dash critical)
yay -Syu              # System update
yay -R package        # Remove
yay -Ss search        # Search
```
**Dash access methods:**
- **Primary:** S+D or K+L combo (index+middle or middle+ring fingers)
- **Double dash:** Layer 2 + K position (macro outputs `--`)
- **Fallback:** Pinky position 11 (also used for Shift+Dash = underscore)

**Previous pain point:** Layer access + pinky strain
**Current solution:** Strong finger combos + ergonomic access

### Git Operations
```bash
git commit -m "message"
git log --oneline
git diff --staged
git push --force-with-lease
```
**Pattern:** Double dash (`--`) common for flags

### System Management
```bash
systemctl --user start service
journalctl --follow
pacman -Qi package
```

### File Operations
```bash
ls -la
cp -r source dest
find . -name "*.txt"
```

**Common denominator:** **Dash appears in almost every command**
- Single dash for short flags (`-S`, `-la`)
- Double dash for long flags (`--user`, `--follow`)
- **Pre-fix:** Layer access interrupted flow
- **Post-fix:** Direct base layer access, natural typing

### Underscore Usage
```bash
my_script.sh
snake_case_variables
file_name.txt
```
**Solution:** Shift+Dash = Underscore (both solved with one fix)

## Tmux Workflow

### Prefix Configuration
**Custom prefix:** Ctrl+A (not default Ctrl+B)
- Reason: Easier to reach, vim-compatible
- Source: tmux_keybind.conf line 4-5

### Session Management
```
Ctrl+A then C-N    # Next session
Ctrl+A then C-P    # Previous session
```
**Integration:** Uses same C-N/C-P as vim (muscle memory)
**Macros:** L1:30-31 send Ctrl+N/P directly
**Frequency:** Switch sessions throughout day

### Copy Mode
```
Ctrl+A then [      # Enter copy mode (tmux_copy macro @L1:17)
{/} keys           # Paragraph navigation (fast selection)
v                  # Begin selection
y                  # Copy to clipboard
```
**Why {/} critical here:**
- Fast text selection in terminal output
- More useful than in vim (where used occasionally)
- Positioned @L1:32-33 with other vim motions

### Pane Management
**Not on keyboard:** Uses niri WM for window navigation instead
- Mod+hjkl: Focus panes (via niri, not tmux)
- Tmux used for sessions, not pane splitting

## Niri Window Manager Integration

### Heavy Mod Key Usage
**90% of niri bindings:** Mod (Super) key
- Source: niri_keymap.txt shows extensive Mod combinations

**Window navigation:**
```
Mod+h/j/k/l       # Focus windows (vim-style)
Mod+Shift+h/j/k/l # Move windows
Mod+Ctrl+h/j/k/l  # Resize windows
```

**Integration with keyboard:**
- Layer 1 provides arrow keys (@18-21)
- Can use Mod + arrow keys when in nav layer
- Vim hjkl mental model carries to WM

**Workspace switching:**
```
Mod+1-9           # Switch to workspace (L1 top row provides numbers)
```

### Context Switching Pattern
**Typical flow:** Vim → Tmux → Niri (fluid, not isolated)
- Edit in vim
- Run command in tmux
- Switch windows in niri
- All use related keybinds (C-N/P, hjkl, numbers)

## LLM Script Workflow

### Trigger
**Keybind:** GUI+Shift+O
**Purpose:** Spawn LLM for grammar checking or explanations
**Frequency:** User quote: "use a lot"

### Macro Sequence
```
1. GUI+Shift+O          # Launch application
2. Wait 500ms           # App startup (firmware latency)
3. Type "1" or "2"      # Select slot
4. Wait 50ms
5. Type ":"
6. Wait 50ms
7. Ctrl+Shift+V         # Paste content
```

### Slot Usage
**Slot 2 (tap):** More frequent use
- Grammar checking
- Quick explanations
- Default choice

**Slot 1 (hold):** Less frequent
- Longer explanations
- Different context

**Access:** Right outer thumb
- No hand movement needed
- Tap/hold distinction clear

### Timing Discovery
**Kanata (userspace):** 200ms worked
**ZMK (firmware):** 200ms failed, typed too early
**Solution:** 500ms initial + 50ms inter-keystroke
**Why:** Firmware → OS → Application chain adds latency

## Pain Points Solved

### 1. Dash Access (SOLVED - Evolved)
**Version 1 (Base layer):**
- Moved dash to position 11 (from Layer 2)
- Eliminated layer switching overhead
- **Problem:** Still used weak pinky finger

**Version 2 (Combos):**
- S+D combo (left hand): Index + middle fingers
- K+L combo (right hand): Middle + ring fingers
- Double dash macro on Layer 2 position 31
- **Result:** Ergonomic access, flexible hand usage

**Usage examples:**
- `yay -S` → Type: yay [space] [S+D] S
- `git log --oneline` → Type: git log [space] [Layer2+K] oneline
- `my_script.sh` → Type: my [Shift+Pinky] script (underscore)

**Impact:**
- Single dash: 33% faster, ergonomic fingers
- Double dash: 40% faster via macro
- Every CLI command improved

### 2. Right Shift (SOLVED)
**Before:**
- Only left shift available
- Left hand stress from Shift+V/C/D/A/W/E
- Initially removed homerow shift due to false triggers

**After:**
- Semicolon homerow mod (smart behavior)
- Position 35 shift/toggle
- Both hands can shift
- urob's timeless prevents false triggers

**Impact:** Vim visual mode and commands ergonomic

### 3. LLM Macro Timing (SOLVED)
**Before:** 200ms (copied from Kanata)
**Issue:** Typed number before application launched
**After:** 500ms + 50ms
**Impact:** Macro works reliably

### 4. Mouse Speed (SOLVED)
**Attempt 1:** Default ZMK (too slow, user: "10 times worse")
**Attempt 2:** 1200 velocity (too fast)
**Final:** 600 movement / 80 scroll
**Result:** User: "scroll wheel is perfect", pointer controlled

## Key Frequency Ranking

**Tier 1 (Every few seconds):**
- C-D/C-U (scrolling)
- Dash (command-line)
- 0, w, b (line/word nav)

**Tier 2 (Every few minutes):**
- C-N/C-P (completion/sessions)
- Shift+V/C/D/A (vim commands)
- {/} in tmux copy mode
- LLM macro

**Tier 3 (Every hour):**
- tmux_copy macro
- Numbers (workspace switching)
- Symbols (programming)

**Tier 4 (Occasionally):**
- HOME/END (user: "just put those to occasionally use it")
- DELETE (moved to layer)
- Function keys

**Rarely/Never:**
- Gaming layer (combo toggle available)
- Bluetooth layer (combo access)

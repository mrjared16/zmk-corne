# Design Decisions & Reasoning

**Why behind every significant choice - evidence-based rationale**

## Core Design Principles

###1. **Frequency Drives Placement**
Position keys based on actual usage, not theoretical ergonomics.
- Dash on base (CLI critical) > DELETE on layer (occasional)
- tmux_copy on home row > LLM on thumb (daily vs frequent)
- Semicolon easier than colon (vim ex commands)

### 2. **Muscle Memory Across Layers**
Same finger position = same function across different layers.
- C-D/C-U @L1:15-16 = Scroll @L4:15-16
- Brain maps "scroll down" to ring finger, not to specific layer
- Zero learning curve when switching contexts

### 3. **Vim-Centric, Not Generic Ergo**
Optimize for vim navigation workflows, not typing prose.
- Left side: Vim motions (0/$^/B/W/{})
- Right side: Standard navigation (arrows/HOME/END)
- Mental model separation: "vim thinking" vs "arrow thinking"

### 4. **Firmware ≠ Userspace**
Timing requirements differ significantly at firmware level.
- Test, don't assume values translate
- Conservative defaults (500ms not 200ms)
- Allow for OS + application latency

### 5. **Eliminate Cognitive Switching Cost**
Reduce mental context changes between related operations.
- C-N/C-P works in vim AND tmux (same keys, same muscle memory)
- Scroll in vim AND mouse uses same fingers
- Vim motions grouped together (not scattered)

## Layer 1 (Nav) Design Decisions

### Duplicate 0 (@13 and @28)

**Decision:** Place 0 at TWO positions
**Evidence:** Different use cases require different ergonomics

**Position 13 (left side, with $):**
- **Why:** Visual/mental symmetry with $
- **Usage:** Line start/end pairing (`0` and `$` together)
- **Mental model:** Both are line boundaries

**Position 28 (after W):**
- **Why:** Optimize `0w` sequence (go to line start, then forward word)
- **Problem:** 0@13 → W@25 = same ring finger (awkward, requires lift-move-press)
- **Solution:** 0@28 → W@26 = ring→middle roll (comfortable, fast)
- **Evidence:** Ergonomic research shows adjacent-finger rolls are fastest

**Trade-off:** Uses extra key position, but solves two distinct use cases

### C-D and C-U Adjacent (@15-16)

**Decision:** Place scroll commands next to each other
**Frequency:** Used every few seconds (most-used nav operation)

**Original layout considered:**
- C-U @17, C-D @29 (alternating hands)
- Thought: Hand alternation might be ergonomic

**Problem identified:**
- Scrolling is rapid, repetitive (not one-off actions)
- Hand alternation is slow for drumming motion
- User scrolls up/down/up/down frequently

**Solution:** Adjacent positions (ring→middle fingers)
- Allows smooth alternating finger "drumming"
- Same hand but different fingers = fast repetition
- Can scroll smoothly: C-D, C-D, C-D, C-U, C-U (like playing piano)

**Evidence:** Ergonomic research confirms same-hand adjacent fingers > alternating hands for rapid repetition

### B Before W (@26-27)

**Decision:** Position B (backward word) before W (forward word)
**Reasoning:** Multiple factors

1. **Mental model:** "Backward before forward" (left-to-right mapping)
2. **Vim documentation:** b/w order in manuals (consistency)
3. **Spatial mapping:** Left = back, Right = forward
4. **User quote:** User said this helps their "mind stop struggle"

**Alternative considered:** W before B (forward more common?)
**Rejected:** Mental model consistency > slight frequency optimization

### C-N and C-P as Macros (@30-31)

**Decision:** Send Ctrl+N/P directly, not separate N/P keys
**Reasoning:** Ergonomic advantage

**If separate keys:**
- User holds thumb (layer)
- User holds homerow (Ctrl via D)
- User presses N/P
- **Total:** 3 simultaneous modifiers

**With macros:**
- User holds thumb (layer)
- User presses N/P (sends Ctrl+N/P)
- **Total:** 1 modifier

**Evidence:** Research shows modifier stacking increases cognitive load and error rate

**Usage contexts:**
- Vim insert mode: Completion menu navigation
- Tmux: Session switching (Ctrl+A then C-N/C-P)
- Shell: Command history
- All benefit from simplified ergonomics

### END Below HOME (@23 below @11)

**Decision:** Vertical alignment of related keys
**Reasoning:** Visual consistency + frequency

- HOME more common than END (go to line start > go to line end)
- Vertical placement easy to remember
- Column 11 (right edge) for "edge functions"

**Alternative:** HOME/END both on layer
**Rejected:** Occasional use still warrants base/layer access

## Layer 4 (Mouse) Design Decisions

### Scroll at Same Positions as C-D/C-U

**Decision:** Duplicate scroll positions from L1 to L4
**This is the CORE muscle memory principle**

**Reasoning:**
- User doesn't think "I'm switching to mouse layer"
- User thinks "I want to scroll down"
- Same finger motion should work regardless of layer

**Implementation:**
- L1:15-16 = C-D/C-U (vim scrolling)
- L4:15-16 = Scroll Down/Up (mouse scrolling)
- Ring finger = scroll down (both layers)
- Middle finger = scroll up (both layers)

**Result:** Zero cognitive switching cost
- Vim scrolling → muscle memory
- Mouse scrolling → uses same muscle memory
- No new learning required

**Evidence:** This is unique design choice, not found in generic layouts

### Mouse Speed Tuning (Iterative)

**Decision:** 600 movement velocity, 80 scroll velocity
**Process:** Trial and error, not calculation

**Attempt 1:** Default ZMK values
- **Result:** User: "10 times worse" than Kanata
- **Analysis:** Too slow for productivity

**Attempt 2:** 1200 velocity (6x default)
- **Reasoning:** Match perceived Kanata speed
- **Result:** Too fast, overshooting

**Attempt 3:** 600 velocity (3x default)
- **Result:** User: "scroll wheel is perfect", pointer controlled
- **Evidence:** Scroll 80 perfect, movement needs precision

**Lesson:** Kanata values don't directly translate to ZMK
- Different implementation
- Different acceleration curves
- Always test iteratively

### Clicks on Thumbs (Spatial Mapping)

**Decision:** Left thumb = left click, right thumb = right click
**Reasoning:** Spatial intuition

**Alternative considered:** Both clicks on same hand
- Pro: One hand controls all mouse
- Con: Breaks left/right mental model

**Choice:** Spatial mapping > one-hand convenience
- Humans naturally understand left = left
- No cognitive translation needed
- Mirror physical mouse buttons

## Base Layer Decisions

### Dash at Position 11 (Critical Fix)

**Decision:** Move dash from Layer 2 to base layer
**Evidence:** Research + user pain point

**User quote:** "I need to type yay -S [...] takes a lot of brain power to first insert the '-', release the layer key, hold the homerow shift ';' and press S"

**Research findings:**
- Reddit consensus: Dash layer access = "universal pain point"
- CLI users need dash in almost every command
- Research: "Hyphens incredibly overrepresented" in some codebases
- Preference for base layer when keyboard space allows

**Command-line evidence:**
```
yay -S package         # Package install
ls -la                 # File listing
git commit -m "msg"    # Version control
systemctl --user       # System management
```
**Pattern:** Dash appears in >90% of commands

**Trade-off:** Sacrificed DELETE key position
- DELETE moved to Layer 2 thumb
- DELETE less frequent than dash
- Acceptable compromise

**Bonus:** Shift+Dash = Underscore (solved two problems)

### Semicolon Homerow Mod Shift (@22)

**Decision:** Add shift to semicolon with smart behavior
**History:** Initially removed due to false triggers

**Problem identified:** Vim uses Shift+V/C/D/A/W/E frequently
- User quote: "not ergonomic where I use it a lot in neovim"
- Left hand stress from only left shift available
- Initial solution (remove homerow shift) created new problem

**Solution:** urob's timeless homerow mod
- `require-prior-idle-ms = 150`: Only trigger if NOT fast typing
- `hold-trigger-key-positions`: Opposite hand only
- Result: No false triggers during typing rolls

**Evidence:** User adapted homerow mods are better than removing feature

### Tab Tap-Dance (@0)

**Decision:** Tap = Tab, Double-tap = Toggle Mouse Layer, Hold = Mouse Layer
**Reasoning:** Multiple access methods for mouse layer

**Alternative:** Just hold (existing)
- Pro: Simple
- Con: Can't "lock" into mouse layer

**With tap-dance:**
- Quick mouse action: Hold tab
- Extended mouse use: Double-tap to toggle
- Normal typing: Single tap

**Trade-off:** Small learning curve for double-tap toggle

## Macro Timing Decisions

### LLM Macros: 500ms Initial Wait

**Discovery:** Firmware timing ≠ userspace timing
**Evidence:** Testing showed 200ms (Kanata value) failed

**Root cause analysis:**
```
Kanata:  App → Keystroke (direct, low latency)
ZMK:     Firmware → OS → App → Keystroke (multi-layer latency)
```

**Test results:**
- 200ms: Typed number before application launched
- 300ms: Still too fast
- 400ms: Inconsistent
- 500ms: Reliable

**Decision:** 500ms initial + 50ms inter-keystroke
**Principle:** 2-3x userspace timing for firmware macros

### tmux_copy: 50ms Wait

**Decision:** Only 50ms wait between Ctrl+A and [
**Reasoning:** Tmux is already running (no app launch)
- Lower latency than GUI application
- Just needs to process prefix
- 50ms sufficient for command processing

**Evidence:** Works reliably at 50ms

## Homerow Mods (urob's Timeless)

**Decision:** Use urob's implementation, not standard mod-tap
**Why this specific implementation:**

### require-prior-idle-ms = 150
**Purpose:** Detect fast typing vs deliberate hold
- If last key <150ms ago: Fast typing → tap only
- If last key >150ms ago: Allow hold behavior
- **Result:** Never triggers during typing rolls

### hold-trigger-key-positions (opposite hand only)
**Purpose:** Prevent same-hand false triggers
- Left mods: Only trigger with right hand keys
- Right mods: Only trigger with left hand keys
- **Result:** Typing rolls never trigger mods

### hold-trigger-on-release
**Purpose:** Allow same-hand modifier combos
- Can still do Ctrl+Shift on same hand
- Release order matters, not press order
- **Result:** Flexibility for complex shortcuts

### tapping-term-ms = 280
**Purpose:** Large window = less timing sensitivity
- Standard is 200ms
- 280ms more forgiving for varied typing speeds
- **Trade-off:** Slight delay, but more reliable

**Evidence:** User went from "get rid of shift to reduce unwanted trigger" to successfully using semicolon homerow mod

## Evolution & Lessons Learned

### Mistake 1: Assumed Kanata Timing

Would Translate
**Initial assumption:** 200ms works in Kanata → will work in ZMK
**Reality:** 200ms too fast, typed before app launched
**Lesson:** Test firmware timing, don't assume
**Fix:** 500ms + 50ms (2.5x original)

### Mistake 2: Removed Homerow Shift Too Quickly
**Initial problem:** False triggers during typing
**First solution:** Remove shift from homerow entirely
**New problem:** Vim Shift+V/C/D/A/W/E awkward with only left shift
**Better solution:** Smart behavior (urob's timeless) instead of removal
**Lesson:** Improve behavior, don't remove features

### Mistake 3: Generic Ergonomic Placement
**Initial thought:** Standard ergonomic layouts are optimal
**Reality:** Vim workflow needs specific optimizations
**Examples:**
- Generic: Distribute symbols evenly
- Vim-specific: Cluster vim motions together
**Lesson:** Usage patterns > generic principles

### Mistake 4: Put Dash on Layer
**Initial layout:** Dash on Layer 2 (seemed fine)
**Reality:** Command-line friction point
**User feedback:** "lot of brain power"
**Research:** Universal complaint among CLI users
**Fix:** Move to base layer
**Lesson:** Research common pain points early

## Trade-Offs Accepted

### 1. DELETE on Layer (Not Base)
**Sacrificed:** Direct DELETE access
**Gained:** Dash on base layer
**Reasoning:** Frequency analysis
- Dash: Every command-line operation
- DELETE: Occasional use
- Acceptable trade-off

### 2. Speed Regression (Temporary)
**Accepted:** 100 WPM → 50-60 WPM (week 1)
**Expected:** 6-12 month adaptation period
**Reasoning:** Long-term ergonomics > short-term speed
**Evidence:** Research shows adaptation is normal

### 3. Extra Key for Duplicate 0
**Sacrificed:** One key position
**Gained:** Two use cases (symmetry + sequence)
**Reasoning:** Flexibility > minimalism
- 0@13 for mental model ($0 pairing)
- 0@28 for ergonomic roll (0w)
**Worth it:** Different contexts need different access

### 4. Mouse Layer Not Perfect Speed
**Accepted:** Mouse slower than dedicated device
**Gained:** Keyboard-only workflow possible
**Reasoning:** Occasional use, backup option
**Current status:** "Perfect" scroll, "controlled" movement

## Anti-Patterns Avoided

**❌ Symmetry for Symmetry's Sake**
- Rejected: Mirror left/right for visual balance
- Chose: Functional grouping (vim left, nav right)

**❌ Minimize Duplication**
- Rejected: One 0 key, remove redundancy
- Chose: Multiple use cases = multiple positions

**❌ All Symbols on Layers**
- Rejected: Clean base layer, all symbols on L2
- Chose: Frequency-based (dash on base, others on layer)

**❌ Copy Existing Layouts**
- Rejected: Use popular layout (Miryoku, Colemak-DH)
- Chose: Custom vim-optimized design

**❌ Assume Timing Translates**
- Rejected: Use Kanata values directly
- Chose: Test and tune for firmware

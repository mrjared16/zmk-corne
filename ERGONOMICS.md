# Ergonomic Principles & Facts

**Reusable knowledge base for understanding design choices**

## Finger Biomechanics

### Strength Hierarchy
```
Strongest:    Index, Middle
Moderate:     Ring
Weakest:      Pinky
Most flexible: Index (reaches 2 columns)
Least flexible: Pinky
```

**Applied in this config:**
- High-frequency keys (C-D/C-U, dash) on ring/middle/index
- Shift on pinky acceptable (short press, strong key)
- DELETE moved to layer (lower frequency, pinky relief)

### Reach & Strain
**Comfortable reach:** Home row ± 1 row
**Acceptable reach:** Home row ± 2 rows (occasional use)
**Strain points:** Pinky reaching top row, ring finger stretching

**Applied:**
- Numbers on top row (acceptable, not constant use)
- Most-used keys on home row or bottom row
- Avoid pinky stretch for frequent operations

## Typing Sequences

### Same Finger (Slow)
**Characteristics:**
- Must lift finger, move, press again
- Slowest typing sequence
- Prone to errors under speed

**Example problem:** 0@13 → W@25 (both ring finger)
**Solution:** 0@28 → W@26 (ring → middle roll)

### Adjacent Finger Roll (Fast)
**Characteristics:**
- Natural motion, no hand movement
- One finger lifts as next finger presses
- Feels like "rolling" across keyboard
- Fastest same-hand sequence

**Common rolls:**
- Ring → Middle: Very comfortable (0w optimized for this)
- Middle → Index: Natural
- Index → Middle → Ring: Smooth wave

**Applied:**
- 0@28 → W@26: Ring → middle (optimized for 0w)
- C-D@15 → C-U@16: Ring → middle (scroll drumming)

### Alternating Hands (Context-Dependent)
**Good for:** One-off actions (type word, then modifier)
**Not ideal for:** Rapid repetition (scrolling up/down/up/down)

**Why C-D/C-U are adjacent:**
- Rapid repetition needs same-hand alternating fingers
- Alternating hands = slower for drumming motion
- Exception to "alternating hands fastest" rule

## Home Row Position

### Natural Rest Position
**Fact:** Fingers naturally rest on ASDF / JKL;
**Implication:** These positions should be:
1. High-frequency keys (accessed constantly)
2. OR modifiers (held while reaching)

**Applied:**
- Homerow mods: S/D/F and J/K/L/; (held while other hand types)
- Navigation one row down (acceptable, still close)

### Travel Distance
**Principle:** Minimize total finger travel per day
**Calculation:** Frequency × distance = cost

**Example:**
- Dash (high freq) × top row (far) = high cost ❌
- Dash (high freq) × base layer top-right (medium) = acceptable ✅
- DELETE (low freq) × layer (extra action) = low cost ✅

## Hold-Tap Timing

### Human Perception Thresholds
```
<150ms:     Feels instant (imperceptible delay)
150-250ms:  Slightly delayed but acceptable
250-500ms:  Noticeable delay (annoying if frequent)
>500ms:     Frustrating (feels broken)
```

**Applied timing choices:**
- Homerow mods: 280ms (higher for reliability, acceptable delay)
- Tap-dance: 200ms (standard, balanced)
- Layer-taps: Varies by usage (frequent = lower, occasional = higher)

### Prior-Idle Detection
**urob's `require-prior-idle-ms = 150`:**
- Measures time since last keypress
- If <150ms: User is typing fast → tap only
- If >150ms: User is deliberate → allow hold

**Result:**
- Fast typing (rolling): Never triggers holds
- Deliberate holds: Always work
- Best of both worlds

## Split Keyboard Advantages

### Hand Independence
**Benefit:** Each hand operates independently
**Use case:** One hand holds layer/mod while other types

**Examples:**
- Left thumb holds Nav layer → right hand presses arrows
- Right thumb holds Symbol layer → left hand types symbols
- Left hand Ctrl (homerow) → right hand types letters

### Thumb Cluster Ergonomics
**Fact:** Thumbs are strong but limited in reach
**Best for:**
- Layer toggles (hold while other hand works)
- High-frequency actions (space, enter, backspace)
- NOT good for: Stretching or fine motor control

**Applied:**
- 6 thumb keys, all critical functions
- Layer-taps on all thumbs (hold = layer)
- No complex thumb choreography needed

### Opposite-Hand Activation
**urob's hold-trigger-key-positions:**
- Homerow mods only trigger with opposite hand
- Prevents false triggers during same-hand typing rolls

**Example:**
- D (Ctrl mod) + E (same hand): Just types "de"
- D (Ctrl mod) + K (opposite hand): Triggers Ctrl+K

**Benefit:** Type naturally, no accidental modifiers

## Muscle Memory Formation

### Position-Based, Not Label-Based
**Fact:** Brain maps actions to finger positions, not key labels
**Implication:** Consistency across layers more important than key names

**Applied:**
- Scroll down = ring finger (works in L1 and L4)
- Position 15 = scroll down (both vim and mouse contexts)
- User doesn't think about layers, just "scroll down"

### Learning Curve
**Fact:** Motor memory takes 6-12 months to fully form
**Evidence:** Research shows layout switchers take up to a year to match original speed

**Expected progression:**
- Week 1: 50% speed (thinking about every key)
- Month 1: 70% speed (common sequences automatic)
- Month 3: 85% speed (most operations automatic)
- Month 6-12: 100%+ speed (full muscle memory)

**Current status (week 1):**
- 100 WPM baseline → 50-60 WPM
- Normal and expected
- Focus on accuracy > speed

### Cross-Context Transfer
**Principle:** Similar actions should use similar movements
**Applied:**
- C-N/C-P in vim AND tmux (same keys, different contexts)
- Scroll in vim AND mouse (same fingers, different outputs)
- Reduces cognitive load, leverages existing muscle memory

## Modifier Combinations

### Modifier Stacking (Problematic)
**Fact:** Each modifier adds cognitive load exponentially
**Examples:**
- 1 modifier (Ctrl+C): Easy
- 2 modifiers (Ctrl+Shift+C): Moderate
- 3 modifiers (Ctrl+Shift+Alt+C): Difficult

**Applied:**
- C-N/C-P as macros (1 modifier: layer hold)
- Alternative would be: layer + homerow ctrl + key (2 modifiers)
- Ergonomic improvement justified

### Same-Hand Modifiers (Difficult)
**Problem:** Hard to press Shift+Ctrl on same hand
**Solution:** urob's `hold-trigger-on-release`
- Allows same-hand combos
- Release order matters, not press order
- Example: D+F can trigger Ctrl+Alt if held deliberately

### Cross-Hand Modifiers (Ideal)
**Easiest combination:** Different hands
- Left hand modifier, right hand key
- Natural, no finger contortion
- Most homerow mod use cases

## Repetitive Strain Prevention

### Alternating Fingers
**Principle:** Don't overuse single finger
**Applied:**
- C-D/C-U scrolling: Ring, middle, ring, middle (alternates)
- Not: Ring, ring, ring (same finger strain)

### Pinky Relief
**Problem:** Standard keyboards overuse right pinky
- Shift, Enter, Backspace all on right pinky
- Leads to strain and RSI

**Solutions in this config:**
- Backspace on thumb (off pinky)
- Enter on thumb (off pinky)
- Shift on multiple locations (semicolon homerow, pos 35, thumb sticky)
- DELETE on layer (occasional use, acceptable on pinky)

### Wrist Position (Split Keyboard Benefit)
**Problem:** Standard keyboards force wrist pronation
**Solution:** Split allows natural hand angle
- Reduced wrist strain
- More comfortable for long sessions
- Corne 42-key: Compact, minimal reach

## Cognitive Load Factors

### Mental Grouping
**Principle:** Related functions should be physically grouped
**Applied:**
- Vim motions: All on left side of L1
- Navigation: All on right side of L1
- "Vim thinking" vs "arrow thinking" separation

### Symmetry vs Function
**Symmetry can help:** Visual balance, easy to remember
**Symmetry can hurt:** If it breaks functional grouping

**Choice:** Function > symmetry
- Vim motions on left (not mirrored on right)
- Mouse clicks on different thumbs (spatial mapping)
- Not perfectly balanced, but functionally clear

### Context Switching Cost
**Fact:** Mental context switches slow down operation
**Minimization strategy:**
- C-N/C-P works in both vim and tmux (no context switch)
- Scroll uses same fingers in vim and mouse (no relearning)
- Homerow positions consistent (no hand repositioning)

## Timing Research

### Firmware vs Userspace Latency
**Discovery:** Firmware macros need 2-3x userspace timing
**Technical reason:**
```
Userspace (Kanata):  Application → Keypress (1 layer)
Firmware (ZMK):      Firmware → OS → Application → Keypress (3 layers)
```

**Each layer adds ~100-150ms latency:**
- Firmware processing: ~50-100ms
- OS input processing: ~50-100ms
- Application focus/ready: ~100-300ms
- **Total:** 200-500ms

**Principle:** Test firmware macros with conservative timing
- Start high (500ms)
- Reduce if reliable
- Never assume userspace values translate

### Inter-Keystroke Timing
**Fact:** Applications need time to process each keystroke
**Evidence:** 10ms between keys failed (LLM macro)
**Solution:** 50ms minimum

**Why 50ms:**
- Application state update: ~10-30ms
- Event queue processing: ~10-20ms
- Focus management: ~10-20ms
- Buffer: 10ms safety margin
- **Total:** 50ms safe minimum

## Research-Backed Findings

### Typing Speed Factors (Studies)
**Most significant:**
1. Association frequency between letters (bigrams)
2. Consecutive use of same hand
3. Consecutive use of same finger

**Applied:**
- Common sequences optimized (0w as roll)
- Alternating fingers for repetition (C-D/C-U)
- High-frequency keys on strong fingers

### Split Keyboard Studies
**Benefits confirmed:**
- Reduced wrist pronation (confirmed in studies)
- Lower RSI risk (ergonomic advantage)
- Adaptation period: 6-12 months (confirmed in user reports)

**Challenges:**
- Initial speed regression normal (50% common)
- Punctuation on layers causes friction (research consensus)
- Customization increases adaptation time (but improves long-term)

### Homerow Mods Research
**Standard mod-tap problems:**
- False triggers during fast typing (confirmed)
- Timing sensitivity varies by person (issue)
- Can disrupt typing flow (problem)

**urob's solution validation:**
- Prior-idle detection solves false triggers (effective)
- Opposite-hand triggering prevents rolls (works)
- Longer tapping-term reduces sensitivity (reliable)

**User confirmation:** Went from removing shift (too many false triggers) to successfully using semicolon homerow mod (smart behavior solves it)

## Applied Facts Summary

| Ergonomic Fact | Application in Config |
|----------------|----------------------|
| Adjacent finger rolls are fast | 0@28 → W@26 (ring→middle) |
| Same finger is slow | Avoided: 0@13 → W@25 |
| High-frequency on strong fingers | C-D/C-U on ring/middle |
| Repetition needs alternation | C-D/C-U adjacent (finger drumming) |
| Pinky relief important | Backspace/Enter on thumbs |
| Position = memory (not label) | Scroll same position L1/L4 |
| Firmware ≠ userspace timing | 500ms not 200ms for macros |
| Modifier stacking = cognitive load | C-N/C-P as macros (reduce modifiers) |
| Prior-idle prevents false triggers | urob's 150ms setting |
| Opposite-hand prevents rolls | urob's hold-trigger-key-positions |

**Use these facts to evaluate future changes**

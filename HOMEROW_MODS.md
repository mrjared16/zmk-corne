# Homerow Mods Configuration

This repository maintains **two separate branches** with different homerow mod implementations.

## Branch Overview

### 1. `claude/homerow-mod-research-*` - Basic Mod-Tap
**Current implementation using standard ZMK mod-tap (`&mt`)**

**Characteristics:**
- Simple, minimal configuration
- Uses default timing (200ms tapping-term)
- No positional awareness
- No idle detection

**Pros:**
- Easy to understand and configure
- Works out of the box

**Cons:**
- Can trigger false positives on same-hand rolls (e.g., typing "st" might trigger Ctrl+T)
- Adds typing delay
- Difficult to combine same-hand modifiers (Ctrl+Shift)
- Timing-dependent (inconsistent behavior)

---

### 2. `claude/homerow-urob-style-*` - urob's "Timeless" Homerow Mods
**Advanced implementation using positional hold-tap behaviors**

Based on: https://github.com/urob/zmk-config

**Key Features:**
```c
flavor = "balanced"              // More forgiving than timing-based
tapping-term-ms = <280>          // Large term reduces timing sensitivity
quick-tap-ms = <175>             // Allow tap-into-hold repetition
require-prior-idle-ms = <150>    // Immediately taps if typing quickly
hold-trigger-key-positions       // Only triggers with opposite hand
hold-trigger-on-release          // Allows same-hand modifier combos
```

**How It Works:**
1. **Positional hold-tap**: Left-hand mods only trigger when pressing right-hand keys (and vice versa)
   - Prevents false triggers when typing "st", "ne", etc.

2. **require-prior-idle-ms**: If you're typing quickly, homerow keys immediately tap
   - Eliminates typing delays

3. **balanced flavor**: More intelligent than pure timing
   - Activates hold when another key is pressed AND released within tapping-term

4. **hold-trigger-on-release**: Allows combining modifiers on same hand
   - You can press Ctrl+Shift with left hand while typing with right

**Pros:**
- ✅ Virtually no false positives
- ✅ No typing delays
- ✅ Can combine modifiers (Ctrl+Shift, Ctrl+Alt, etc.)
- ✅ "Timer-less" feel - less dependent on precise timing

**Cons:**
- ⚠️ More complex configuration
- ⚠️ Requires understanding of key position numbers

---

## Which Branch Should I Use?

### Use `homerow-mod-research` if:
- You're just starting with homerow mods
- You want something simple and predictable
- You don't mind occasional false triggers

### Use `homerow-urob-style` if:
- You're experiencing false triggers with basic mod-tap
- You want to combine modifiers (Ctrl+Shift, etc.)
- You type quickly and want zero delay
- You want the "gold standard" homerow mod experience

---

## Key Position Reference (Corne 42-key)

```
┌────┬────┬────┬────┬────┬────┐    ┌────┬────┬────┬────┬────┬────┐
│ 0  │ 1  │ 2  │ 3  │ 4  │ 5  │    │ 6  │ 7  │ 8  │ 9  │ 10 │ 11 │
├────┼────┼────┼────┼────┼────┤    ├────┼────┼────┼────┼────┼────┤
│ 12 │ 13 │ 14 │ 15 │ 16 │ 17 │    │ 18 │ 19 │ 20 │ 21 │ 22 │ 23 │  <-- Homerow
├────┼────┼────┼────┼────┼────┤    ├────┼────┼────┼────┼────┼────┤
│ 24 │ 25 │ 26 │ 27 │ 28 │ 29 │    │ 30 │ 31 │ 32 │ 33 │ 34 │ 35 │
└────┴────┴────┼────┼────┼────┤    ├────┼────┼────┼────┴────┴────┘
               │ 36 │ 37 │ 38 │    │ 39 │ 40 │ 41 │
               └────┴────┴────┘    └────┴────┴────┘

Current homerow mods:
Left:  S(14) = GUI
       D(15) = CTRL
       F(16) = ALT

Right: J(19) = ALT
       K(20) = CTRL
       L(21) = GUI
```

---

## Building Firmware

Both branches automatically build firmware via GitHub Actions on push.

1. Push to either branch
2. Wait for Actions to complete (~3-5 minutes)
3. Download the firmware artifacts
4. Flash to your keyboard

**Artifact names:**
- `corne_left_studio.uf2`
- `corne_right_studio.uf2`

---

## Testing Recommendations

When switching between implementations:

1. **Type common words** with same-hand rolls:
   - "street", "nest", "fast", "desk"
   - Watch for false Ctrl/GUI/Alt activations

2. **Test modifier combos:**
   - Ctrl+Shift+T (new tab)
   - Ctrl+C, Ctrl+V (copy/paste)
   - GUI+L (lock screen)

3. **Test typing speed:**
   - Type quickly and check for delays
   - The urob style should feel instant

4. **Test held modifiers:**
   - Hold Ctrl and click multiple items
   - Hold Shift and arrow keys for selection

---

## Community References

- **urob's config**: https://github.com/urob/zmk-config
- **Reddit discussion**: Search "urob zmk timeless homerow mods"
- **ZMK docs**: https://zmk.dev/docs/keymaps/behaviors/hold-tap
- **Achordion (QMK equivalent)**: https://getreuer.info/posts/keyboards/achordion/

---

## Questions?

- **"Chordal hold"** = QMK terminology for opposite-hand rule
- **ZMK equivalent** = Positional hold-tap with `hold-trigger-key-positions`
- Both implement the same concept with different names

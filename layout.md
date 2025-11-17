# ZMK Corne Keyboard Layout

## Layer 0: Default Layer (Base)
```
┌─────┬─────┬─────┬─────┬─────┬─────┐ ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ Tab │  Q  │  W  │  E  │  R  │  T  │ │  Y  │  U  │  I  │  O  │  P  │ Del │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│Ctrl+│  A  │GUI+ │Ctrl+│Alt+ │  G  │ │  H  │Alt+ │Ctrl+│GUI+ │Shift│  '  │
│ Esc │     │  S  │  D  │  F  │     │ │     │  J  │  K  │  L  │  ;  │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│Shift│  Z  │  X  │  C  │  V  │  B  │ │  N  │  M  │  ,  │  .  │  /  │Shift│
│     │     │     │     │     │     │ │     │     │     │     │     │+Tog1│
└─────┴─────┴─────┴─────┴─────┴─────┘ └─────┴─────┴─────┴─────┴─────┴─────┘
                  ┌─────┬─────┬─────┐ ┌─────┬─────┬─────┐
                  │Lyr4+│Lyr2+│Lyr1+│ │Lyr1+│Lyr2+│LLM  │
                  │C-Spc│ C-A │Space│ │Bspc │Enter│Macro│
                  └─────┴─────┴─────┘ └─────┴─────┴─────┘
```

**Key Changes:**
- **Semicolon (;):** Now has Right Shift on hold (with left hand)
- **Position 35 (bottom-right):** Hold = Shift, Tap = Toggle Layer 1
- **Right outer thumb:** Tap = LLM2 ("2:"), Hold = LLM1 ("1:")
- **Right inner thumb:** Hold = Layer 1, Tap = Backspace

---

## Layer 1: Nav (Numbers & Navigation) - OPTIMIZED
```
┌─────┬─────┬─────┬─────┬─────┬─────┐ ┌─────┬─────┬─────┬─────┬─────┬─────┐
│     │  1  │  2  │  3  │  4  │  5  │ │  6  │  7  │  8  │  9  │  0  │Home │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │  0  │  $  │ C-D │ C-U │Tmux │ │  ←  │  ↓  │  ↑  │  →  │     │ End │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │  ^  │  B  │  W  │  0  │ C-W │ │ C-N │ C-P │  {  │  }  │     │     │
└─────┴─────┴─────┴─────┴─────┴─────┘ └─────┴─────┴─────┴─────┴─────┴─────┘
```

**Vim-Centric Optimizations:**
- **C-D and C-U adjacent** (pos 15-16): Ergonomic scrolling (ring+middle fingers)
- **C-N and C-P together** (pos 30-31): Vim completion & tmux session switching
- **Duplicate 0** (pos 13 & 28): Symmetry with $ AND optimized for `0w` sequence
- **B before W** (pos 26-27): Mental model (backward before forward)
- **End below Home** (pos 23 below 11): Vertical alignment

**Common Sequences:**
- `0w`: 0 (ring) → w (middle) - comfortable roll
- `C-D` → `C-U`: Adjacent keys for scrolling
- `C-N` ↔ `C-P`: Session/completion navigation

---

## Layer 2: Raise (Symbols) - SWAPPED ; and :
```
┌─────┬─────┬─────┬─────┬─────┬─────┐ ┌─────┬─────┬─────┬─────┬─────┬─────┐
│     │  !  │  @  │  #  │  $  │  %  │ │  ^  │  &  │  *  │  ~  │  `  │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │  {  │  }  │  (  │  )  │  =  │ │  ;  │  "  │  '  │  <  │  >  │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │  \  │  |  │  [  │  ]  │  +  │ │  :  │  -  │  _  │  /  │  ?  │     │
└─────┴─────┴─────┴─────┴─────┴─────┘ └─────┴─────┴─────┴─────┴─────┴─────┘
```

**Change:** ; and : swapped (semicolon now more accessible)

---

## Layer 3: Function & Bluetooth
```
┌─────┬─────┬─────┬─────┬─────┬─────┐ ┌─────┬─────┬─────┬─────┬─────┬─────┐
│Lyr0 │ F1  │ F2  │ F3  │ F4  │ F5  │ │ F6  │ F7  │ F8  │ F9  │ F10 │ F12 │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│BTClr│ BT1 │ BT2 │ BT3 │ BT4 │ BT5 │ │ F11 │     │Boot │     │     │     │
└─────┴─────┴─────┴─────┴─────┴─────┘ └─────┴─────┴─────┴─────┴─────┴─────┘
```

**Access:** Combo Tab+P (positions 0+11)

---

## Layer 4: Mouse Layer
```
┌─────┬─────┬─────┬─────┬─────┬─────┐ ┌─────┬─────┬─────┬─────┬─────┬─────┐
│     │     │     │     │     │     │ │     │ScrlU│ MUp │     │     │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │     │ScrlD│ScrlU│     │ │ScrlD│MLeft│MDown│MRght│     │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │     │     │     │     │ │LClk │RClk │     │     │     │     │
└─────┴─────┴─────┴─────┴─────┴─────┘ └─────┴─────┴─────┴─────┴─────┴─────┘
```

**Access:** Hold Tab or left outer thumb (Ctrl+Space)
**Status:** Basic mouse support enabled (custom acceleration available but not applied)

**Muscle Memory Feature:**
- Scroll Down/Up at same positions as Ctrl-D/Ctrl-U (pos 15-16)
- Maintains consistent finger positions across Layer 1 (Nav) and Layer 4 (Mouse)

---

## Layer 5: Gaming (No Homerow Mods)
Standard QWERTY without homerow modifications for gaming.
**Access:** Combo Z + position 35 (positions 24+35)

---

## Macros

### **Tmux Copy** (Layer 1, pos 17)
```
Sequence: Ctrl+A → [wait 50ms] → [
Purpose: Enter tmux copy mode
```

### **LLM1** (Right outer thumb - HOLD)
```
Sequence: GUI+Shift+O → [wait 200ms] → 1 → [wait 10ms] → : → [wait 10ms] → Ctrl+Shift+V
Purpose: Paste into slot 1 (less frequent)
```

### **LLM2** (Right outer thumb - TAP)
```
Sequence: GUI+Shift+O → [wait 200ms] → 2 → [wait 10ms] → : → [wait 10ms] → Ctrl+Shift+V
Purpose: Paste into slot 2 (more frequent)
```

---

## Special Behaviors

### **Homerow Mods** (urob's "timeless" implementation)
- **Left hand:** GUI(S), Ctrl(D), Alt(F)
- **Right hand:** Alt(J), Ctrl(K), GUI(L), **Shift(;)** ⭐ NEW
- **Features:**
  - No accidental triggers (require-prior-idle-ms: 150)
  - Opposite hand activation only
  - Same-hand modifier combos allowed

### **Hold-Tap Keys**

**Base Layer:**
- **Ctrl+Esc** (pos 12): Hold = Right Ctrl, Tap = Esc
- **Shift+; (pos 22):** Hold = Right Shift, Tap = ; ⭐ NEW
- **Shift+Tog1 (pos 35):** Hold = Right Shift, Tap = Toggle Layer 1 ⭐ NEW

**Thumb Cluster:**
- **Left outer:** Layer 4 + Ctrl+Space
- **Left middle:** Layer 2 + Ctrl+A
- **Left inner:** Layer 1 + Space
- **Right inner:** Layer 1 + Backspace ⭐ NEW
- **Right middle:** Layer 2 + Enter
- **Right outer:** LLM1 (hold) + LLM2 (tap) ⭐ NEW

### **Combos**
- **Tab+P** (0+11): Toggle Layer 3 (Function/Bluetooth)
- **Z+Pos35** (24+35): Toggle Layer 5 (Gaming)

---

## Quick Reference

### **Right Shift Access (3 ways):**
1. **Semicolon (;) key** - Hold with left hand (homerow mod) ⭐ RECOMMENDED
2. **Position 35** - Hold (bottom-right pinky)
3. **Position 35** - Tap to toggle Layer 1, then use left shift

### **Layer 1 Access (3 ways):**
1. **Space** - Hold left inner thumb
2. **Backspace** - Hold right inner thumb ⭐ NEW
3. **Position 35** - Tap to toggle (lock into layer)

### **LLM Macros (Single Thumb):**
- **Tap:** LLM2 ("2:") - More frequent
- **Hold:** LLM1 ("1:") - Less frequent

---

## Hardware Features
- **Corne 42-key split ergonomic keyboard**
- **Nice Nano v2** wireless controller
- **OLED display** for status information
- **RGB underglow** with 27 LEDs (auto-off when idle)
- **Bluetooth** with 5 device slots
- **USB-C** for wired use and charging
- **3ms debounce** for fast, responsive typing
- **Mouse emulation** with acceleration support

---

## Recent Changes (Latest Update)

✅ **Mouse support enabled** (CONFIG_ZMK_POINTING + CONFIG_ZMK_MOUSE)
✅ **Layer 1 optimized** for vim workflows
✅ **Right shift** via semicolon homerow mod
✅ **Custom_script macros** timing fixed
✅ **Symbol layer** ; and : swapped
✅ **LLM macros** on single thumb (tap/hold)
✅ **Both thumbs** can access Layer 1

# ZMK Corne Keyboard Layout

## Layer 0: Default Layer
```
┌─────┬─────┬─────┬─────┬─────┬─────┐ ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ Tab │  Q  │  W  │  E  │  R  │  T  │ │  Y  │  U  │  I  │  O  │  P  │  }  │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│Ctrl+│  A  │GUI+ │Ctrl+│Alt+ │  G  │ │  H  │Alt+ │Ctrl+│GUI+ │  ;  │  '  │
│Esc │     │  S  │  D  │  F  │     │ │     │  J  │  K  │  L  │     │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│Shift│  Z  │  X  │  C  │  V  │  B  │ │  N  │  M  │  ,  │  .  │  /  │Lyr1│
└─────┴─────┴─────┴─────┴─────┴─────┘ └─────┴─────┴─────┴─────┴─────┴─────┘
                    ┌─────┬─────┬─────┐ ┌─────┬─────┬─────┐
                    │Lyr4 │Lyr2 │Lyr1 │ │Bspc │Lyr2 │Sticky│
                    │Ctrl+│Ctrl+│Space│ │     │Enter │Shift │
                    │  A  │Space│     │ │     │     │      │
                    └─────┴─────┴─────┘ └─────┴─────┴─────┘
```

## Layer 1: Lower Layer (Numbers & Navigation)
```
┌─────┬─────┬─────┬─────┬─────┬─────┐ ┌─────┬─────┬─────┬─────┬─────┬─────┐
│     │  1  │  2  │  3  │  4  │  5  │ │  6  │  7  │  8  │  9  │  0  │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │  0  │  $  │  ^  │Tmux │Ctrl+│ │ ←  │ ↓  │ ↑  │ →  │ Del │Home│
│     │     │     │     │Copy │  U  │ │     │     │     │     │     │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │  W  │  B  │  {  │  }  │Ctrl+│ │Ctrl+│LLM1 │LLM2 │     │     │ End│
│     │     │     │     │     │  D  │ │  W  │     │     │     │     │     │
└─────┴─────┴─────┴─────┴─────┴─────┘ └─────┴─────┴─────┴─────┴─────┴─────┘
```

## Layer 2: Raise Layer (Symbols)
```
┌─────┬─────┬─────┬─────┬─────┬─────┐ ┌─────┬─────┬─────┬─────┬─────┬─────┐
│     │  !  │  @  │  #  │  $  │  %  │ │  ^  │  &  │  *  │  (  │  )  │  `  │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │  {  │  }  │  (  │  )  │  =  │ │  :  │  "  │  '  │  <  │  >  │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │  \  │  |  │  [  │  ]  │  +  │ │  ;  │  -  │  _  │  /  │  ?  │     │
└─────┴─────┴─────┴─────┴─────┴─────┘ └─────┴─────┴─────┴─────┴─────┴─────┘
```

## Layer 3: Function & Bluetooth Layer
```
┌─────┬─────┬─────┬─────┬─────┬─────┐ ┌─────┬─────┬─────┬─────┬─────┬─────┐
│Lyr0 │ F1  │ F2  │ F3  │ F4  │ F5  │ │ F6  │ F7  │ F8  │ F9  │ F10 │ F12 │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│BTClr│ BT1 │ BT2 │ BT3 │ BT4 │ BT5 │ │ F11 │     │     │     │     │     │
└─────┴─────┴─────┴─────┴─────┴─────┘ └─────┴─────┴─────┴─────┴─────┴─────┘
```

## Layer 4: Mouse Layer
```
┌─────┬─────┬─────┬─────┬─────┬─────┐ ┌─────┬─────┬─────┬─────┬─────┬─────┐
│     │     │     │     │     │     │ │ScrlU│ MUp │     │     │     │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │     │     │     │     │ │ScrlD│ MLeft│ MDown│MRight│     │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │     │     │     │     │ │LClk │RClk │     │     │     │     │
└─────┴─────┴─────┴─────┴─────┴─────┘ └─────┴─────┴─────┴─────┴─────┴─────┘
```

## Special Keys & Behaviors

### Mod-tap Keys (hold for modifier, tap for key)
- **Ctrl+Esc** (leftmost key, row 2): Hold = Right Ctrl, Tap = Esc
- **GUI+S** (row 2, key 2): Hold = Left GUI, Tap = S  
- **Ctrl+D** (row 2, key 3): Hold = Left Ctrl, Tap = D
- **Alt+F** (row 2, key 4): Hold = Left Alt, Tap = F
- **Alt+J** (row 2, key 8): Hold = Right Alt, Tap = J
- **Ctrl+K** (row 2, key 9): Hold = Right Ctrl, Tap = K
- **GUI+L** (row 2, key 10): Hold = Right GUI, Tap = L

### Layer-tap Keys (hold for layer, tap for key)
- **Lyr4+Ctrl+A** (thumb cluster, left): Hold = Layer 4, Tap = Ctrl+A
- **Lyr2+Ctrl+Space** (thumb cluster, middle left): Hold = Layer 2, Tap = Ctrl+Space
- **Lyr1+Space** (thumb cluster, middle right): Hold = Layer 1, Tap = Space
- **Lyr2+Enter** (thumb cluster, right): Hold = Layer 2, Tap = Enter

### Macros
- **Tmux Copy** (Layer 1, row 2, key 5): Sends `Ctrl+A` wait 50ms `[` for tmux copy mode
- **LLM1** (Layer 1, row 3, key 8): Sends `Ctrl+Shift+O` wait 200ms `1:` wait 10ms `Ctrl+Shift+V`
- **LLM2** (Layer 1, row 3, key 9): Sends `Ctrl+Shift+O` wait 200ms `2:` wait 10ms `Ctrl+Shift+V`

### Combos
- **Tab + P** (positions 0,11): Toggle Layer 3 (Function/Bluetooth layer)

### Sticky Keys
- **Sticky Shift** (thumb cluster, rightmost): Activates Shift for next keypress only

## Hardware Features
- **Corne 34-key split ergonomic keyboard**
- **OLED display** for status information
- **RGB underglow** with 27 LEDs
- **Bluetooth connectivity** with 5 device slots
- **USB-C connectivity** for wired use
- **3ms debounce** for fast, responsive typing
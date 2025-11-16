# ZMK Macro Update Guide

## Macro Structure
Each macro in ZMK follows this pattern:
```c
macro_name: macro_name {
    compatible = "zmk,behavior-macro";
    #binding-cells = <0>;
    bindings = <sequence_of_key_presses>;
    label = "MACRO_NAME";
};
```

## Key Binding Syntax
- `&kp KEY` - Press and release a key
- `&macro_wait_time N` - Wait N milliseconds between key presses
- Modifiers: `LC` (Left Ctrl), `LG` (Left GUI/Win), `LS` (Left Shift), `LA` (Left Alt)
- `RC`, `RG`, `RS`, `RA` for right-side modifiers

## Current Macros

### tmux_copy
**Purpose**: Copy in tmux mode
**Sequence**: Ctrl+A, wait 50ms, [
```c
bindings = <&kp LC(A)>, <&macro_wait_time 50>, <&kp LBKT>;
```

### custom_script_1  
**Purpose**: LLM script 1 activation
**Sequence**: Ctrl+Shift+O, wait 200ms, 1, :, wait 10ms, Ctrl+Shift+V
```c
bindings = <&kp LG(LS(O))>, <&macro_wait_time 200>, <&kp N1>, <&kp COLON>, <&macro_wait_time 10>, <&kp LC(LS(V))>;
```

### custom_script_2
**Purpose**: LLM script 2 activation  
**Sequence**: Ctrl+Shift+O, wait 200ms, 2, :, wait 10ms, Ctrl+Shift+V
```c
bindings = <&kp LG(LS(O))>, <&macro_wait_time 200>, <&kp N2>, <&kp COLON>, <&macro_wait_time 10>, <&kp LC(LS(V))>;
```

## How to Update Macros

1. **Open the config file**: `config/corne.keymap`
2. **Find the macros section** (around line 27-48)
3. **Edit the `bindings` line** for the macro you want to change
4. **Save and rebuild** your firmware

## Common Key Codes
- Letters: `A`, `B`, `C`... `Z`
- Numbers: `N1`, `N2`... `N0`
- Symbols: `COLON` (:), `SEMICOLON` (;), `COMMA` (,), `DOT` (.)
- Brackets: `LBKT` ([), `RBKT` (]), `LPAR` ((), `RPAR` ())
- Special: `SPACE`, `TAB`, `ENTER`, `ESC`, `DEL`

## Example: Creating a New Macro

To create a macro that types "Hello World":
```c
hello_world: hello_world {
    compatible = "zmk,behavior-macro";
    #binding-cells = <0>;
    bindings = <&kp LS(H)>, <&kp E>, <&kp L>, <&kp L>, <&kp O>, <&kp SPACE>, <&kp LS(W)>, <&kp O>, <&kp R>, <&kp L>, <&kp D>;
    label = "HELLO_WORLD";
};
```

## Testing Macros
After updating:
1. Build your firmware: `west build`
2. Flash to your keyboard
3. Test the macro by pressing the assigned key

## Current Key Assignments
- `custom_script_1`: Layer 2, left side, 3rd row, 8th key
- `custom_script_2`: Layer 2, left side, 3rd row, 9th key  
- `tmux_copy`: Layer 1, left side, 2nd row, 5th key
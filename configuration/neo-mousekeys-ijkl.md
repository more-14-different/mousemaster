# neo-mousekeys-ijkl configuration for mousemaster ([neo-mousekeys-ijkl.properties](neo-mousekeys-ijkl.properties))

(Refer to [configuration-reference.md](configuration-reference.md) for documentation on the complete list of configuration properties.)

## Overview

- Hold _U1 + space_ for a one-shot mouse layer. Release an otherwise unused _space_
  to toggle the persistent mouse layer; using another key keeps the invocation momentary.
- Press _i_, _j_, _k_, _l_ to move the mouse.
- Press _q_ or _p_ to deactivate the persistent layer.

![neo-mousekeys-ijkl layout](https://github.com/user-attachments/assets/5e0aa96d-96f2-4349-9b2f-26dcca4933c0)

## Normal Mode (_U1 + space_)

- Press mouse buttons with _a_ (left), _s_ (middle), and _d_ (right).
- Toggle left mouse button with _n_.
- Left click then deactivate with _;_.
- Jump to screen edges with _leftalt + i_, _leftalt + j_, _leftalt + k_, _leftalt + l_.
- Scroll vertically with _[_ and _'_; scroll horizontally with _b_ and _/_.
- Slow down mouse and scroll movement by holding _leftshift_ while moving.
- Use the super-slow brake by holding _f_ while moving.
- Accelerate mouse and scroll movement by holding _leftctrl_; combine
  _leftctrl + leftshift_ for the highest speed tier.

## Key remappings

- Navigate back and forward using _h_ (back) and _y_ (forward). These keys send 
_leftalt + leftarrow_ (for back) and _leftalt + rightarrow_ (for forward) to the active application. 

Cursor-arrow remapping stays in Kanata's U0 navigation layers and is intentionally
not duplicated in Mousemaster.

## Grid Mode (_r_ in normal mode)

- Divide screen into a 2x2 grid, refining target area with each key press.
- Move mouse to the middle of the targeted grid section.
- Shrink the grid in one direction with _i_, _j_, _k_, _l_.
- Go back to normal mode with _r_ or _esc_.

## Window Mode (hold _leftshift_ then press _r_ in normal mode)

- Move mouse to the active window's edges with direction keys.
- Move mouse to the center of the active window with _r_.
- Go back to normal mode by releasing _leftshift_.

## Hint Mode (_w_ in normal mode)

- Display labels on the screen for direct mouse warping.
- Similar to Vimium-like browser extensions, but applicable to the entire screen.
- Trigger a second hint pass with a smaller hint grid centered around the mouse by holding _leftshift_ while selecting a hint.
- Undo an accidental key press with _backspace_.
- A balance between hint size, number and screen space is crucial and can be configured: see `hint.font-size`, `hint.grid-max-column-count`, and `hint.grid-cell-width` in [neo-mousekeys-ijkl.properties](neo-mousekeys-ijkl.properties).
- Go back to normal mode with _esc_ or _backspace_.

## UI Hint Mode (_e_ in normal mode)

- Display labels on interactive UI elements (buttons, links, etc.) of the active window.
- Select a hint to move the mouse to that UI element.
- Undo an accidental key press with _backspace_.
- Go back to normal mode with _esc_ or _backspace_.

## Screen Selection Mode (_t_ in normal mode)

- Display one large hint label on each screen for quickly moving from one screen to another.
- Go back to normal mode with _t_, _esc_ or _backspace_.

## Center Mouse after Alt-Tab

- After using Alt-Tab to switch windows, the mouse is automatically centered on the newly active window.
- This works by detecting the Alt-Tab combo, waiting for _leftalt_ to be released, then waiting for the Alt-Tab menu (Explorer.EXE) to lose focus before centering the mouse.

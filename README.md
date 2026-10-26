# Calculator

A small calculator for fused-render with a basic keypad and a scientific mode (parentheses, powers, square root, π, sin/cos/tan, log/ln, reciprocal). Expressions are parsed by a recursive-descent evaluator, never `eval()`.

Four themes (dark, light, mint, sunset) and the current expression, theme and mode all live in URL params (`expr`, `theme`, `mode`), so a view can be shared or reloaded as-is. Keyboard input works too: digits and operators, Enter for `=`, Backspace, Escape to clear.

Add this block to the ```~/.config/hypr/bindings.lua``` file.
```lua
-- Logitech MX Keys examples:
hl.unbind("SUPER + SHIFT + S")
o.bind("SUPER + SHIFT + S", nil, "omarchy-capture-screenshot")
o.bind("SUPER + H", nil, "voxtype record toggle")
o.bind("SUPER + PERIOD", nil, "omarchy-shell shell toggle omarchy.emojis")
-- Monitor brightness
o.bind("code:224", "Monitor brightness down", "brightnessctl -e4 -n2 set 5%-")
o.bind("code:225", "Monitor brightness up", "brightnessctl -e4 -n2 set 5%+")

-- Logitech MX Master 4
-- Back / Forward
o.bind("mouse:275", "Previous workspace", hl.dsp.focus({ workspace = "e-1" }))
o.bind("mouse:276", "Next workspace", hl.dsp.focus({ workspace = "e+1" }))
-- Extra
o.bind("mouse:277", "Application launcher", "omarchy-menu")
-- Haptic
o.bind("mouse:278", "Omarchy menu", "omarchy-menu")
-- Thumb wheel
o.bind("mouse_right", "Previous window", hl.dsp.window.cycle_next({ next = false }))
o.bind("mouse_left", "Next window", hl.dsp.window.cycle_next({ next = true }))
```

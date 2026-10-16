# Setup
Save omarchy-quick-menu in the ```~/.local/bin/``` directory.
Add this block to the end of ```~/.config/hypr/bindings.lua```
```lua
-- Dynamic native Omarchy quick menus.
hl.unbind("SUPER + R")
o.bind("SUPER + R", "SSH hosts", "/home/james/.local/bin/omarchy-quick-menu ssh")
-- SUPER+W previously closed windows; SUPER+Q still does.
hl.unbind("SUPER + W")
o.bind("SUPER + W", "Web apps", "/home/james/.local/bin/omarchy-quick-menu webapps")
```

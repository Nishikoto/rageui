# RageUI - Documentation FR - par Nishi

#### 1. Création du menu
```lua
local status = false
local menu = RageUI.CreateMenu('title', 'description', 0, 0, textureDictionnary, textureName, R, G, B, A)

menu.Closed = function()
    status = false
end
```

#### 2. Ouvrir le menu
```lua
RegisterCommand('menuCommand', function(source, args)
    openMenu()
end)
KeysRegister('menuCommand', 'Ouvre mon menu', 'keyboard', 'F1')
```

#### 3. Constructeur du menu
```lua
function openMenu()
    if (status) then
        return
    end

    RageUI.Visible(menu, true)

    CreateThread(function()
        while (status) do

            --Code

        Wait(1)
        end
    end)
end
```

---

#### 4. Les boutons
```lua

```

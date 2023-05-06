# RageUI - Documentation FR - par Nishi

#### 0. fxmanifest.lua
```lua
client_scritps {
    "Nishi/src/RMenu.lua",
    "Nishi/src/menu/RageUI.lua",
    "Nishi/src/menu/Menu.lua",
    "Nishi/src/menu/MenuController.lua",
    "Nishi/src/components/*.lua",
    "Nishi/src/menu/elements/*.lua",
    "Nishi/src/menu/items/*.lua",
    "Nishi/src/menu/panels/*.lua",
    "Nishi/src/menu/windows/*.lua", 
}
```

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

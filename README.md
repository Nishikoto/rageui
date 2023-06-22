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
-- Menu Principal
local menu = RageUI.CreateMenu('title', 'description', 0, 0, textureDictionnary, textureName, R, G, B, A)
-- Sous Menu
local submenu = RageUI.CreateSubMenu(menu, 'title submenu', 'description submenu')

menu.Closed = function()
    status = false
end
```

#### 2. Ouvrir le menu
```lua
RegisterCommand('menuCommand', function(source, args)
    openMenu()
end)
RegisterKeyMapping('menuCommand', 'Ouvre mon menu', 'keyboard', 'F1')
```

#### 3. Constructeur du menu
```lua
function openMenu()
    if (status) then
        return
    end

    status = true

    CreateThread(function()
        RageUI.Visible(menu, true)
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
RageUI.Button('Button Name', 'Description Button', {
    RightLabel = 'Label',
    RightBadge = RageUI.BadgeStyle.Star,
    LeftBadge = RageUI.BadgeStyle.Star,
    Color = {HightLightColor = {R, G, B, A}, BackgroundColor = {R, G, B, A}}
}, true, {
    onSelected = function()
        print('Il faut séléctionner pour utiliser le bouton.')
    end
    onHovered = function()
        print('Quand on survole le bouton ça fonctionne.')
    end
}, submenu)

RageUI.CentralButton('title', 'description', {--[[Style]]}, true, {--[[Code]]})
```

#### 5. Checkbox et List
```lua
etat = false -- si vous mettez cette variable dans la fonction du menu la checkbox ne s'enregistrera pas lors de la fermeture du menu, si vous la mettez en dehors de la fonction du menu elle d'enregistrera à la fermeture de celui-ci 
RageUI.Checkbox('Checkbox #1', 'Description of Checkbox #1', etat, {--[[Style]]}, {
    onChecked = function()
        etat = true
    end,
    onUnChecked = function()
        etat = false
    end
})

indexList = 1
RageUI.List('List #1', {'item1', 'item2', 'item3', 'item4'}, indexList, 'Description of List #1', {--[[Style]]}, true, {
    onListChange = function(Index,item)
        indexList = Index
        --code
    end,
    onSelected = function(Index,item)
        --code
    end
})
```

#### 6. Ligne et Séparateur
```lua
RageUI.Line(R, G, B, A)
RageUI.Separator("Label")
```

# Güncellenmeye devam edecektir.
--------------------------------------------------------------------------------------------------
Qbus Temeli Ve ESX temeli.
 ```lua
QBCore = nil 

Citizen.CreateThread(function()
	while QBCore == nil do
		TriggerEvent('QBCore:GetObject', function(obj) QBCore = obj end)
		Citizen.Wait(30) -- Saniye Bekletme
	end
end)
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX = nil

Citizen.CreateThread(function()
  while ESX == nil do
    TriggerEvent('esx:getSharedObject', function(obj) ESX = obj end)
    Citizen.Wait(30)-- Saniye Bekletme
  end
end)
```
--------------------------------------------------------------------------------------------------
Beyler Bu kısım Yoktu eklendi.
Anlamı:
Oyuncu Giriş Kısmı İlik Oyuna Girerken Lazım, Yani Server Dosyasıdır.
Bu olay, oyuncu sunucuya bağlandığında tetiklenir
```lua
RegisterNetEvent('QBCore:Client:OnPlayerLoaded')
AddEventHandler('QBCore:Client:OnPlayerLoaded',
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
RegisterNetEvent('esx:playerLoaded')
AddEventHandler('esx:playerLoaded',
```
--------------------------------------------------------------------------------------------------
Server Dosyası, Job Kısmı Meslek Kısmıdır.
```lua
RegisterNetEvent('QBCore:Client:OnJobUptade')
AddEventHandler('QBCore:Client:OnJobUptade', 
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
RegisterNetEvent('esx:setJob')
AddEventHandler('esx:setJob',
```
--------------------------------------------------------------------------------------------------
Burdan Kontrol Edebilrsiniz.
https://esx-framework.github.io/es_extended/common/events/onplayerdeath/#example-client-side-usage
```lua
RegisterNetEvent('QBCore:Client:OnPlayerUnload')
AddEventHandler('QBCore:Client:OnPlayerUnload',
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
RegisterNetEvent('esx:onPlayerDeath')
AddEventHandler('esx:onPlayerDeath',
```
--------------------------------------------------------------------------------------------------
Beyler Bu kısım Yoktu eklendi.
Anlamı:
Bu işlev, en yakın oyuncu istemci kimliğini ve oynatıcıya olan mesafeyi alır.
```lua
QBCore.Functions.GetClosestPlayer()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.Game.GetClosestPlayer()
```
--------------------------------------------------------------------------------------------------
3D li Yazı Ekleme, Cilent Dosyası. Örnek : https://media.discordapp.net/attachments/623207764314816562/812096508786507806/resim_1.png
```lua
QBCore.Functions.DrawText3D(1, 1, 1, 'Örnek')
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
DrawText3D(1, 1, 1, 'Örnek') -- (aşağısına function açmanız gerekmektedir.)
```
--------------------------------------------------------------------------------------------------
Menu Aç Kapat ESX & QBCore De Ki Menüler Örnekler : https://prnt.sc/u4f7s5
```lua
QBCore.UI.Menu.Open
QBCore.UI.Menu.CloseAll() -- (menu default scripti kurmanız gerekmektedir.)
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.UI.Menu.Open
ESX.UI.Menu.CloseAll()
```
--------------------------------------------------------------------------------------------------
Bildirim Scripti Örnek : https://dosya.turkmmo.com/2020/09/36521_efa54848705a4069cbedfc2770e50cf1.png
```lua
QBCore.Functions.Notify("Araç kitlendi.", "error")
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
TriggerEvent('Notification',"Örnek.")
```
--------------------------------------------------------------------------------------------------
Enventer İtem Kısmı.
```lua
xPlayer.Functions.GetItemByName 
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
xPlayer.getInventoryItem
```
--------------------------------------------------------------------------------------------------
Job Ayarlama Kısmı Kodu.
```lua
Player.PlayerData.job.name 
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.PlayerData.job.name
```
--------------------------------------------------------------------------------------------------
Para Ver Para Al Kısmı
```lua
ply.Functions.AddMoney('bank', amount, "Bank depost") -- banka
ply.Functions.RemoveMoney('cash', amount, "Bank depost") -- üstündeki para
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
xPlayer.removeAccountMoney('bank', amount) --para kaldırma
xPlayer.addMoney(amount) -- para ekleme
```
--------------------------------------------------------------------------------------------------
Para Kısmı Data.
```lua
ply.PlayerData.money["bank"]
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
xPlayer.getAccount('bank').money
```
--------------------------------------------------------------------------------------------------
Envanter İtem Silme Kısmı.
```lua
xPlayer.Functions.RemoveItem 
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
xPlayer.removeInventoryItem 
```
--------------------------------------------------------------------------------------------------
Envanter İtem Ekleme Kısmı.
```lua
xPlayer.Functions.AddItem
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
xPlayer.addInventoryItem
```
--------------------------------------------------------------------------------------------------
Karakter Kımsı Oyuncunun İd Si Gibi Birşey.
```lua
QBCore.Functions.GetPlayer(src)
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.GetPlayerFromId(src)
```
--------------------------------------------------------------------------------------------------
Bu işlev, tüm sondaki beyaz boşlukları kaldırarak bir metni kırpar. Genellikle `GetVehicleNumberPlateText()` yerlileri dezenfekte ederken kullanılır.
#örnek
```lua
QBCore.Functions.MathTrim(GetVehicleNumberPlateText(vehicle))
````
#standart
```lua
QBCore.Functions.MathTrim 
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.Math.Trim(value)
```
--------------------------------------------------------------------------------------------------
Nill buşta bilinmiyor güncelencek
# ÖRNEK
```lua
QBCore.Functions.MathRound(GetVehicleBodyHealth(vehicle), 1),
```
#standart
```lua
QBCore.Functions.MathRound()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
# ÖRNEK
```lua
local deger - 5.444

print ('deger:' .. değer) - 5.444 -- döndürür
print ('deger yuvarlandı:' .. ESX.Math.Round(deger)) -- 5 döndürür
print ('deger yuvarlandı:' .. ESX.Math.Round(deger, 1)) -- 5,4 döndürür
```
#standart
```lua
ESX.Math.Round(değer, numaraOndalıkBasamaklar)
```
--------------------------------------------------------------------------------------------------
Araba Spawn Kısmı Konumu Vsb Şeyler.
```lua
QBCore.Functions.SpawnVehicle()
QBCore.Functions.GetVehicleProperties()
QBCore.Functions.GetClosestVehicle()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.Game.SpawnVehicle()
ESX.Game.GetVehicleProperties()
ESX.Game.GetClosestVehicle()
```
--(Eğer ESX.Game olan neredeyse her şey QBCore.Functions olarak aynı şekildedir.)
--------------------------------------------------------------------------------------------------
Oyuncu Kendi Karakterin.
```lua
QBCore.Functions.GetPlayerData()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.GetPlayerData()
```
--------------------------------------------------------------------------------------------------
İtem Oluşturma.
```lua
QBCore.Functions.CreateUseableItem()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.RegisterUsableItem()
```
--------------------------------------------------------------------------------------------------
Banka Para Kaldırma.
```lua
Player.Functions.RemoveMoney()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
xPlayer.removeMoney(money)
```
--------------------------------------------------------------------------------------------------
Dosya'lar İle Alakalı.
```lua
QBCore.Functions.CreateCallback()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.RegisterServerCallback()
```
--------------------------------------------------------------------------------------------------
Dosya'lar İle Alakalı.
```lua
QBCore.Functions.TriggerCallback()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.TriggerServerCallback()
```
--------------------------------------------------------------------------------------------------
qb'de cid esx'de identifier kullanılıyor olayı çözmeniz için ufak bir kod bloğu bıraktım.
```lua
QBCore.Functions.CreateCallback('system:fetchStatus', function(source, cb)
    local Player = QBCore.Functions.GetPlayer(source)

     if Player then
           exports['ghmattimysql']:execute('SELECT skills FROM players WHERE citizenid = @citizenid', {
               ['@citizenid'] = Player.PlayerData.citizenid
          }, function(status)
              if status ~= nil then
                   cb(json.decode(status))
              else
                   cb(nil)
              end
          end)
     else
          cb()
     end
end)
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.RegisterServerCallback("system:fetchStatus", function(source, cb)
    local src = source
    local user = ESX.GetPlayerFromId(src)


    local fetch = [[
         SELECT
              skills
         FROM
              users
         WHERE
              identifier = @identifier
    ]]

    MySQL.Async.fetchScalar(fetch, {
         ["@identifier"] = user.identifier

    }, function(status)

         if status ~= nil then
              cb(json.decode(status))
         else
              cb(nil)
         end

    end)
end)
```
--------------------------------------------------------------------------------------------------
Sql bağlama kısmı
```lua
QBCore.Functions.ExecuteSql()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.ExecuteSql() --(ghmattimysql)
MySQL.Async.execute()
```
--------------------------------------------------------------------------------------------------
RegisterCommand - yani chat komut kısmı.
```lua
QBCore.Commands.Add()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
RegisterCommand 
```
-- (RegisterCommand qbcore'da da çalışır.)
--------------------------------------------------------------------------------------------------
Karakter Kısmı Dır Data Sına Bağlama.
```lua
local Player = QBCore.Functions.GetPlayer(source)
['@citizenid'] = Player.PlayerData.citizenid
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
local user : ESX.Get.PlayerFromId(src)
["@identifier"] = user.identifier
```
--------------------------------------------------------------------------------------------------

--Client Side

# ÜSTEKİ QBUSCORE
```lua
QBCore.Shared.Items
```
# ALTAKİ ESX
```lua
ESX.GetItems()
```

# ÜSTEKİ QBUSCORE
```lua
esx:onPlayerDeath 
```
# ALTAKİ ESX
```lua
hospital:server:SetDeathStatus
```

esx:playerLoaded -> QBCore:Client:OnPlayerLoaded

esx:showAdvancedNotification -> QBCore:Notify

esx:showHelpNotification -> QBCore:Notify

esx:showNotification -> QBCore:Notify

ESX.GetPlayerData -> QBCore.Functions.GetPlayerData

ESX.IsPlayerLoaded -> None

ESX.SetPlayerData -> QBCore:Player:SetPlayerData

ESX.TriggerServerCallback -> QBCore.Functions.TriggerCallback

ESX.Game.DeleteObject -> None (Can use FiveM native DeleteEntity)

ESX.Game.DeleteVehicle -> QBCore.Functions.DeleteVehicle

ESX.Game.GetClosestObject -> None (Can use FiveM native GetClosestObjectOfType)

ESX.Game.GetClosestPed -> QBCore.Functions.GetClosestPed

ESX.Game.GetClosestPlayer -> QBCore.Functions.GetClosestPlayer

ESX.Game.GetClosestVehicle -> QBCore.Functions.GetClosestVehicle

ESX.Game.GetObjects -> None (uses enumeration)

ESX.Game.GetPedMugshot -> None (Can use FiveM native RegisterPedheadshot)

ESX.Game.GetPeds -> None (uses enumeration)

ESX.Game.GetPlayers -> QBCore.Functions.GetPlayers

ESX.Game.GetPlayersInArea -> None (uses enumeration)

ESX.Game.GetVehicleInDirection -> None (uses ray casting)

ESX.Game.GetVehicles -> QBCore.Functions.GetVehicles

ESX.Game.GetVehiclesInArea -> None (uses enumeration)

ESX.Game.IsSpawnPointClear -> None (uses getvehiclesinarea)

ESX.Game.SetVehicleProperties -> QBCore.Functions.SetVehicleProperties

ESX.Game.SpawnLocalObject -> None (dont bother)

ESX.Game.SpawnLocalVehicle -> None (dont bother)

ESX.Game.SpawnObject -> None (Can use FiveM Native CreateObject)

ESX.Game.SpawnVehicle -> QBCore.Functions.SpawnVehicle

ESX.Game.Teleport -> (Can use FiveM Native SetEntityCoords and SetEntityHeading)

ESX.Game.Utils.DrawText3D -> QBCore.Functions.DrawText3D

--Server Side

ESX.CreatePickup -> None (irrelevant and done through qb-inventory)

ESX.GetItemLabel -> None (Just returns item label)

ESX.GetPlayerFromId -> QBCore.Functions.GetPlayer

ESX.GetPlayerFromIdentifier -> QBCore.Functions.GetPlayerByCitizenId

ESX.GetPlayers -> QBCore.Functions.GetPlayers

ESX.RegisterServerCallback -> QBCore.Functions.CreateCallback

ESX.RegisterUsableItem -> QBCore.Functions.CreateUseableItem

ESX.SavePlayer -> QBCore.Player.Save

ESX.SavePlayers -> None (dont bother)

ESX.Trace -> Use QBCore.Debug but dont bother converting this

ESX.UseItem -> QBCore.Functions.UseItem

--xPlayer

xPlayer.addAccountMoney -> xPlayer.Functions.AddMoney (account)

xPlayer.addInventoryItem -> xPlayer.Functions.AddItem (item name)

xPlayer.addMoney -> xPlayer.Functions.AddMoney (cash)

xPlayer.addWeapon -> xPlayer.Functions.AddItem (weapon name)

xPlayer.addWeaponAmmo -> xPlayer.Functions.AddItem (ammo name)

xPlayer.addWeaponComponent -> xPlayer.Functions.AddItem (component name)

xPlayer.canCarryItem -> None (xPlayer.Functions.AddItem already checks this)

xPlayer.canSwapItem -> None (xPlayer.Functions.AddItem already checks this)

xPlayer.getAccount -> None (use player data)

xPlayer.getAccounts -> None (use player data)

xPlayer.getCoords -> None (Can use FiveM Native GetEntityCoords)

xPlayer.getGroup -> xPlayer.Functions.GetPermission

xPlayer.getIdentifier -> xPlayer.Functions.GetIdentifier

xPlayer.getInventory -> QBCore.Player.LoadInventory

xPlayer.getInventoryItem -> xPlayer.Functions.GetItemByName

xPlayer.getJob -> None (use player data)

xPlayer.getLoadout -> None (fuck loadouts)

xPlayer.getMoney -> None (use player data)

xPlayer.getName -> None (use player data)

xPlayer.getWeapon -> xPlayer.Functions.GetItemByName (weapon name)

xPlayer.getWeight -> xPlayer.Player.GetTotalWeight

xPlayer.hasWeapon -> xPlayer.Functions.GetItemByName (weapon name)

xPlayer.hasWeaponComponent -> xPlayer.Functions.GetItemByName (component name)

xPlayer.kick -> xPlayer.Functions.Kick

xPlayer.removeAccountMoney -> xPlayer.Functions.RemoveMoney (account)

xPlayer.removeInventoryItem -> xPlayer.Functions.RemoveItem (item name)

xPlayer.removeMoney -> xPlayer.Functions.RemoveMoney (cash)

xPlayer.removeWeapon -> xPlayer.Functions.RemoveItem (weapon name)

xPlayer.removeWeaponAmmo -> xPlayer.Functions.RemoveItem (ammo name)

--xPlayer #2

xPlayer.removeWeaponComponent -> xPlayer.Functions.RemoveItem (component name)

xPlayer.setAccountMoney -> xPlayer.Functions.SetMoney (account)

xPlayer.setCoords -> None (used for teleporting)

xPlayer.setInventoryItem -> xPlayer.Functions.AddItem (item name)

xPlayer.setJob -> xPlayer.Functions.SetJob

xPlayer.setMaxWeight -> None (It is set in qb-core config)

xPlayer.setMoney -> xPlayer.Functions.SetMoney

xPlayer.setName -> None (dont bother)

xPlayer.setWeaponTint -> None (qb-weapons does this)

xPlayer.showHelpNotification -> TriggerClientEvent('QBCore:Notify')

xPlayer.showNotification -> TriggerClientEvent('QBCore:Notify')

xPlayer.triggerEvent -> None (dont bother)

xPlayer.updateCoords -> None (dont bother)

--Events

esx:getSharedObject -> QBCore:GetObject

esx:setJob -> QBCore:Client:OnJobUpdate

esx:onPlayerSpawn -> QBCore:Client:OnPlayerLoaded

playerSpawned -> QBCore:Client:OnPlayerLoaded (spawnmanager compatibility)

esx:addInventoryItem -> QBCore:Server:AddItem

esx:removeInventoryItem -> QBCore:Server:RemoveItem

esx:useItem -> QBCore:Server:UseItem

MySQL.Async.fetchScalar() -> exports['ghmattimysql']:scalar() or QBCore.Functions.ExecuteSql(true,

MySQL.Async.fetchAll() -> exports['ghmattimysql']:execute() or QBCore.Functions.ExecuteSql(true,

MySQL.Async.execute() -> exports['ghmattimysql']:execute() or QBCore.Functions.ExecuteSql(false,

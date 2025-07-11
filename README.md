local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

local roupas = {
    "Green Ghillie Suit Hood",
    "Grass Ghillie Suit Top",
    "Grass Ghillie Suit Pants"
}

for _, nomeRoupa in ipairs(roupas) do
    local roupa = workspace:FindFirstChild(nomeRoupa)
    if roupa and roupa:FindFirstChild("PrimaryPart") then
        -- Teleportar para a roupa
        character:SetPrimaryPartCFrame(roupa.PrimaryPart.CFrame)
        wait(1)

        -- Simular toque/interação (se o jogo permitir)
        firetouchinterest(character.PrimaryPart, roupa.PrimaryPart, 0)
        wait(0.3)
        firetouchinterest(character.PrimaryPart, roupa.PrimaryPart, 1)
        
        wait(2)
    end
end

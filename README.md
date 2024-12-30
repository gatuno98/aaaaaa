game.Players.PlayerAdded:Connect(function(player)
    -- Espera o personagem do jogador ser carregado
    player.CharacterAdded:Connect(function(character)
        -- Verifica se o jogador tem uma tag de nome
        local humanoid = character:WaitForChild("Humanoid")
        
        -- Espera a parte do nome do jogador (Head) aparecer
        local head = character:WaitForChild("Head")
        
        -- Cria um BillboardGui para exibir o nome sobre a cabeça
        local billboardGui = Instance.new("BillboardGui")
        billboardGui.Parent = head
        billboardGui.Adornee = head
        billboardGui.Size = UDim2.new(0, 200, 0, 50)
        
        -- Cria um TextLabel para exibir o nome
        local textLabel = Instance.new("TextLabel")
        textLabel.Parent = billboardGui
        textLabel.Size = UDim2.new(1, 0, 1, 0)
        textLabel.Text = player.Name
        textLabel.TextColor3 = Color3.fromRGB(255, 255, 255)  -- Cor branca
        textLabel.TextScaled = true
        textLabel.BackgroundTransparency = 1  -- Sem fundo
    end)
end)

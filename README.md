jogador local = jogo.Jogadores.JogadorLocal
caractere local = player.Character ou player.CharacterAdded:Wait()
humanoide local = personagem:WaitForChild("Humanoide")

-- Função para itens de riqueza
função local collectItem(item)
    se item:IsA("Parte") e item.Nome == "Pote" então
        item:Destroy() -- Remove o item do jogo
        print("Item coletado: " .. item.Nome)
    fim
fim

-- Conectar a função de coleta ao evento Touched
para _, item em pares(workspace:GetChildren()) faça
    se item:IsA("Parte") e item.Nome == "Pote" então
        item.Tocado:Conectar(função(acerto)
            se hit.Parent == personagem então
                coletarItem(item)
            fim
        fim)
    fim
fim

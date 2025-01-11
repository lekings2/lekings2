- 👋 Hi, I’m @leking.s2
- 👉🏾 standoff2 hack
- 👇🏾DC
- 👉🏾https://discord.gg/AHzXT5vH
- 
<!----- Variáveis
local ativado = false
local corAmiga = {r = 255, g = 0, b = 0} -- Vermelho
local corInimiga = {r = 128, g = 0, b = 128} -- Roxa

-- Função para desenhar ESP
local function desenharESP(jogador, cor)
    gui.drawRect(jogador.x, jogador.y, 10, 10, cor.r, cor.g, cor.b) -- FOV
    gui.drawLine(jogador.x, jogador.y, jogador.x + 10, jogador.y, cor.r, cor.g, cor.b) -- Seta
end

-- Função para verificar equipe
local function getEquipe(jogador)
    if jogador.team == getLocalPlayer():getTeam() then
        return corAmiga
    else
        return corInimiga
    end
end

-- Função para ativar/desativar script
local function toggleScript()
    ativado = not ativado
end

-- Loop principal
while true do
    if ativado then
        local players = getPlayers()
        if players then
            for _, jogador in pairs(players) do
                local cor = getEquipe(jogador)
                desenharESP(jogador, cor)
            end
        end
    end
    wait(0.016) -- 60 FPS (not 90 FPS, corrected for common frame rate)
end

-- Atalho para ativar/desativar script
-- Use um botão no aplicativo de modding para executar "toggleScript()"
lekings2/lekings2 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

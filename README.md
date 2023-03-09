-- Initialisiere das Fenster und die Schriftart
local screenWidth, screenHeight = love.graphics.getDimensions()
love.window.setTitle("Fly Script")
love.graphics.setBackgroundColor(255, 255, 255)
local font = love.graphics.newFont(20)
 
-- Setze die Anfangsposition des Textes
local x = screenWidth / 2
local y = screenHeight / 2
 
-- Definiere die Bewegungsgeschwindigkeit des Textes
local speed = 100
 
-- Definiere die Flugrichtung des Textes
local angle = 0
 
-- Definiere die Aktualisierungsfunktion
function love.update(dt)
    -- Berechne die neue Position des Textes basierend auf der Geschwindigkeit und dem Winkel
    x = x + math.cos(angle) * speed * dt
    y = y + math.sin(angle) * speed * dt
 
    -- Wenn der Text den Bildschirmrand erreicht, ändere die Flugrichtung
    if x < 0 or x > screenWidth or y < 0 or y > screenHeight then
        angle = angle + math.pi / 2
    end
end
 
-- Definiere die Zeichenfunktion
function love.draw()
    love.graphics.setFont(font)
    love.graphics.print("Fly!", x, y)
end

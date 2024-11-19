local Players = game:GetService("Players")
local MarketPlaceService = game:GetService("MarketplaceService")
local GamepassID = 962361438
local ToolName = "Bicycle"

Players.PlayerAdded:Connect(function(player)
	player.CharacterAdded:Connect(function(character)
		if MarketPlaceService:UserOwnsGamePassAsync(player.UserId, GamepassID) then
			script[ToolName]:Clone().Parent = player.Backpack
		end
	end)
end)

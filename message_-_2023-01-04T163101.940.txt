function replicatedDoor(room)
	for _,strip in pairs(room:GetDescendants()) do
		if strip:IsA("BasePart") and strip.Material ~= Enum.Material.Neon and not strip.Parent:FindFirstChild("ModulePrompt") then
			strip.BrickColor = BrickColor.new("Black")
		end
	end
end
for _, v in pairs(workspace.CurrentRooms:GetChildren()) do
        replicatedDoor(v)
    end
workspace.CurrentRooms.ChildAdded:Connect(function()
	for _, v in pairs(workspace.CurrentRooms:GetChildren()) do
        replicatedDoor(v)
    end
end)

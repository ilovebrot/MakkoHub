function ShowMenu(MakkoHub)
    local options = {"Option 1", "Option 2", "Option 3"}
    for i, option in ipairs(options) do
        print(i .. ". " .. option)
    end
    
    local choice = io.read()
    
    if choice == "1" then
        print("Option 1 selected")
    elseif choice == "2" then
        print("Option 2 selected")
    elseif choice == "3" then
        print("Option 3 selected")
    else
        print("Invalid choice")
    end
end

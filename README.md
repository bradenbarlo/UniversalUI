# UniversalUI
A better version of my previously made UniversalUI which works in pretty much any game that you play. I made this keyless because I just hate when I want a hack script but I need to sit through a bunch of shitty ads, and its also open sourced so feel free to make your own versions!


## Custom Module Examples
If you want to add custom modules, here is a nice little example:

> (Add this somewhere after the **local specialModules = {}**)

specialModules.Example = function(UI)

  local exampleTab = UI:AddTab("Example Module")
  
  local exampleButton = exampleTab:AddButton("Example Button", function()
  
    print("Example Button Clicked")
	
  end)
  
end

> and then at the end of the script, add something like this:

local exampleMod = tab4:AddButton("Example Module", function()

	local moduleName = "Example Module"
	
	if not table.find(loadedModules, moduleName) then
	
		specialModules.Example(UI)	
		
		table.insert(loadedModules, moduleName)
		
	end
	
end)

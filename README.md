
function ESX.GetImg(name, item)
	local url = ("VOTRELIENIMAGEDISCORD"):format(name)
	if (item) == true and Config.img[name] == nil then
		url = ("VOTRELIENIMAGEDISCORD"):format("box")
	end

	return url
end


function ESX.ShowNotification(msg, time)
	-- if exports.Inventory:isInInventory() then
	-- 	TriggerEvent("inventory:sendMessage", msg, icon)
	-- else
	TriggerEvent('SHOW_NOTIF', msg, "rgb(0, 255, 0)", ESX.GetImg("VOTRELIENIMAGEDISCORD"), "Informations", "Informations", withaccept, announcement)
	end
	-- end
	function ESX.ShowAdvancedNotification(text, color, icon, jobname, phone, withaccept, announcement)
		-- if exports.Inventory:isInInventory() then
		-- 	TriggerEvent("inventory:sendMessage", text)
		-- else
			local color = color
			local icon = icon
			local jobname = jobname
	
			if color == "" then
				color = "rgb(0, 255, 0)"
			end
	
			if icon == "" then
				icon = ESX.GetImg("VOTRELIENIMAGEDISCORD")
			end
	
			if jobname == "" then
				jobname = "Informations"
			end
			TriggerEvent('SHOW_NOTIF', text, color, icon, jobname, phone, withaccept, announcement)
		-- end
	end
	

function ESX.ShowHelpNotification(msg)
	AddTextEntry('esxHelpNotification', msg)
	BeginTextCommandDisplayHelp('esxHelpNotification')
	EndTextCommandDisplayHelp(0, false, true, -1)
end

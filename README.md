function ESX.GetImg(name, item)
	local url = ("https://media.discordapp.net/attachments/1216106744007364663/1216494003768262706/pauseLogo.png?ex=66009753&is=65ee2253&hm=590ea8a207569e268ad85a44c23f3c60b7d08a718ab955b0243fa4f171de749d&=&format=webp&quality=lossless&width=181&height=95"):format(name)

	if (item) == true and Config.img[name] == nil then
		url = ("https://media.discordapp.net/attachments/1216106744007364663/1216494003768262706/pauseLogo.png?ex=66009753&is=65ee2253&hm=590ea8a207569e268ad85a44c23f3c60b7d08a718ab955b0243fa4f171de749d&=&format=webp&quality=lossless&width=181&height=95"):format("box")
	end

	return url
end


function ESX.ShowNotification(msg, time)
	-- if exports.Inventory:isInInventory() then
	-- 	TriggerEvent("inventory:sendMessage", msg, icon)
	-- else
	TriggerEvent('SHOW_NOTIF', msg, "rgb(0, 255, 0)", ESX.GetImg("https://media.discordapp.net/attachments/1216106744007364663/1216494003768262706/pauseLogo.png?ex=66009753&is=65ee2253&hm=590ea8a207569e268ad85a44c23f3c60b7d08a718ab955b0243fa4f171de749d&=&format=webp&quality=lossless&width=181&height=95"), "Informations", "Informations", withaccept, announcement)
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
				icon = ESX.GetImg("https://media.discordapp.net/attachments/1216106744007364663/1216494003768262706/pauseLogo.png?ex=66009753&is=65ee2253&hm=590ea8a207569e268ad85a44c23f3c60b7d08a718ab955b0243fa4f171de749d&=&format=webp&quality=lossless&width=181&height=95")
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

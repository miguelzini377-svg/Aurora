local createFontPreset
if not game:IsLoaded() then
	game.Loaded:Wait()
end
local protectedCall = pcall
local cloneReference, environment, protectGui, getHiddenUi, services, userInputService, runService
local httpService, stats, localPlayer, white, black2, theme, keyCodes, fontPresets, fontBindings, currentFont
local applyFont, refreshFontStyles, profiler, uiState, saveUiState, trackConnection, capturingKey, createInstance, bindTheme, addCorner
local createRow, getGradientColors, registerGradient, applyFonts, addGradientStroke, applyTextGradient, captureKeybind, createKeybindButton, createLogo
do
	do
		do
			do
				if getgenv and getgenv().AuroraHub and getgenv().AuroraHub.Destroy then
					local handleAction = function()
						getgenv().AuroraHub.Destroy()
					end
					handleAction()
				end
				cloneReference = cloneref or function(argument)
					return argument
				end
				environment = getgenv and getgenv() or {}
				if environment.Aurora and environment.Aurora.Destroy then
					local handleAction2 = function()
						environment.Aurora:Destroy()
					end
					handleAction2()
				end
				protectGui = syn and syn.protect_gui or protect_gui
				getHiddenUi = gethui
				do
					local items2 = {}
					for index2 = 1, 64 do
						items2[string.byte("ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/", index2)] = index2
							- 1
					end
				end
			end
			services = setmetatable({}, {
				__index = function(world, argument2)
					local getGetService = function()
						return cloneReference(game:GetService(argument2))
					end
					local value2 = getGetService()
					rawset(world, argument2, value2)
					return value2
				end,
			})
			userInputService = services.UserInputService
			runService = services.RunService
			httpService = services.HttpService
			stats = services.Stats
			localPlayer = services.Players.LocalPlayer
			tick()
			white = Color3.new(1, 1, 1)
			black2 = Color3.new(0, 0, 0)
			theme = {
				Name = "Aurora",
				Version = "v1.5.9",
				Base = Color3.fromRGB(24, 25, 29),
				Raised = Color3.fromRGB(30, 31, 36),
				Inset = Color3.fromRGB(37, 38, 44),
				Stroke = Color3.fromRGB(46, 48, 54),
				Hover = Color3.fromRGB(52, 55, 63),
				Sel = Color3.fromRGB(50, 53, 60),
				Accent = Color3.fromRGB(255, 112, 24),
				Accent2 = Color3.fromRGB(149, 86, 242),
				Text = Color3.fromRGB(236, 237, 242),
				SubText = Color3.fromRGB(161, 164, 175),
				Corner = 8,
				Pad = 10,
				Font = Enum.Font.Gotham,
				FontMed = Enum.Font.GothamMedium,
				FontBold = Enum.Font.GothamBold,
				FontBlack = Enum.Font.GothamBlack,
				FontFamily = "Gotham",
				LogoAssetId = "118580479624832",
				RagdollAssetId = "90219076786818",
				LogoStyle = "ring",
			}
			do
				local items3 = {}
				for _, item in ipairs(Enum.Font:GetEnumItems()) do
					items3[item.Name] = item
				end
				local handleAction3 = function(argument3)
					return items3[argument3]
				end
				keyCodes = {}
				for _, item2 in ipairs(Enum.KeyCode:GetEnumItems()) do
					keyCodes[item2.Name] = item2
				end
				createFontPreset = function(argument4, argument5, argument6, argument7, argument8)
					local value3 = handleAction3(argument5) or Enum.Font.Gotham
					local value4 = handleAction3(argument6) or value3
					local value5 = handleAction3(argument7) or value4
					return {
						Name = argument4,
						reg = value3,
						med = value4,
						bold = value5,
						black = handleAction3(argument8) or value5,
					}
				end
			end
		end
		fontPresets = {}
		do
			local value6 = createFontPreset("Gotham", "Gotham", "GothamMedium", "GothamBold", "GothamBlack")
			local value7 =
				createFontPreset("Source Sans", "SourceSans", "SourceSansSemibold", "SourceSansBold", "SourceSansBlack")
			local value8 = createFontPreset("Arial", "Arial", "Arial", "ArialBold", "ArialBold")
			local value9 = createFontPreset("Roboto", "Roboto", "Roboto", "Roboto", "Roboto")
			local value10 = createFontPreset("Roboto Mono", "RobotoMono", "RobotoMono", "RobotoMono", "RobotoMono")
			local value11 = createFontPreset("Ubuntu", "Ubuntu", "Ubuntu", "Ubuntu", "Ubuntu")
			local value12 = createFontPreset("Nunito", "Nunito", "Nunito", "Nunito", "Nunito")
			local value13 =
				createFontPreset("Merriweather", "Merriweather", "Merriweather", "Merriweather", "Merriweather")
			local value14 = createFontPreset("Oswald", "Oswald", "Oswald", "Oswald", "Oswald")
			local value15 = createFontPreset("Code", "Code", "Code", "Code", "Code")
			local value16 = createFontPreset("Highway", "Highway", "Highway", "Highway", "Highway")
			local value17 = createFontPreset("Garamond", "Garamond", "Garamond", "Garamond", "Garamond")
			local value18 = createFontPreset("Fantasy", "Fantasy", "Fantasy", "Fantasy", "Fantasy")
			local value19 = createFontPreset("Antique", "Antique", "Antique", "Antique", "Antique")
			fontPresets[1] = value6
			fontPresets[2] = value7
			fontPresets[3] = value8
			fontPresets[4] = value9
			fontPresets[5] = value10
			fontPresets[6] = value11
			fontPresets[7] = value12
			fontPresets[8] = value13
			fontPresets[9] = value14
			fontPresets[10] = value15
			fontPresets[11] = value16
			fontPresets[12] = value17
			fontPresets[13] = value18
			fontPresets[14] = value19
		end
	end
	do
		do
			fontBindings = setmetatable({}, { __mode = "k" })
			currentFont = fontPresets[1]
			do
				local items4 = {}
				applyFont = function(argument9, argument10)
					local text2 = "EnumItem"
					if typeof(argument10) == text2 then
						local handleAction4 = function()
							argument9.Font = argument10
						end
						handleAction4()
					elseif argument10 ~= nil then
						local handleAction5 = function()
							argument9.FontFace = argument10
						end
						handleAction5()
					end
				end
				refreshFontStyles = function()
					items4 = {}
					local handleAction6 = function(argument11, argument12)
						local text3 = "EnumItem"
						if typeof(argument11) == text3 and items4[argument11] == nil then
							items4[argument11] = argument12
						end
					end
					handleAction6(theme.Font, "reg")
					handleAction6(theme.FontMed, "med")
					handleAction6(theme.FontBold, "bold")
					handleAction6(theme.FontBlack, "black")
				end
				refreshFontStyles()
				local handleAction10 = function()
					local items5 = {}
					local items6 = {}
					local handleAction7 = function(p)
						return p
					end
					local controller = {
						Enabled = true,
						Capacity = 64,
						Limit = 256,
						Generation = 0,
						Register = function(argument13, argument14, argument15)
							assert(type(argument14) == "string" and #argument14 > 0, "Profile label is required")
							local value20 = argument15 == "sync" and "sync" or "elapsed"
							local value21 = items5[argument14]
							if value21 then
								if value21.Kind ~= value20 then
									value21.Kind = "mixed"
								end
								return value21
							end
							if argument13.Limit <= #items6 then
								return nil
							end
							local options = {
								Name = argument14,
								Kind = value20,
								Values = {},
								Head = 0,
								Sum = 0,
								Samples = 0,
								Calls = 0,
								Errors = 0,
								LastSeen = nil,
							}
							items5[argument14] = options
							items6[#items6 + 1] = options
							return options
						end,
						Measure = function(self, label, duration, kind)
							if not self.Enabled then
								return
							end
							local metric = self:Register(label, kind)
							if not metric then
								return
							end
							local milliseconds = math.max(0, tonumber(duration) or 0) * 1000
							metric.Calls += 1
							metric.LastSeen = os.clock()
							metric.Head = metric.Head % self.Capacity + 1
							local previous = metric.Values[metric.Head]
							metric.Sum = metric.Sum - (previous or 0) + milliseconds
							metric.Values[metric.Head] = milliseconds
							metric.Samples = math.min(metric.Samples + 1, self.Capacity)
							return metric
						end,
					}

					controller.Wrap = function(argument16, argument17, argument18, argument19)
						assert(type(argument18) == "function", "Profile callback must be a function")
						assert(argument16:Register(argument17, argument19), "Profile registration failed")
						return function(...)
							if not argument16.Enabled then
								return argument18(...)
							end
							local started = os.clock()
							local results = table.pack(pcall(argument18, ...))
							local metric = argument16:Measure(argument17, os.clock() - started, argument19)
							if not results[1] then
								if metric then
									metric.Errors += 1
								end
								error(results[2], 0)
							end
							return table.unpack(results, 2, results.n)
						end
					end
					controller.SetEnabled = function(argument20, argument21)
						local value22 = argument21 == true
						if argument20.Enabled ~= value22 then
							argument20.Generation = argument20.Generation + 1
						end
						argument20.Enabled = value22
					end
					controller.Reset = function(argument22)
						argument22.Generation = argument22.Generation + 1
						for _, item3 in ipairs(items6) do
							item3.Values = {}
							item3.Head = 0
							item3.Sum = 0
							local numberValue = 0
							local numberValue2 = 0
							item3.Samples = 0
							item3.Calls = numberValue
							item3.Errors = numberValue2
							item3.LastSeen = nil
						end
					end
					local handleAction9 = function(argument23, argument24, argument25)
						local value23 = argument23.LastSeen and math.max(0, argument24 - argument23.LastSeen) or nil
						local options2 = {
							Name = argument23.Name,
							Kind = argument23.Kind,
							Samples = argument23.Samples,
							Calls = argument23.Calls,
							Errors = argument23.Errors,
							LastSeen = argument23.LastSeen,
							Age = value23,
							Recording = controller.Enabled,
						}
						local value24 = argument23.Calls == 0 and "unmeasured"
						if not value24 then
							value24 = not controller.Enabled and "paused"
							if not value24 then
								value24 = value23 > 5 and "idle" or "active"
							end
						end
						options2.Status = value24
						if argument23.Samples > 0 then
							options2.MeanMs = math.max(0, argument23.Sum / argument23.Samples)
							options2.LastMs = argument23.Values[argument23.Head]
							if argument25 == nil or argument25 == "P95Ms" then
								local value25 = table.clone(argument23.Values)
								table.sort(value25)
								options2.P95Ms = value25[math.max(1, math.ceil(argument23.Samples * 0.95))]
								options2.MaxMs = value25[argument23.Samples]
							elseif argument25 == "MaxMs" then
								local value26, value27, value28 = ipairs(argument23.Values)
								local numberValue3 = 0
								for _, item4 in value26, value27, value28 do
									numberValue3 = math.max(numberValue3, item4)
								end
								options2.MaxMs = numberValue3
							end
						end
						return options2
					end
					controller.Snapshot = function(argument26, argument27)
						local startedAt = os.clock()
						local value29 = table.create(#items6)
						for key2, item5 in ipairs(items6) do
							value29[key2] = handleAction9(item5, startedAt, argument27)
						end
						return value29
					end
					controller.Detail = function(argument28, argument29)
						local value30 = items5[argument29]
						return value30 and handleAction9(value30, os.clock()) or nil
					end
					return controller
				end
				profiler = handleAction10()
				profiler.Build = {}
				uiState = {
					alive = true,
					connections = {},
					cleanups = {},
					themeBindings = {},
					dropdowns = {},
					controls = {},
					sliders = {},
					keyBindings = {},
					windowPositions = {},
					windowControls = {},
					savedWindows = {},
				}
				saveUiState = nil
				trackConnection = function(argument30)
					uiState.connections[#uiState.connections + 1] = argument30
					return argument30
				end
				capturingKey = false
				trackConnection(services.UserInputService.InputBegan:Connect(function(input, argument31)
					if argument31 or capturingKey or input.UserInputType ~= Enum.UserInputType.Keyboard then
						return
					end
					for index3 = 1, #uiState.keyBindings do
						local value31 = uiState.keyBindings[index3]
						if value31.key == input.KeyCode then
							value31.fn()
						end
					end
				end))
				createInstance = function(argument32, instance, argument33)
					local value32 = Instance.new(argument32)
					if instance then
						for key3, item6 in next, instance, nil do
							if key3 ~= "Parent" then
								value32[key3] = item6
							end
						end
						if instance.Font ~= nil then
							local value33 = items4[instance.Font]
							if value33 then
								fontBindings[value32] = value33
								local value34 = currentFont[value33]
								if value34 ~= instance.Font then
									applyFont(value32, value34)
								end
							end
						end
					end
					if argument33 then
						for index4 = 1, #argument33 do
							argument33[index4].Parent = value32
						end
					end
					if instance and instance.Parent then
						value32.Parent = instance.Parent
						local value35 = fontBindings[value32]
						if value35 then
							value35 = (uiState.internalValue171 or 0) > 0.35
						end
						if value35 then
							uiState.fontBindings(value32)
						end
					end
					if
						argument32 == "TextButton"
						and instance
						and instance.BackgroundTransparency ~= 1
						and instance.Text
						and instance.Text ~= ""
						and uiState.bindButtonFeedback
					then
						uiState.bindButtonFeedback(value32)
					end
					return value32
				end
			end
		end
		do
			local value36 = setmetatable({}, { __mode = "k" })
			local value37 = setmetatable({}, { __mode = "k" })
			local value38 = setmetatable({}, { __mode = "k" })
			uiState.fontStyles = value36
			uiState.themeProperties = {
				Base = true,
				Raised = true,
				Inset = true,
				Hover = true,
				Sel = true,
			}
			uiState.fontPresets = function(argument34)
				local value39 = uiState.internalValue171 or 0
				return value39 + argument34 * (1 - value39)
			end
			uiState.internalValue176 = function(argument35)
				if value36[argument35] or value37[argument35] then
					return
				end
				local data2 = { normal = argument35.BackgroundTransparency }
				value36[argument35] = data2
				local handleAction11 = function()
					data2.writing = true
					data2.applied = uiState.fontPresets(data2.normal)
					argument35.BackgroundTransparency = data2.applied
					data2.writing = false
				end
				data2.apply = handleAction11
				data2.conn =
					trackConnection(argument35:GetPropertyChangedSignal("BackgroundTransparency"):Connect(function()
						if data2.writing or math.abs(argument35.BackgroundTransparency - data2.applied) < 1e-06 then
							return
						end
						data2.normal = argument35.BackgroundTransparency
						handleAction11()
					end))
				handleAction11()
			end
			uiState.internalValue177 = function(argument36)
				value37[argument36] = true
				local value40 = value36[argument36]
				if not value40 then
					return argument36
				end
				value36[argument36] = nil
				value40.conn:Disconnect()
				argument36.BackgroundTransparency = value40.normal
				return argument36
			end
			uiState.internalValue178 = function(argument37)
				if argument37 <= 0.35 then
					return 1
				end
				return 1 - 0.65 * math.clamp((argument37 - 0.35) / 0.5, 0, 1)
			end
			uiState.fontBindings = function(argument38)
				local value41 = uiState.screenGui
				if not value41 or not argument38:IsDescendantOf(value41) then
					return
				end
				if uiState.internalValue180 and argument38:IsDescendantOf(uiState.internalValue180) then
					return
				end
				local value42 = uiState.internalValue178(uiState.internalValue171 or 0)
				if not value38[argument38] then
					if value42 >= 1 or argument38.TextStrokeTransparency < 1 then
						return
					end
					value38[argument38] = true
					argument38.TextStrokeColor3 = Color3.new(0, 0, 0)
				end
				argument38.TextStrokeTransparency = value42
			end
			uiState.internalValue181 = function(argument39)
				uiState.internalValue171 = math.clamp(tonumber(argument39) or 0, 0, 100) / 100
				for key4, item7 in pairs(value36) do
					if key4.Parent then
						item7.apply()
					end
				end
				for key5 in pairs(fontBindings) do
					if key5.Parent then
						uiState.fontBindings(key5)
					end
				end
			end
		end
	end
	do
		bindTheme = function(argument40, argument41, argument42)
			uiState.themeBindings[#uiState.themeBindings + 1] = { argument40, argument41, argument42 }
			argument40[argument41] = theme[argument42]
			if argument41 == "BackgroundColor3" then
				argument40:SetAttribute("AuroraButtonTone", argument42)
			end
			if
				argument41 == "BackgroundColor3"
				and uiState.themeProperties[argument42]
				and argument40:IsA("GuiObject")
			then
				uiState.internalValue176(argument40)
			end
			return argument40
		end
		addCorner = function(argument43, argument44)
			local value43 = argument43:IsA("GuiButton")
				and argument43.Size.X.Scale == 0
				and argument43.Size.Y.Scale == 0
				and argument43.Size.X.Offset <= 44
				and argument43.Size.Y.Offset <= 44
			argument44 = argument44 or theme.Corner
			local value44
			if argument44 >= 4 then
				value44 = math.max(argument44, 10)
			else
				value44 = argument44
			end
			return createInstance(
				"UICorner",
				{ CornerRadius = value43 and UDim.new(0.5, 0) or UDim.new(0, value44), Parent = argument43 }
			)
		end
		createRow = function(argument45, argument46)
			return createInstance("Frame", {
				Size = UDim2.new(1, 0, 0, argument46),
				BackgroundTransparency = 1,
				BorderSizePixel = 0,
				ZIndex = 2,
				Parent = argument45,
			})
		end
		do
			local value45 = nil
			local value46 = nil
			local value47 = nil
			local value48 = nil
			getGradientColors = function(argument47)
				local accent3 = theme.Accent
				local accent22 = theme.Accent2
				if accent3 ~= value45 or accent22 ~= value46 then
					value45 = accent3
					value46 = accent22
					value47 = nil
					value48 = nil
				end
				if argument47 == "shimmer" then
					if not value48 then
						local new2 = ColorSequence.new
						local items7 = {}
						local value49 = ColorSequenceKeypoint.new(0, accent3)
						local value50 = ColorSequenceKeypoint.new(0.5, accent22)
						local new3 = ColorSequenceKeypoint.new
						items7[1] = value49
						items7[2] = value50
						do
							local values = table.pack(new3(1, accent3))
							table.move(values, 1, values.n, 3, items7)
						end
						value48 = new2(items7)
					end
					return value48
				end
				if not value47 then
					value47 = ColorSequence.new(accent3, accent22)
				end
				return value47
			end
		end
	end
	do
		registerGradient = function(argument48, argument49)
			uiState.sliders[#uiState.sliders + 1] = { argument48, argument49 }
			return argument48
		end
		do
			local value51 = setmetatable({}, { __mode = "k" })
			applyFonts = {}
			trackConnection(runService.Heartbeat:Connect(profiler:Wrap("Gradient animation", function()
				local phase = os.clock() * 25
				for gradient, entry in pairs(value51) do
					if gradient.Parent and entry.host and entry.host.Parent then
						gradient.Rotation = entry.rotation or 0
						if entry.text then
							gradient.Offset = Vector2.new(math.sin(os.clock() * 0.6) * 0.3, 0)
						end
					end
				end
			end, "sync")))
			addGradientStroke = function(argument50, argument51, argument52)
				local uIStroke = createInstance("UIStroke", {
					Thickness = argument51 or 1,
					Color = Color3.new(1, 1, 1),
					ApplyStrokeMode = Enum.ApplyStrokeMode.Border,
					Parent = argument50,
				})
				local value52 = argument52 or 0
				value51[registerGradient(
					createInstance(
						"UIGradient",
						{ Rotation = value52, Color = getGradientColors("edge"), Parent = uIStroke }
					),
					"edge"
				)] =
					{ host = argument50, rotation = value52 }
				return uIStroke
			end
			applyTextGradient = function(argument53)
				argument53.TextColor3 = Color3.new(1, 1, 1)
				value51[argument53:FindFirstChildOfClass("UIGradient") or registerGradient(
					createInstance(
						"UIGradient",
						{ Name = "AuroraTextGradient", Color = getGradientColors("shimmer"), Parent = argument53 }
					),
					"shimmer"
				)] =
					{ host = argument53, text = true }
			end
		end
	end
	captureKeybind = function(argument54)
		capturingKey = true
		local connection2 = nil
		local enabled2 = false
		local handleAction12 = function(argument55, argument56)
			if enabled2 then
				return
			end
			enabled2 = true
			if connection2 then
				connection2:Disconnect()
				connection2 = nil
			end
			argument54(argument55, argument56)
			task.defer(function()
				capturingKey = false
			end)
		end
		connection2 = services.UserInputService.InputBegan:Connect(function(input2)
			if input2.UserInputType ~= Enum.UserInputType.Keyboard then
				return
			end
			if input2.KeyCode == Enum.KeyCode.Escape or input2.KeyCode == Enum.KeyCode.Backspace then
				handleAction12(nil, false)
			else
				handleAction12(input2.KeyCode, false)
			end
		end)
		task.delay(10, function()
			handleAction12(nil, true)
		end)
		return function()
			handleAction12(nil, true)
		end
	end
	createKeybindButton = function(argument57, argument58, argument59, argument60)
		uiState.internalValue182 = uiState.internalValue182 or {}
		local value53 = nil
		if argument60 then
			uiState.internalValue182[argument60] = (uiState.internalValue182[argument60] or 0) + 1
			value53 = argument60 .. "#" .. uiState.internalValue182[argument60]
		end
		local binding2 = { key = nil, fn = argument58, name = value53 }
		uiState.keyBindings[#uiState.keyBindings + 1] = binding2
		local textButton = createInstance("TextButton", {
			AnchorPoint = Vector2.new(1, 0.5),
			Position = UDim2.new(1, argument59 or -48, 0.5, 0),
			Size = UDim2.new(0, 22, 0, 18),
			Font = theme.FontBold,
			Text = "",
			TextColor3 = theme.SubText,
			TextSize = 10,
			BorderSizePixel = 0,
			Parent = argument57,
		})
		uiState.internalValue177(textButton)
		bindTheme(textButton, "BackgroundColor3", "Inset")
		bindTheme(textButton, "TextColor3", "Accent")
		addCorner(textButton, 4)
		addGradientStroke(textButton, 1)
		if value53 and uiState.windowPositions[value53] then
			binding2.key = uiState.windowPositions[value53]
			textButton.Text = binding2.key.Name:sub(1, 4)
		end
		local enabled3 = false
		local value54 = nil
		trackConnection(textButton.MouseButton1Click:Connect(function()
			if enabled3 then
				value54()
				return
			end
			enabled3 = true
			textButton.Text = "..."
			value54 = captureKeybind(function(argument61, argument62)
				enabled3 = false
				value54 = nil
				if argument62 then
					textButton.Text = binding2.key and binding2.key.Name:sub(1, 4) or ""
				elseif argument61 == nil then
					binding2.key = nil
					textButton.Text = ""
					if value53 then
						uiState.windowPositions[value53] = nil
					end
					if saveUiState then
						saveUiState()
					end
				else
					binding2.key = argument61
					textButton.Text = argument61.Name:sub(1, 4)
					if value53 then
						uiState.windowPositions[value53] = argument61
					end
					if saveUiState then
						saveUiState()
					end
				end
			end)
		end))
		return textButton
	end
	do
		local handleAction13 = function(argument63, argument64)
			argument63.BackgroundColor3 = Color3.new(1, 1, 1)
			registerGradient(
				createInstance(
					"UIGradient",
					{ Rotation = argument64 or 90, Color = getGradientColors("edge"), Parent = argument63 }
				),
				"edge"
			)
			return argument63
		end
		local handleAction14 = function(argument65, argument66, argument67, argument68, argument69, argument70)
			local value55 = argument68 - argument66
			local value56 = argument69 - argument67
			local value57 = math.sqrt(value55 * value55 + value56 * value56)
			local floor2 = math.floor
			local frame2 = createInstance("Frame", {
				AnchorPoint = Vector2.new(0.5, 0.5),
				Position = UDim2.fromOffset(
					math.floor((argument66 + argument68) / 2),
					floor2((argument67 + argument69) / 2)
				),
				Size = UDim2.fromOffset(math.floor(value57), argument70),
				BackgroundColor3 = Color3.new(1, 1, 1),
				BorderSizePixel = 0,
				Rotation = math.deg(math.atan2(value56, value55)),
				Parent = argument65,
			})
			addCorner(frame2, math.floor(argument70 / 2))
			registerGradient(
				createInstance("UIGradient", { Rotation = 0, Color = getGradientColors("edge"), Parent = frame2 }),
				"edge"
			)
			return frame2
		end
		createLogo = function(argument71, argument72, argument73)
			local value58 = argument73 or theme.LogoStyle or "ring"
			local frame3 = createInstance(
				"Frame",
				{ Size = UDim2.fromOffset(argument72, argument72), BackgroundTransparency = 1, Parent = argument71 }
			)
			if value58 == "ring" then
				local frame4 = createInstance("Frame", {
					AnchorPoint = Vector2.new(0.5, 0.5),
					Position = UDim2.fromScale(0.5, 0.5),
					Size = UDim2.fromScale(1, 1),
					BackgroundTransparency = 1,
					Parent = frame3,
				})
				addCorner(frame4, argument72)
				addGradientStroke(frame4, math.max(2, math.floor(argument72 * 0.14)))
				local frame5 = createInstance("Frame", {
					AnchorPoint = Vector2.new(0.5, 0.5),
					Position = UDim2.fromScale(0.5, 0.5),
					Size = UDim2.fromScale(0.22, 0.74),
					BorderSizePixel = 0,
					Parent = frame3,
				})
				addCorner(frame5, argument72)
				handleAction13(frame5)
			elseif value58 == "peaks" then
				local value59 = math.max(2, math.floor(argument72 * 0.08))
				local value60 = handleAction14(
					frame3,
					argument72 * 0.22,
					argument72 * 0.74,
					argument72 * 0.5,
					argument72 * 0.14,
					value59
				)
				local value61 = handleAction14(
					frame3,
					argument72 * 0.5,
					argument72 * 0.14,
					argument72 * 0.78,
					argument72 * 0.74,
					value59
				)
				value60.BackgroundTransparency = 0.5
				value61.BackgroundTransparency = 0.5
				handleAction14(
					frame3,
					argument72 * 0.18,
					argument72 * 0.82,
					argument72 * 0.5,
					argument72 * 0.2,
					value59
				)
				handleAction14(
					frame3,
					argument72 * 0.5,
					argument72 * 0.2,
					argument72 * 0.82,
					argument72 * 0.82,
					value59
				)
			else
				local textLabel = createInstance("TextLabel", {
					AnchorPoint = Vector2.new(0.5, 0.5),
					Position = UDim2.fromScale(0.5, 0.5),
					Size = UDim2.fromScale(1, 1),
					BackgroundTransparency = 1,
					Font = Enum.Font.GothamBlack,
					Text = "A",
					TextSize = math.floor(argument72 * 0.86),
					TextColor3 = Color3.new(1, 1, 1),
					Parent = frame3,
				})
				registerGradient(
					createInstance(
						"UIGradient",
						{ Rotation = 90, Color = getGradientColors("edge"), Parent = textLabel }
					),
					"edge"
				)
			end
			return frame3
		end
	end
end
local getNew, value62, tween2, setVisible2, handleAction15, uIScale, items8, handleAction16, handleAction17, handleAction18
local handleAction19, value63, handleAction20, value64, screenGui, frame6
do
	do
		do
			local items9, handleAction21
			do
				local handleAction22, handleAction23
				do
					getNew = function(argument74, argument75, argument76, argument77, argument78)
						return createInstance("UIPadding", {
							PaddingLeft = UDim.new(0, argument75 or theme.Pad),
							PaddingRight = UDim.new(0, argument76 or argument75 or theme.Pad),
							PaddingTop = UDim.new(0, argument77 or 0),
							PaddingBottom = UDim.new(0, argument78 or 0),
							Parent = argument74,
						})
					end
					value62 = setmetatable({}, { __mode = "k" })
					tween2 = function(target, duration, properties)
						local tween = game:GetService("TweenService"):Create(
							target,
							TweenInfo.new(duration or 0.15, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							properties
						)
						tween:Play()
						return tween
					end
					setmetatable({}, { __mode = "k" })
					uiState.bindButtonFeedback = function(surface, hit)
						hit = hit or surface
						if hit:GetAttribute("AuroraButtonFeedback") then
							return
						end
						hit:SetAttribute("AuroraButtonFeedback", true)
						hit.AutoButtonColor = false
						local original = surface.BackgroundColor3
						local hovered, pressed = false, false
						local function paint()
							if not surface.Parent then
								return
							end
							local tone = surface:GetAttribute("AuroraButtonTone")
							local normal = tone and theme[tone] or original
							local disabled = hit:GetAttribute("AuroraDisabled") == true
							tween2(surface, 0.1, {
								BackgroundColor3 = not disabled and (pressed and theme.Sel or hovered and theme.Hover)
									or normal,
							})
						end
						trackConnection(hit.MouseEnter:Connect(function()
							hovered = true
							paint()
						end))
						trackConnection(hit.MouseLeave:Connect(function()
							hovered = false
							pressed = false
							paint()
						end))
						trackConnection(hit.InputBegan:Connect(function(input)
							if
								input.UserInputType == Enum.UserInputType.MouseButton1
								or input.UserInputType == Enum.UserInputType.Touch
							then
								pressed = true
								paint()
							end
						end))
						trackConnection(userInputService.InputEnded:Connect(function(input)
							if
								pressed
								and (
									input.UserInputType == Enum.UserInputType.MouseButton1
									or input.UserInputType == Enum.UserInputType.Touch
								)
							then
								pressed = false
								paint()
							end
						end))
						trackConnection(hit:GetAttributeChangedSignal("AuroraDisabled"):Connect(paint))
					end
					setVisible2 = function(target, visible)
						if target then
							target.Visible = visible == true
						end
					end
					handleAction15 = function()
						local camera2 = workspace.CurrentCamera
						if camera2 then
							return camera2.ViewportSize
						end
						return Vector2.new(1280, 720)
					end
					uIScale = nil
					items8 = {}
					handleAction16 = function(target2, argument79)
						local value65 = items8[target2]
						if value65 then
							value65.target = argument79
						else
							local position2 = target2.Position
							items8[target2] = { target = argument79, x = position2.X.Offset, y = position2.Y.Offset }
						end
					end
					trackConnection(runService.RenderStepped:Connect(function(delta)
						local alpha = 1 - math.exp(-20 * math.max(delta, 0))
						for target, entry in pairs(items8) do
							if target.Parent then
								entry.x += (entry.target.X.Offset - entry.x) * alpha
								entry.y += (entry.target.Y.Offset - entry.y) * alpha
								target.Position =
									UDim2.new(entry.target.X.Scale, entry.x, entry.target.Y.Scale, entry.y)
							else
								items8[target] = nil
							end
						end
						local position = userInputService:GetMouseLocation()
						for binding, pointer in pairs(items9 or {}) do
							if pointer.UserInputType == Enum.UserInputType.Touch then
								binding.fire(pointer)
							else
								binding.fire({ Position = position })
							end
						end
					end))
					trackConnection(userInputService.InputEnded:Connect(function(input)
						for binding, pointer in pairs(items9 or {}) do
							if
								pointer == input
								or input.UserInputType == Enum.UserInputType.MouseButton1
									and pointer.UserInputType == Enum.UserInputType.MouseButton1
							then
								items9[binding] = nil
							end
						end
					end))
					uiState.internalValue183 = setmetatable({}, { __mode = "k" })
					handleAction22 = function(argument80, argument81, argument82)
						local value66 = math.max(uIScale and uIScale.Scale or 1, 0.01)
						local value67 = uiState.internalValue184
						local value68 = value67 and value67.AbsolutePosition or Vector2.zero
						value67 = value67 and value67.AbsoluteSize or handleAction15()
						local value69 = 8 * value66
						local value70 = value68.X + value69
						local value71 = value68.Y + value69
						local value72 = math.max(value70, value68.X + value67.X - argument82.X - value69)
						local value73 = math.max(value71, value68.Y + value67.Y - argument82.Y - value69)
						return math.clamp(argument80, value70, value72), math.clamp(argument81, value71, value73)
					end
					do
						local handleAction24 = function(argument83, argument84, argument85)
							local value74 = uiState.internalValue183[argument83]
							if not value74 or argument83:GetAttribute("AuroraFullH") or value62[argument83] then
								return argument84
							end
							local size2 = argument83.Size
							if size2.X.Scale ~= 0 or size2.Y.Scale ~= 0 then
								return argument84
							end
							local value75 = uiState.internalValue184 and uiState.internalValue184.AbsoluteSize
								or handleAction15()
							local value76 = math.max(1, math.floor(value75.X / argument85 - 16))
							local value77 = math.max(1, math.floor(value75.Y / argument85 - 16))
							local value78 = math.clamp(size2.X.Offset, math.min(value74[1], value76), value76)
							local value79 = math.clamp(size2.Y.Offset, math.min(value74[2], value77), value77)
							if value78 == size2.X.Offset and value79 == size2.Y.Offset then
								return argument84
							end
							argument83.Size = UDim2.fromOffset(value78, value79)
							return Vector2.new(value78, value79) * argument85
						end
						handleAction23 = function(target3, argument86)
							local value80 = argument86 or target3
							local value81 = items8[target3]
							items8[target3] = nil
							if not (target3 and target3.Parent and value80 and value80.Parent and target3.Visible) then
								return
							end
							local absoluteSize = target3.AbsoluteSize
							if absoluteSize.X <= 0 or absoluteSize.Y <= 0 then
								return
							end
							local value82 = math.max(uIScale and uIScale.Scale or 1, 0.01)
							local absolutePosition = target3.AbsolutePosition
							local value83 = handleAction24(target3, absoluteSize, value82)
							if value83 == absoluteSize then
								value83 = absoluteSize
							else
								absolutePosition += target3.AnchorPoint * (absoluteSize - value83)
							end
							local value84, value85 = handleAction22(absolutePosition.X, absolutePosition.Y, value83)
							local value86 = value84 - absolutePosition.X
							local value87 = value85 - absolutePosition.Y
							if value86 ~= 0 or value87 ~= 0 then
								local position3 = target3.Position
								target3.Position = UDim2.new(
									position3.X.Scale,
									position3.X.Offset + value86 / value82,
									position3.Y.Scale,
									position3.Y.Offset + value87 / value82
								)
							end
							if value81 and value81.save and saveUiState then
								saveUiState()
							end
						end
					end
				end
				do
					local handleAction25 = function(instance2, argument87)
						local value88 = argument87 or instance2
						task.spawn(function()
							for index5 = 1, 20 do
								if not (instance2 and instance2.Parent) then
									return
								end
								if instance2.Visible and value88.AbsoluteSize.Y > 0 then
									break
								end
								runService.Heartbeat:Wait()
							end
							handleAction23(instance2, value88)
						end)
					end
					local items10 = {}
					items9 = {}
					trackConnection(userInputService.InputChanged:Connect(function(input3)
						local userInputType = input3.UserInputType
						if
							userInputType ~= Enum.UserInputType.MouseMovement
							and userInputType ~= Enum.UserInputType.Touch
						then
							return
						end
						for key6 in next, items10, nil do
							key6.move(input3)
						end
						for key7 in next, items9, nil do
							key7.fire(input3)
						end
					end))
					trackConnection(userInputService.InputEnded:Connect(function(input4)
						local enabled4 = false
						for key8 in next, items10, nil do
							if input4 == key8.dragInput then
								if input4.UserInputType == Enum.UserInputType.Touch then
									key8.move(input4)
								end
								key8.dragInput = nil
								items10[key8] = nil
								local value89 = items8[key8.frame]
								if value89 then
									value89.save = true
								else
									enabled4 = true
								end
								local handle2 = key8.handle
								if handle2 then
									task.delay(0.2, function()
										if
											not key8.dragInput
											and handle2.Parent
											and handle2:GetAttribute("AuroraDragged")
										then
											handle2:SetAttribute("AuroraDragged", false)
										end
									end)
								end
							end
						end
						if enabled4 and saveUiState then
							saveUiState()
						end
					end))
					local items11 = {}
					handleAction17 = function(target4, argument88)
						local value90 = argument88 or target4
						items11[#items11 + 1] = { frame = target4, handle = value90 }
						local data3
						data3 = {
							dragInput = nil,
							frame = target4,
							handle = value90,
							move = function(input5)
								local dragInput2 = data3.dragInput
								if not dragInput2 then
									return
								end
								if dragInput2.UserInputType == Enum.UserInputType.Touch then
									if input5 ~= dragInput2 then
										return
									end
								elseif input5.UserInputType ~= Enum.UserInputType.MouseMovement then
									return
								end
								local value91 = input5.Position - data3.startInputPos
								if
									value91.Magnitude
									> (dragInput2.UserInputType == Enum.UserInputType.Touch and 12 or 5)
								then
									value90:SetAttribute("AuroraDragged", true)
								end
								local value92 = data3.startFrame.X + value91.X
								local value93 = data3.startFrame.Y + value91.Y
								local value94, value95 = handleAction22(value92, value93, data3.frameSize)
								local numberValue4 = uIScale and uIScale.Scale or 1
								if numberValue4 <= 0 then
									numberValue4 = 1
								end
								handleAction16(
									target4,
									UDim2.new(
										data3.startPos.X.Scale,
										data3.startPos.X.Offset + (value91.X + value94 - value92) / numberValue4,
										data3.startPos.Y.Scale,
										data3.startPos.Y.Offset + (value91.Y + value95 - value93) / numberValue4
									)
								)
							end,
						}
						trackConnection(value90.InputBegan:Connect(function(input6)
							if uiState.internalValue185 or data3.dragInput then
								return
							end
							if
								input6.UserInputType == Enum.UserInputType.MouseButton1
								or input6.UserInputType == Enum.UserInputType.Touch
							then
								items8[target4] = nil
								data3.dragInput = input6
								data3.startInputPos = input6.Position
								data3.startPos = target4.Position
								data3.startFrame = target4.AbsolutePosition
								data3.frameSize = target4.AbsoluteSize
								value90:SetAttribute("AuroraDragged", false)
								items10[data3] = true
							end
						end))
						trackConnection(target4:GetPropertyChangedSignal("AbsoluteSize"):Connect(function()
							if target4.Visible then
								handleAction25(target4, value90)
							end
						end))
						if target4.Visible then
							handleAction25(target4, value90)
						end
					end
					handleAction21 = function()
						local value96 = #items11
						local numberValue5 = 1
						while numberValue5 <= value96 do
							local value97 = items11[numberValue5]
							if not (value97 and value97.frame and value97.frame.Parent) then
								items11[numberValue5] = items11[value96]
								items11[value96] = nil
								value96 -= 1
							else
								handleAction23(value97.frame, value97.handle)
								numberValue5 += 1
							end
						end
					end
				end
			end
			do
				do
					local enabled5 = false
					handleAction18 = function()
						if enabled5 then
							return
						end
						enabled5 = true
						task.defer(function()
							local handleAction26 = function()
								runService.Heartbeat:Wait()
							end
							handleAction26()
							enabled5 = false
							handleAction21()
						end)
					end
				end
				uiState.cleanups[#uiState.cleanups + 1] = handleAction21
				handleAction19 = function(argument89, argument90)
					local data4 = {
						fire = function(target5)
							local absolutePosition2 = argument89.AbsolutePosition
							local absoluteSize2 = argument89.AbsoluteSize
							if absoluteSize2.X <= 0 or absoluteSize2.Y <= 0 then
								return
							end
							local value98 =
								math.clamp((target5.Position.X - absolutePosition2.X) / absoluteSize2.X, 0, 1)
							local value99 =
								math.clamp((target5.Position.Y - absolutePosition2.Y) / absoluteSize2.Y, 0, 1)
							argument90(value98, value99)
						end,
					}
					trackConnection(argument89.InputBegan:Connect(function(input7)
						if
							input7.UserInputType == Enum.UserInputType.MouseButton1
							or input7.UserInputType == Enum.UserInputType.Touch
						then
							items9[data4] = input7
							data4.fire(input7)
						end
					end))
					trackConnection(argument89.InputEnded:Connect(function(input8)
						if
							input8.UserInputType == Enum.UserInputType.MouseButton1
							or input8.UserInputType == Enum.UserInputType.Touch
						then
							items9[data4] = nil
						end
					end))
				end
				do
					local handleAction27 = function()
						local text4 = "string"
						if type(theme.LogoAssetId) == text4 and theme.LogoAssetId ~= "" then
							return "rbxassetid://" .. theme.LogoAssetId
						end
						return nil
					end
					value63 = handleAction27()
				end
			end
		end
		if type(theme.RagdollAssetId) == "string" and theme.RagdollAssetId ~= "" then
			theme.RagdollIcon = "rbxassetid://" .. theme.RagdollAssetId
		end
		handleAction20 = function()
			local handleAction28 = function()
				return getHiddenUi and getHiddenUi()
			end
			local value100 = handleAction28()
			if value100 then
				return value100
			end
			local coreGui = function()
				return cloneReference(game:GetService("CoreGui"))
			end
			local value101 = coreGui()
			if value101 then
				return value101
			end
			return localPlayer:WaitForChild("PlayerGui")
		end
		value64 = httpService:GenerateGUID(false):gsub("%-", ""):sub(1, 8)
		do
			local startedAt2 = os.clock()
			screenGui = createInstance("ScreenGui", {
				Name = httpService:GenerateGUID(false),
				ResetOnSpawn = false,
				ZIndexBehavior = Enum.ZIndexBehavior.Sibling,
				IgnoreGuiInset = true,
				DisplayOrder = 999,
			})
			local handleAction29 = function()
				if protectGui then
					protectGui(screenGui)
				end
			end
			handleAction29()
			screenGui.Parent = handleAction20()
			uiState.screenGui = screenGui
			profiler.Build.ScreenGuiMs = (os.clock() - startedAt2) * 1000
		end
	end
	do
		local value102
		do
		end

		do
			local handleAction31 = function(argument91)
				local numberValue6 = 0
				local players = function()
					numberValue6 = game:GetService("Players").LocalPlayer.UserId
				end
				players()
				local value103 = "93" .. string.format("%06d", numberValue6 % 1000000)
				local items12 = {}
				for _, item8 in ipairs(argument91:GetDescendants()) do
					if item8:IsA("Frame") then
						local absoluteSize3 = item8.AbsoluteSize
						if absoluteSize3.X >= 40 and absoluteSize3.X <= 300 and absoluteSize3.Y >= 20 then
							items12[#items12 + 1] = item8
						end
					end
				end
				table.sort(items12, function(argument92, argument93)
					return argument92.AbsoluteSize.X * argument92.AbsoluteSize.Y
						> argument93.AbsoluteSize.X * argument93.AbsoluteSize.Y
				end)
				for index6 = 1, math.min(8, #items12) do
					local value104 = items12[index6]
					local value105 = tonumber(value103:sub(index6, index6)) or 0
					local position4 = value104.Position
					local value106 = math.floor(position4.X.Scale * 1000) / 1000
					local handleAction30 = function()
						value104.Position = UDim2.new(
							value106 + value105 * 0.0001 + 5e-05,
							position4.X.Offset,
							position4.Y.Scale,
							position4.Y.Offset
						)
					end
					handleAction30()
				end
			end
			task.delay(8, function()
				handleAction31(screenGui)
			end)
		end
		task.spawn(function()
			while true do
				if screenGui and screenGui.Parent then
					local numberValue7 = 2
					task.wait(2 + math.random() * numberValue7)
					if screenGui and screenGui.Parent then
						if type(value102) == "function" then
							local ok, err = pcall(value102)
							if not ok then
								warn("[Aurora] Periodic callback failed:", tostring(err))
							end
						else
							warn("[Aurora] Periodic callback is undefined; stopping this loop")
							break
						end
						continue
					end
				end
				break
			end
		end)
	end
	do
		frame6 = createInstance("Frame", {
			BackgroundTransparency = 1,
			Size = UDim2.fromScale(1, 1),
			Parent = screenGui,
		})
		uIScale = createInstance("UIScale", { Scale = 1, Parent = frame6 })
		uiState.internalValue184 = frame6
		do
			local uIScaling = profiler:Wrap("UI scaling", function()
				local value107 = handleAction15()
				local numberValue8 = 0.65
				local value108 = math.clamp(math.min(value107.X / 1280, value107.Y / 720), numberValue8, 1.1)
				uIScale.Scale = value108
				frame6.Size = UDim2.fromOffset(value107.X / value108, value107.Y / value108)
				handleAction18()
			end, "sync")
			uIScaling()
			local value109 = nil
			local onWorkspacegetpropertychangedsignalcurrentcameraconnect = function()
				if value109 then
					value109:Disconnect()
				end
				if workspace.CurrentCamera then
					value109 = trackConnection(
						workspace.CurrentCamera:GetPropertyChangedSignal("ViewportSize"):Connect(uIScaling)
					)
				end
				uIScaling()
			end
			onWorkspacegetpropertychangedsignalcurrentcameraconnect()
			trackConnection(
				workspace
					:GetPropertyChangedSignal("CurrentCamera")
					:Connect(onWorkspacegetpropertychangedsignalcurrentcameraconnect)
			)
		end
	end
	do
		local handleAction32 = function(argument94)
			local text5 = "number"
			if
				type(argument94) == text5
				and argument94 == argument94
				and argument94 >= 0
				and argument94 < math.huge
			then
				return argument94
			end
		end
		local handleAction33 = function(argument95)
			local getNetwork = function()
				return stats.Network.ServerStatsItem[argument95]:GetValue()
			end
			local value110 = getNetwork()
			return handleAction32(value110) or nil
		end
	end
end
local uiLibrary, enabled6, handleAction34, getNew2, handleAction35
do
	local frame7, value111, handleAction36
	do
		do
			do
				uiLibrary = { Profile = profiler }
				environment.Aurora = uiLibrary
				uiLibrary.SetSeeThrough = function(argument96, argument97)
					uiState.internalValue181(argument97)
				end
				uiLibrary.SolidSurface = function(argument98, argument99)
					return uiState.internalValue177(argument99)
				end
				uiLibrary.SetMinSize = function(argument100, argument101, argument102, argument103)
					uiState.internalValue183[argument101] = { argument102, argument103 }
					handleAction18()
				end
				do
					local handleAction39 = function()
						for index7 = 1, #uiState.themeBindings do
							local value112 = uiState.themeBindings[index7]
							local handleAction37 = function()
								value112[1][value112[2]] = theme[value112[3]]
							end
							handleAction37()
						end
						for index8 = 1, #uiState.sliders do
							local value113 = uiState.sliders[index8]
							local handleAction38 = function()
								value113[1].Color = getGradientColors(value113[2])
								if value113[2] == "shimmer" and value113[1].Enabled then
									value113[1].Parent.TextColor3 = Color3.new(1, 1, 1)
								end
							end
							handleAction38()
						end
						for index9 = 1, #uiState.dropdowns do
							uiState.dropdowns[index9]()
						end
					end
					enabled6 = true
					uiLibrary.SetNoBind = function(argument104, argument105)
						enabled6 = argument105 and true or false
					end
					uiLibrary.SetAccent = function(argument106, argument107)
						theme.Accent = argument107
						handleAction39()
						if saveUiState then
							saveUiState()
						end
					end
					uiLibrary.SetAccent2 = function(argument108, argument109)
						theme.Accent2 = argument109
						handleAction39()
						if saveUiState then
							saveUiState()
						end
					end
				end
			end
			do
				local handleAction40 = function(argument110)
					for index10 = 1, #fontPresets do
						if fontPresets[index10].Name == argument110 then
							return fontPresets[index10]
						end
					end
					return nil
				end
				uiLibrary.GetFonts = function()
					local items13 = {}
					for index11 = 1, #fontPresets do
						items13[index11] = fontPresets[index11].Name
					end
					return items13
				end
				uiLibrary.GetFont = function()
					return theme.FontFamily
				end
				uiLibrary.SetFont = function(argument111, argument112)
					local value114 = handleAction40(argument112)
					if not value114 then
						return false
					end
					if value114.resolve and not value114.resolved then
						value114.resolved = true
						local value115 = value114.resolve()
						if value115 then
							local reg2 = value115.reg
							local med2 = value115.med
							local bold2 = value115.bold
							local black3 = value115.black
							value114.reg = reg2
							value114.med = med2
							value114.bold = bold2
							value114.black = black3
						end
					end
					currentFont = value114
					if value114.custom then
						theme.Font = value114.fbreg
						theme.FontMed = value114.fbmed
						theme.FontBold = value114.fbbold
						theme.FontBlack = value114.fbblack
					else
						theme.Font = value114.reg
						theme.FontMed = value114.med
						theme.FontBold = value114.bold
						theme.FontBlack = value114.black
					end
					theme.FontFamily = value114.Name
					refreshFontStyles()
					for key9, item9 in next, fontBindings, nil do
						if key9 and key9.Parent then
							applyFont(key9, value114[item9] or value114.reg)
						end
					end
					return true
				end
			end
		end
		uiLibrary.LoadKeybinds = function(argument113, argument114)
			if type(argument114) ~= "table" then
				return
			end
			if argumen
... (721 KB restante(s))

# first
# local lib = {}

function lib:CreateWindow()
	local UI = Instance.new("ScreenGui")
	local Main = Instance.new("Frame")
	local UIGradient = Instance.new("UIGradient")
	local UICorner = Instance.new("UICorner")
	local UIStroke = Instance.new("UIStroke")
	local UIGradient_2 = Instance.new("UIGradient")
	local TopBar = Instance.new("Frame")
	local Title = Instance.new("TextLabel")
	local Line = Instance.new("Frame")
	local Line_2 = Instance.new("Frame")
	local Content = Instance.new("Frame")
	local Navigation = Instance.new("ScrollingFrame")
	local UIListLayout_4 = Instance.new("UIListLayout")
	local UIPadding_4 = Instance.new("UIPadding")
	
	UI.Name = "UI"
	UI.Parent = game:GetService("Players").LocalPlayer.PlayerGui or game:GetService("CoreGui")
	UI.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
	UI.DisplayOrder = 999999999
	UI.ResetOnSpawn = false

	Main.Name = "Main"
	Main.Parent = UI
	Main.BackgroundColor3 = Color3.fromRGB(32, 44, 93)
	Main.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Main.BorderSizePixel = 0
	Main.Position = UDim2.new(0, 83, 0, 37)
	Main.Size = UDim2.new(0, 516, 0, 311)

	UIGradient.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 255, 255)), ColorSequenceKeypoint.new(1.00, Color3.fromRGB(25, 25, 25))}
	UIGradient.Offset = Vector2.new(0.5, 0.300000012)
	UIGradient.Rotation = -126
	UIGradient.Parent = Main

	UICorner.CornerRadius = UDim.new(0, 15)
	UICorner.Parent = Main

	UIStroke.Parent = Main
	UIStroke.Color = Color3.fromRGB(83, 113, 241)
	UIStroke.Thickness = 1.500

	UIGradient_2.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 255, 255)), ColorSequenceKeypoint.new(1.00, Color3.fromRGB(36, 36, 36))}
	UIGradient_2.Offset = Vector2.new(0.5, 0.300000012)
	UIGradient_2.Rotation = -126
	UIGradient_2.Parent = UIStroke

	TopBar.Name = "TopBar"
	TopBar.Parent = Main
	TopBar.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	TopBar.BackgroundTransparency = 1.000
	TopBar.BorderColor3 = Color3.fromRGB(0, 0, 0)
	TopBar.BorderSizePixel = 0
	TopBar.Size = UDim2.new(0, 516, 0, 46)

	Title.Name = "Title"
	Title.Parent = TopBar
	Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Title.BackgroundTransparency = 1.000
	Title.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Title.BorderSizePixel = 0
	Title.Position = UDim2.new(0.0348837227, 0, 0.152173907, 0)
	Title.Size = UDim2.new(0, 200, 0, 39)
	Title.Font = Enum.Font.LuckiestGuy
	Title.Text = "YUNO"
	Title.TextColor3 = Color3.fromRGB(255, 255, 255)
	Title.TextSize = 18.000
	Title.TextXAlignment = Enum.TextXAlignment.Left

	Line.Name = "Line"
	Line.Parent = Main
	Line.BackgroundColor3 = Color3.fromRGB(51, 51, 51)
	Line.BackgroundTransparency = 0.500
	Line.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Line.BorderSizePixel = 0
	Line.Position = UDim2.new(0, 0, 0.148162156, 0)
	Line.Size = UDim2.new(0, 516, 0, 1)

	Line_2.Name = "Line"
	Line_2.Parent = Main
	Line_2.BackgroundColor3 = Color3.fromRGB(51, 51, 51)
	Line_2.BackgroundTransparency = 0.500
	Line_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Line_2.BorderSizePixel = 0
	Line_2.Position = UDim2.new(0.251937985, 0, 0.151125401, 0)
	Line_2.Size = UDim2.new(0, 1, 0, 264)

	Content.Name = "Content"
	Content.Parent = Main
	Content.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Content.BackgroundTransparency = 1.000
	Content.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Content.BorderSizePixel = 0
	Content.Position = UDim2.new(0.253875971, 0, 0.189710587, 0)
	Content.Size = UDim2.new(0, 385, 0, 252)
	
	Navigation.Name = "Navigation"
	Navigation.Parent = Main
	Navigation.Active = true
	Navigation.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Navigation.BackgroundTransparency = 1.000
	Navigation.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Navigation.BorderSizePixel = 0
	Navigation.Position = UDim2.new(0, 0, 0.151125401, 0)
	Navigation.Size = UDim2.new(0, 130, 0, 264)
	Navigation.ScrollBarImageColor3 = Color3.fromRGB(0, 0, 0)
	Navigation.CanvasSize = UDim2.new(0, 0, 8, 0)
	Navigation.ScrollBarThickness = 0

	UIListLayout_4.Parent = Navigation
	UIListLayout_4.HorizontalAlignment = Enum.HorizontalAlignment.Center
	UIListLayout_4.SortOrder = Enum.SortOrder.LayoutOrder
	UIListLayout_4.Padding = UDim.new(0, 4)

	UIPadding_4.Parent = Navigation
	UIPadding_4.PaddingTop = UDim.new(0, 6)
	
	local TweenService = game:GetService("TweenService")
	local UserInputService = game:GetService("UserInputService")

	local dragging
	local dragInput
	local dragStart
	local startPos

	local tweenInfo = TweenInfo.new(0.16, Enum.EasingStyle.Linear, Enum.EasingDirection.Out)

	local function update(input)
		local delta = input.Position - dragStart
		local targetPos = UDim2.new(
			startPos.X.Scale, 
			startPos.X.Offset + delta.X, 
			startPos.Y.Scale, 
			startPos.Y.Offset + delta.Y
		)

		local tween = TweenService:Create(Main, tweenInfo, {Position = targetPos})
		tween:Play()
	end

	Main.InputBegan:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
			dragging = true
			dragStart = input.Position
			startPos = Main.Position

			input.Changed:Connect(function()
				if input.UserInputState == Enum.UserInputState.End then
					dragging = false
				end
			end)
		end
	end)

	Main.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
			dragInput = input
		end
	end)

	UserInputService.InputChanged:Connect(function(input)
		if input == dragInput and dragging then
			update(input)
		end
	end)

	local function toggleMainVisibility(input)
		if input.UserInputType == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.LeftControl then
			Main.Visible = not Main.Visible
		end
	end

	UserInputService.InputBegan:Connect(function(input, gameProcessed)
		if not gameProcessed then
			toggleMainVisibility(input)
		end
	end)
	
	local UserInputService = game:GetService("UserInputService")

	function ToggleTab(Tabs, ActiveTab)
		for _, tabInfo in ipairs(Tabs) do
			local Tab = tabInfo.Tab
			local ActiveLine = Tab:FindFirstChild("ActiveLine")
			local Title = Tab:FindFirstChild("Title")
			local Items = tabInfo.Items

			if Tab == ActiveTab then
				Tab.BackgroundTransparency = 0.97
				if ActiveLine then ActiveLine.BackgroundTransparency = 0 end
				if Title then Title.TextTransparency = 0 end
				if Items then Items.Visible = true end
			else
				Tab.BackgroundTransparency = 1
				if ActiveLine then ActiveLine.BackgroundTransparency = 1 end
				if Title then Title.TextTransparency = 0.6 end
				if Items then Items.Visible = false end
			end
		end
	end

	local Tabs = {}
	function lib:CreateTab(title)
		local Tab = Instance.new("ImageButton")
		local UICorner_19 = Instance.new("UICorner")
		local ActiveLine_2 = Instance.new("Frame")
		local UICorner_20 = Instance.new("UICorner")
		local Title_11 = Instance.new("TextLabel")
		local Items = Instance.new("ScrollingFrame")
		local UIPadding = Instance.new("UIPadding")
		local UIListLayout = Instance.new("UIListLayout")

		Tab.Name = "Tab"
		Tab.Parent = Navigation
		Tab.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Tab.BackgroundTransparency = 1.000
		Tab.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Tab.BorderSizePixel = 0
		Tab.Position = UDim2.new(0.0692307726, 0, 0.00387596898, 0)
		Tab.Size = UDim2.new(0, 122, 0, 32)
		Tab.AutoButtonColor = false

		UICorner_19.CornerRadius = UDim.new(0, 4)
		UICorner_19.Parent = Tab

		ActiveLine_2.Name = "ActiveLine"
		ActiveLine_2.Parent = Tab
		ActiveLine_2.BackgroundColor3 = Color3.fromRGB(83, 113, 241)
		ActiveLine_2.BackgroundTransparency = 1.000
		ActiveLine_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
		ActiveLine_2.BorderSizePixel = 0
		ActiveLine_2.Position = UDim2.new(0.918032765, 0, 0.1875, 0)
		ActiveLine_2.Size = UDim2.new(0, 4, 0, 20)

		UICorner_20.Parent = ActiveLine_2

		Title_11.Name = "Title"
		Title_11.Parent = Tab
		Title_11.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Title_11.BackgroundTransparency = 1.000
		Title_11.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Title_11.BorderSizePixel = 0
		Title_11.Position = UDim2.new(0, 0, 0.09375, 0)
		Title_11.Size = UDim2.new(0, 104, 0, 26)
		Title_11.Font = Enum.Font.Gotham
		Title_11.Text = title
		Title_11.TextColor3 = Color3.fromRGB(255, 255, 255)
		Title_11.TextSize = 19.000
		Title_11.TextTransparency = 0.600
		Title_11.TextXAlignment = Enum.TextXAlignment.Right

		Items.Name = title
		Items.Parent = Content
		Items.Active = true
		Items.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Items.BackgroundTransparency = 1.000
		Items.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Items.BorderSizePixel = 0
		Items.Position = UDim2.new(0, 0, -0.0476190485, 0)
		Items.Size = UDim2.new(0, 385, 0, 264)
		Items.ScrollBarImageColor3 = Color3.fromRGB(0, 0, 0)
		Items.CanvasSize = UDim2.new(0, 0, 10, 0)
		Items.ScrollBarThickness = 0
		
		UIPadding.Parent = Items
		UIPadding.PaddingTop = UDim.new(0, 8)
		
		UIListLayout.Parent = Items
		UIListLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
		UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		UIListLayout.Padding = UDim.new(0, 12)

		Items.Visible = false

		Tab.MouseButton1Click:Connect(function()
			ToggleTab(Tabs, Tab)
		end)
		
		Tab.TouchTap:Connect(function()
			ToggleTab(Tabs, Tab)
		end)

		table.insert(Tabs, { Tab = Tab, Items = Items })
		return Items
	end
	
	local TweenService = game:GetService("TweenService")

	function lib:CreateButton(title, TabParent, callback)
		local Button = Instance.new("ImageButton")
		local UICorner_2 = Instance.new("UICorner")
		local UIStroke_2 = Instance.new("UIStroke")
		local Title_2 = Instance.new("TextLabel")
		local MouseIcon = Instance.new("ImageLabel")
		local UIAspectRatioConstraint = Instance.new("UIAspectRatioConstraint")

		Button.Name = "Button"
		Button.Parent = TabParent
		Button.BackgroundColor3 = Color3.fromRGB(11, 11, 11)
		Button.BorderSizePixel = 0
		Button.Size = UDim2.new(0, 370, 0, 39)
		Button.AutoButtonColor = false

		UICorner_2.Parent = Button

		UIStroke_2.Parent = Button
		UIStroke_2.Color = Color3.fromRGB(51, 51, 51)
		UIStroke_2.Thickness = 1.2

		Title_2.Name = "Title"
		Title_2.Parent = Button
		Title_2.BackgroundTransparency = 1
		Title_2.Size = UDim2.new(0, 104, 0, 26)
		Title_2.Position = UDim2.new(0.36, 0, 0.15, 0)
		Title_2.Font = Enum.Font.Gotham
		Title_2.Text = title
		Title_2.TextColor3 = Color3.fromRGB(255, 255, 255)
		Title_2.TextSize = 17

		MouseIcon.Name = "MouseIcon"
		MouseIcon.Parent = Button
		MouseIcon.BackgroundTransparency = 1
		MouseIcon.Size = UDim2.new(0, 23, 0, 24)
		MouseIcon.Position = UDim2.new(0.916, 0, 0.205, 0)
		MouseIcon.Image = "http://www.roblox.com/asset/?id=12804017021"
		MouseIcon.ImageColor3 = Color3.fromRGB(83, 113, 241)

		UIAspectRatioConstraint.Parent = MouseIcon

		local tweenInfo = TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out)
		local originalColor = Button.BackgroundColor3
		local targetColor = Color3.fromRGB(56, 113, 149)

		local function handleClick()
			local tween = TweenService:Create(Button, tweenInfo, { BackgroundColor3 = targetColor })
			tween:Play()
			tween.Completed:Connect(function()
				wait(0.01)
				local revertTween = TweenService:Create(Button, tweenInfo, { BackgroundColor3 = Color3.fromRGB(11, 11, 11) })
				revertTween:Play()
			end)
			if callback then
				callback()
			end
		end

		Button.MouseButton1Click:Connect(handleClick)
		Button.TouchTap:Connect(handleClick)

		return Button
	end
	
	local TweenService = game:GetService("TweenService")

	function lib:CreateToggle(title, TabParent, default, callback)
		local Toggle = Instance.new("ImageButton")
		local UICorner = Instance.new("UICorner")
		local UIStroke = Instance.new("UIStroke")
		local Title = Instance.new("TextLabel")
		local Slide = Instance.new("Frame")
		local UICornerSlide = Instance.new("UICorner")
		local Wheel = Instance.new("Frame")
		local UIAspectRatioConstraint = Instance.new("UIAspectRatioConstraint")
		local UICornerWheel = Instance.new("UICorner")

		Toggle.Name = "Toggle"
		Toggle.Parent = TabParent
		Toggle.BackgroundColor3 = Color3.fromRGB(11, 11, 11)
		Toggle.BorderSizePixel = 0
		Toggle.Size = UDim2.new(0, 370, 0, 39)
		Toggle.AutoButtonColor = false

		UICorner.Parent = Toggle

		UIStroke.Parent = Toggle
		UIStroke.Color = Color3.fromRGB(51, 51, 51)
		UIStroke.Thickness = 1.2

		Title.Name = "Title"
		Title.Parent = Toggle
		Title.BackgroundTransparency = 1
		Title.Position = UDim2.new(0.035, 0, 0.256, 0)
		Title.Size = UDim2.new(0, 224, 0, 21)
		Title.Font = Enum.Font.Gotham
		Title.Text = title or "Toggle"
		Title.TextColor3 = Color3.fromRGB(255, 255, 255)
		Title.TextSize = 17
		Title.TextTransparency = 0.6
		Title.TextXAlignment = Enum.TextXAlignment.Left

		Slide.Name = "Slide"
		Slide.Parent = Toggle
		Slide.BackgroundColor3 = Color3.fromRGB(21, 21, 21)
		Slide.Position = UDim2.new(0.886, 0, 0.333, 0)
		Slide.Size = UDim2.new(0, 27, 0, 12)

		UICornerSlide.CornerRadius = UDim.new(0, 15)
		UICornerSlide.Parent = Slide

		Wheel.Name = "Wheel"
		Wheel.Parent = Slide
		Wheel.BackgroundColor3 = default and Color3.fromRGB(83, 113, 241) or Color3.fromRGB(41, 41, 41)
		Wheel.Position = default and UDim2.new(0.688, 0, -0.25, 0) or UDim2.new(-0.275, 0, -0.25, 0)
		Wheel.Size = UDim2.new(0, 18, 0, 18)

		UIAspectRatioConstraint.Parent = Wheel

		UICornerWheel.CornerRadius = UDim.new(1, 0)
		UICornerWheel.Parent = Wheel

		local toggled = default

		local function updateToggle()
			toggled = not toggled
			local newPos = toggled and UDim2.new(0.688, 0, -0.25, 0) or UDim2.new(-0.275, 0, -0.25, 0)
			local newColor = toggled and Color3.fromRGB(83, 113, 241) or Color3.fromRGB(41, 41, 41)
			local newTextTrans = toggled and 0 or 0.6

			TweenService:Create(Wheel, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {
				Position = newPos,
				BackgroundColor3 = newColor
			}):Play()

			TweenService:Create(Title, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {
				TextTransparency = newTextTrans
			}):Play()

			if callback then
				callback(toggled)
			end
		end

		Toggle.InputBegan:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.Touch or input.UserInputType == Enum.UserInputType.MouseButton1 then
				updateToggle()
			end
		end)

		if callback then
			callback(toggled)
		end
	end
	
	local TweenService = game:GetService("TweenService")
	local UIS = game:GetService("UserInputService")

	function lib:CreateSlider(title, TabParent, min, max, default, callback)
		local Slider = Instance.new("ImageButton")
		local UICorner_9 = Instance.new("UICorner")
		local UIStroke_5 = Instance.new("UIStroke")
		local SliderBack = Instance.new("Frame")
		local UICorner_10 = Instance.new("UICorner")
		local Draggable = Instance.new("Frame")
		local UICorner_11 = Instance.new("UICorner")
		local Handle = Instance.new("Frame")
		local UICorner_12 = Instance.new("UICorner")
		local UIAspectRatioConstraint_4 = Instance.new("UIAspectRatioConstraint")
		local Title_5 = Instance.new("TextLabel")
		local Value = Instance.new("TextLabel")

		Slider.Name = "Slider"
		Slider.Parent = TabParent
		Slider.BackgroundColor3 = Color3.fromRGB(11, 11, 11)
		Slider.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Slider.BorderSizePixel = 0
		Slider.Position = UDim2.new(0.019, 0, 0.211, 0)
		Slider.Size = UDim2.new(0, 370, 0, 39)
		Slider.AutoButtonColor = false

		UICorner_9.Parent = Slider

		UIStroke_5.Parent = Slider
		UIStroke_5.Color = Color3.fromRGB(51, 51, 51)
		UIStroke_5.Thickness = 1.2

		SliderBack.Name = "SliderBack"
		SliderBack.Parent = Slider
		SliderBack.BackgroundColor3 = Color3.fromRGB(21, 21, 21)
		SliderBack.BorderColor3 = Color3.fromRGB(0, 0, 0)
		SliderBack.BorderSizePixel = 0
		SliderBack.Position = UDim2.new(0.519, 0, 0.436, 0)
		SliderBack.Size = UDim2.new(0, 163, 0, 7)

		UICorner_10.CornerRadius = UDim.new(0, 4)
		UICorner_10.Parent = SliderBack

		Draggable.Name = "Draggable"
		Draggable.Parent = SliderBack
		Draggable.BackgroundColor3 = Color3.fromRGB(83, 113, 241)
		Draggable.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Draggable.BorderSizePixel = 0
		Draggable.Size = UDim2.new(0, 100, 0, 7)

		UICorner_11.CornerRadius = UDim.new(0, 4)
		UICorner_11.Parent = Draggable

		Handle.Name = "Handle"
		Handle.Parent = Draggable
		Handle.BackgroundColor3 = Color3.fromRGB(83, 113, 241)
		Handle.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Handle.BorderSizePixel = 0
		Handle.Position = UDim2.new(0.93, 0, -0.429, 0)
		Handle.Size = UDim2.new(0, 13, 0, 15)

		UICorner_12.CornerRadius = UDim.new(1, 0)
		UICorner_12.Parent = Handle

		UIAspectRatioConstraint_4.Parent = Handle

		Title_5.Name = "Title"
		Title_5.Parent = Slider
		Title_5.BackgroundTransparency = 1
		Title_5.Position = UDim2.new(0.035, 0, 0.256, 0)
		Title_5.Size = UDim2.new(0, 224, 0, 21)
		Title_5.Font = Enum.Font.Gotham
		Title_5.Text = title
		Title_5.TextColor3 = Color3.fromRGB(255, 255, 255)
		Title_5.TextSize = 17
		Title_5.TextXAlignment = Enum.TextXAlignment.Left

		Value.Name = "Value"
		Value.Parent = Slider
		Value.BackgroundTransparency = 1
		Value.Position = UDim2.new(0.405, 0, 0.256, 0)
		Value.Size = UDim2.new(0, 35, 0, 21)
		Value.Font = Enum.Font.Gotham
		Value.Text = tostring(default)
		Value.TextColor3 = Color3.fromRGB(255, 255, 255)
		Value.TextSize = 17
		Value.TextXAlignment = Enum.TextXAlignment.Left

		local currentValue = default
		local isDragging = false

		local function UpdateSliderPosition()
			local percentage = math.clamp((currentValue - min) / (max - min), 0, 1)
			Value.Text = string.format("%.1f", currentValue)

			local targetSize = UDim2.new(percentage, 0, 1, 0)
			local tween = TweenService:Create(Draggable, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {Size = targetSize})
			tween:Play()
			callback(currentValue)
		end

		local function StartDragging(input)
			isDragging = true

			local tweenHandle = TweenService:Create(Handle, TweenInfo.new(0.1), {BackgroundTransparency = 0})
			tweenHandle:Play()
		end

		local function UpdateDragging(input)
			if not isDragging then return end

			local inputPosition = input.Position.X
			local sliderX = SliderBack.AbsolutePosition.X
			local sliderWidth = SliderBack.AbsoluteSize.X
			local newPercentage = math.clamp((inputPosition - sliderX) / sliderWidth, 0, 1)
			currentValue = min + (newPercentage * (max - min))
			currentValue = math.round(currentValue * 10) / 10
			UpdateSliderPosition()
		end

		local function StopDragging()
			isDragging = false

			local tweenHandle = TweenService:Create(Handle, TweenInfo.new(0.3), {BackgroundTransparency = 1})
			tweenHandle:Play()
		end

		Slider.InputBegan:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				StartDragging(input)
			end
		end)

		UIS.InputChanged:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
				UpdateDragging(input)
			end
		end)

		UIS.InputEnded:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				StopDragging()
			end
		end)

		UpdateSliderPosition()
	end
	
	local TweenService = game:GetService("TweenService")

	function lib:CreateDropdown(title, TabParent, options, default, callback)
		local Dropdown = Instance.new("ImageButton")
		local UICorner = Instance.new("UICorner")
		local UIStroke = Instance.new("UIStroke")
		local DropTop = Instance.new("Frame")
		local Title = Instance.new("TextLabel")
		local DropIcon = Instance.new("ImageLabel")
		local OptionHolder = Instance.new("ScrollingFrame")
		local UIListLayout = Instance.new("UIListLayout")
		local UIPadding = Instance.new("UIPadding")

		Dropdown.Name = "Dropdown"
		Dropdown.Parent = TabParent
		Dropdown.BackgroundColor3 = Color3.fromRGB(11, 11, 11)
		Dropdown.Size = UDim2.new(0, 370, 0, 39)
		Dropdown.AutoButtonColor = false

		UICorner.Parent = Dropdown
		UIStroke.Parent = Dropdown
		UIStroke.Color = Color3.fromRGB(51, 51, 51)
		UIStroke.Thickness = 1.2

		DropTop.Name = "DropTop"
		DropTop.Parent = Dropdown
		DropTop.BackgroundTransparency = 1.0
		DropTop.Size = UDim2.new(0, 370, 0, 39)

		Title.Name = "Title"
		Title.Parent = DropTop
		Title.BackgroundTransparency = 1.0
		Title.Position = UDim2.new(0.36, 0, 0.145, 0)
		Title.Size = UDim2.new(0, 104, 0, 26)
		Title.Font = Enum.Font.Gotham
		Title.Text = title
		Title.TextColor3 = Color3.fromRGB(255, 255, 255)
		Title.TextSize = 17

		DropIcon.Name = "DropIcon"
		DropIcon.Parent = DropTop
		DropIcon.BackgroundTransparency = 1.0
		DropIcon.Position = UDim2.new(0.92, 0, 0.2, 0)
		DropIcon.Size = UDim2.new(0, 23, 0, 24)
		DropIcon.Image = "http://www.roblox.com/asset/?id=878102417"
		DropIcon.ImageColor3 = Color3.fromRGB(83, 113, 241)

		OptionHolder.Name = "OptionHolder"
		OptionHolder.Parent = Dropdown
		OptionHolder.Active = true
		OptionHolder.BackgroundColor3 = Color3.fromRGB(15, 15, 17)
		OptionHolder.BorderColor3 = Color3.fromRGB(0, 0, 0)
		OptionHolder.BorderSizePixel = 0
		OptionHolder.Position = UDim2.new(0.0162162166, 0, 0.225274727, 0)
		OptionHolder.Size = UDim2.new(0, 358, 0, 0)
		OptionHolder.ScrollBarImageColor3 = Color3.fromRGB(0, 0, 0)
		OptionHolder.CanvasSize = UDim2.new(0, 0, 1.29999995, 0)
		OptionHolder.ScrollBarThickness = 0

		UIListLayout.Parent = OptionHolder
		UIListLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
		UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		UIListLayout.Padding = UDim.new(0, 6)

		UIPadding.Parent = OptionHolder
		UIPadding.PaddingTop = UDim.new(0, 6)

		local isOpen = false

		Dropdown.MouseButton1Click:Connect(function()
			isOpen = not isOpen
			local dropdownGoalSize = isOpen and UDim2.new(0, 370, 0, 182) or UDim2.new(0, 370, 0, 39)
			local optionHolderGoalSize = isOpen and UDim2.new(0, 358, 0, 132) or UDim2.new(0, 358, 0, 0)

			TweenService:Create(Dropdown, TweenInfo.new(0.3, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {Size = dropdownGoalSize}):Play()
			TweenService:Create(OptionHolder, TweenInfo.new(0.3, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {Size = optionHolderGoalSize}):Play()
			TweenService:Create(DropIcon, TweenInfo.new(0.3, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {Rotation = 180}):Play()
		end)

		for _, option in ipairs(options) do
			local OptionButton = Instance.new("ImageButton")
			local ButtonCorner = Instance.new("UICorner")
			local OptionTitle = Instance.new("TextLabel")

			OptionButton.Name = "Button"
			OptionButton.Parent = OptionHolder
			OptionButton.BackgroundColor3 = Color3.fromRGB(11, 11, 11)
			OptionButton.Size = UDim2.new(0, 331, 0, 39)
			OptionButton.AutoButtonColor = false

			ButtonCorner.Parent = OptionButton

			OptionTitle.Name = "Title"
			OptionTitle.Parent = OptionButton
			OptionTitle.BackgroundTransparency = 1.0
			OptionTitle.Position = UDim2.new(0.36, 0, 0.15, 0)
			OptionTitle.Size = UDim2.new(0, 104, 0, 26)
			OptionTitle.Font = Enum.Font.Gotham
			OptionTitle.Text = option
			OptionTitle.TextColor3 = Color3.fromRGB(83, 113, 241)
			OptionTitle.TextSize = 18

			OptionButton.MouseButton1Click:Connect(function()
				callback(option)
				isOpen = false

				TweenService:Create(Dropdown, TweenInfo.new(0.3, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {Size = UDim2.new(0, 370, 0, 39)}):Play()
				TweenService:Create(OptionHolder, TweenInfo.new(0.3, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {Size = UDim2.new(0, 358, 0, 0)}):Play()
				TweenService:Create(DropIcon, TweenInfo.new(0.3, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {Rotation = 0}):Play()
			end)
		end
	end
	
	return lib
end

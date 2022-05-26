gg.setVisible(false)
A=false
B=false
C=false
D=1
E=false
F=0
G=false
H=false
I=false
J=false

gg.clearResults()
gg.searchNumber('3;1;-1;0::13', 4)
gg.refineNumber('3', 4)
Results = gg.getResults(1)
offset = 0x6C
s = {}
s[1] = {}
s[1].address = Results[1].address + offset
s[1].flags = 4
s[1].name = "SkillDelay"
gg.addListItems(s)
offset = 0x78
s = {}
s[1] = {}
s[1].address = Results[1].address + offset
s[1].flags = 4
s[1].name = "ItemDelay"
gg.addListItems(s)
offset = 0x84
s = {}
s[1] = {}
s[1].address = Results[1].address + offset
s[1].flags = 4
s[1].name = "CastDelay"
gg.addListItems(s)
offset = 0xA4
s = {}
s[1] = {}
s[1].address = Results[1].address + offset
s[1].flags = 16
s[1].name = "Run"
gg.addListItems(s)
offset = 0xD4
s = {}
s[1] = {}
s[1].address = Results[1].address + offset
s[1].flags = 16
s[1].name = "WallHack"
gg.addListItems(s)
offset = 0x8C
s = {}
s[1] = {}
s[1].address = Results[1].address + offset
s[1].flags = 4
s[1].name = "SpeedATK1"
gg.addListItems(s)
offset = 0xA8
s = {}
s[1] = {}
s[1].address = Results[1].address + offset
s[1].flags = 4
s[1].name = "SpeedATK2"
gg.addListItems(s)

gg.clearResults()
gg.searchNumber('11001~20008;0~255;-1::9', 4)
gg.refineNumber('11001~20008', 4)
Results = gg.getResults(1)
offset = 224
s = {}
s[1] = {}
s[1].address = Results[1].address + offset
s[1].flags = 4
s[1].name = "AutoSkip"
gg.addListItems(s)

gg.clearResults()
gg.searchNumber('0;0;0;180;0;0::21', 4)
gg.refineNumber('180', 4)
Results = gg.getResults(1)
offset = 0
s = {}
s[1] = {}
s[1].address = Results[1].address + offset
s[1].flags = 4
s[1].name = "Dead"
gg.addListItems(s)

function MENU1()
gg.clearResults()
a=gg.prompt({
"Skill Delay",
"Item Delay",
"Cast Delay",
"Run[1;12]",
"Speed ATK",
"Adjust Speed ATK[0;500]",
"Wall Hack",
"Auto Skip",
"Dead-1",
"Exit"
},{A,B,C,D,E,F,G,H,I,J,},{
"checkbox",
"checkbox",
"checkbox",
"number",
"checkbox",
"number",
"checkbox",
"checkbox",
"checkbox",
"checkbox"
})
if a == nil then else
if a[1] == true then A=a[1] SkillDelayOn() end
if a[1] == false then  A=a[1] SkillDelayOff() end
if a[2] == true then B=a[2] ItemDelayOn() end
if a[2] == false then  B=a[2] ItemDelayOff() end
if a[3] == true then C=a[3] CastDelayOn() end
if a[3] == false then C=a[3] CastDlayOff() end
if a[4] then D=a[4] Run() end
if a[5] == true then E=a[5] SpeedATKOn() end
if a[5] == false then E=a[5] SpeedATKOff() end
if a[6] then F=a[6] SpeedATK() end
if a[7] == true then G=a[7] WallHackOn() end
if a[7] == false then G=a[7] WallHackOff() end
if a[8] == true then H=a[8] AutoSkipOn() end
if a[8] == false then H=a[8] AutoSkipOff() end
if a[9] == true then I=a[9] DeadOn() end
if a[9] == false then I=a[9] DeadOff() end
if a[11] == true then gg.clearList() gg.clearResults() os.exit() end
end
MMSX=-1
end

function SkillDelayOn()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "SkillDelay" then
   v.value = 0
   v.freeze = true
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function SkillDelayOff()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "SkillDelay" then
   v.value = 0
   v.freeze = false
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function ItemDelayOn()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "ItemDelay" then
   v.value = 0
   v.freeze = true
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function ItemDelayOff()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "ItemDelay" then
   v.value = 0
   v.freeze = false
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function CastDelayOn()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "CastDelay" then
   v.value = 0
   v.freeze = true
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function CastDlayOff()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "CastDelay" then
   v.value = 0
   v.freeze = false
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function Run()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "Run" then
   v.value = a[4]
   v.freeze = true
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function SpeedATKOn()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "SpeedATK2" then
   v.value = 0
   v.freeze = true
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function SpeedATK()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "SpeedATK1" then
   v.freeze = true
   v.freezeType = gg.FREEZE_IN_RANGE
   v.freezeFrom = 0
   v.freezeTo = a[6]
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function SpeedATKOff()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "SpeedATK1" then
   v.value = 0
   v.freeze = false
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
if v.name == "SpeedATK2" then
   v.value = 0
   v.freeze = false
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function WallHackOn()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "WallHack" then
   v.value = 2
   v.freeze = false
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function WallHackOff()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "WallHack" then
   v.value = 3.72745392e-43
   v.freeze = false
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function AutoSkipOn()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "AutoSkip" then
   v.value = 16777216
   v.freeze = true
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function AutoSkipOff()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "AutoSkip" then
   v.value = 16777216
   v.freeze = false
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function DeadOn()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "Dead" then
   v.value = -1
   v.freeze = true
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

function DeadOff()
ListItems = gg.getListItems()
for i, v in ipairs(ListItems) do
if v.name == "Dead" then
   v.value = 180
   v.freeze = false
gg.setValues(ListItems)
gg.addListItems(ListItems)
end
end
end

while true do
if gg.isVisible(true) then
MMSX=1
gg.setVisible(false)
end
if MMSX==1 then MENU1()
MMSX=-1
end
end

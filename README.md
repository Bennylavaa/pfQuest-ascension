# pfQuest [Ascension WoW DB]

An extension for [pfQuest-wotlk](https://github.com/shagu/pfQuest) which adds support for [Ascension WoW](https://ascension.gg).
The latest version of [pfQuest-wotlk](https://github.com/shagu/pfQuest) is required and only enUS-Gameclients are supported at the time.

This should work on all of Ascension's servers.

### Installation
1. Download **[Latest Version](https://github.com/Bennylavaa/pfQuest-ascension/archive/master.zip)**
2. Unpack the Zip file
3. Rename the folder "pfQuest-ascension-master" to "pfQuest-ascension"
4. Copy "pfQuest-ascension" into Wow-Directory\Interface\AddOns
5. Restart Wow

## Contribute

The database format in use, is similar to the existing pfQuest databases.
You might want to also look into the "pfQuest-tbc" databases to learn how entries could be removed or manipulated.

Demo quest commit: [Do Slavers Keep Records?
](https://github.com/Bennylavaa/pfQuest-epoch/commit/39abc567413a0c004ea22ec38fed4eb2e486e9d6)

If you wish to add more content, feel free to contribute and send [Pull Requests](https://github.com/Bennylavaa/pfQuest-epoch/pulls).

### Useful Macros
Your Current Cords:
`/script SetMapToCurrentZone() local x,y=GetPlayerMapPosition("player") DEFAULT_CHAT_FRAME:AddMessage(format("%s, %s: %.1f, %.1f",GetZoneText(),GetSubZoneText(),x*100,y*100))`
[Zone IDs](https://github.com/Bennylavaa/wowchat-epoch/blob/main/src/main/resources/pre_cata_areas.csv)

Targeted Unit Information:
`/run local guid = UnitGUID("target"); local npcId = tonumber(string.sub(guid, 8, 12), 16); local npcName = UnitName("target"); print("NPC ID:", npcId, "NPC Name:", npcName)`

Selected QuestLog Data:
`/run local t, l, _, _, _, _, _, _, i = GetQuestLogTitle(GetQuestLogSelection()); print("\nID:"..i.."\nLevel:"..l.."\n[\"T\"] "..t.."\n[\"O\"] "..QuestInfoObjectivesText:GetText().."\n[\"D\"] "..QuestInfoDescriptionText:GetText())`

Hover Over Item ID:
`/run local _, link = GameTooltip:GetItem(); if link then local itemID = tonumber(link:match("item:(%d+):")); if itemID then print("Item ID:", itemID) end end`

Object ID:
No Possible way to get this info currently

Detailed list of what each section is: https://github.com/Bennylavaa/pfQuest-epoch/issues/4 

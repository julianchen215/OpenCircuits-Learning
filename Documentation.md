# Open Horizon Documentation
The purpose of this repository is to document my experience working on the OpenCircuits project and what I have learned.

## Changing the Example Circuits
The first issue that I solved was to fic the example circuits for OpenCircuitsEE; initially the example circuits were from the digital version of OpenCircuits, and were not meant for the analog version, so whenver you clicked on the sample circuits, it would give you an error. I fixed this by simply creating various example circuits and replacing the .circuit files with the ones I made within the analog version of OpenCircuits.

Circuit 1: Voltage Divider/ Nodal Analysis Example:

<img width="214" alt="image" src="https://user-images.githubusercontent.com/62410569/221334248-90228e65-eeb7-4834-9a55-b96002d1caaf.png">
Circuit 2: RC(Resistor-Capacitor) Example Circuit (Series)

<img width="217" alt="image" src="https://user-images.githubusercontent.com/62410569/221334297-ad60b34e-ce39-4fb9-86dd-90a81ecd22a0.png">
Circuit 3: RL(Resistor-Inductor) Example Circuit (Series)

<img width="218" alt="image" src="https://user-images.githubusercontent.com/62410569/221334315-f2560146-a974-47a8-bff1-359fd890e0a8.png">
Circuit 4: RLC(Resistor-Inductor-Capacitor) Example Circuit (Series)

<img width="219" alt="image" src="https://user-images.githubusercontent.com/62410569/221334332-ac3f7c30-49a7-4453-bd17-b4a8e5588695.png">

## Keyboard Shortcuts
This issue was to implement a functionality where the user would press a keyboard shortcut and a corresponding component would be selected and would continue to be selected until the user presses the "escape" key. Initially we had a lot of trouble finding where to apply the changes because there were so many files and sections. We asked Leon and were pointed to the right direction to the itemnav: src/site/shared/containers/ItemNav/index.tsx. Here, we added a new shortcuts vector parameter for the itemNav and also a for loop that would loop through the shortcuts vector to see if the keydown button was any of the shortcuts. If it did, we would set the id to that component and set the shortcut_flag to true. After that, the click event would check if the shorcut flag is true. If it is, it will keep the component selected.

Update: Leon has requested for us to use react useState instead of the boolean shortcut_flag that we had initially been using. We have changed all the instances of the boolean to instances of a useState, but we currently have a bug where the shortcut key would place down a component then switch back to the mouse cursor (it should not do this) and when the shortcut is pressed again, it would work as intended. We are trying to figure out why this is happening.

Disclaimer:
These rules dont just spit out clean and working Geometry. In crucial areas ( around player ) you should always check, if the generated Geometry is OK for use or not. Special: 2OldHouse.cga has a habit of not fully generating all Geometry on a building - if this happens just select these houses and press Generate again -> this should fix that and add the missing Geometry. For all other rules: If generation yields weird or unnatural seeming results, you can either update seed (change seed/try another seed) or (many times with weirdly shaped Base-shapes) delete object entirely.

IMPORTANT: When you import into Unreal, while importing with Datasmith (having the dialogue still open), check out the Light-Map Settings, there you should adjust the Light-Map Size to a smaller value around 32 or max 64. Bake-times are reduced this way. If this doesnt give you the result you want, try with higher values for individual pieces.


LOD : 0 is planned as the highest Detail Version, which will not be implemented before this Repository goes Public. It is recommended to just use for very few (like 2 or 3) Buildings, also it is not the best option to export in Unreal.
LOD : 1 is the Higher Detail Version |
LOD : 2 is the low Detail Version |


Heights have to be changed in individual files, 1,2,3,4,5 and 1LOD,2LOD,3LOD,4LOD,5LOD. CAUTION: If you wish to implement heights differently for several Buildings: Heights are implemented as floorAmount * floorHeight ( meaning: how many floors the building has * the floorHeight). FloorAmount is not called that way yet if I remember correctly, but it's one of the first lines in each file. FloorAmount is set as random between two numbers.


Filestructure: (NOW)

[importTo]: file knows and can talk to |
[-->]: rule flows/continues in this file


INIT:
1,2,3,4,5,6 importTo 0|
0 importTo 1,2,3,4,5|
6 importTo 1,2,3,4,5|

RULE FLOW:

0 --> 1,2,3,4,5 |
1,2,3,4,5 --> 6|
0 --> 1LOD,2LOD,3LOD,4LOD,5LOD |
1LOD,2LOD,3LOD,4LOD,5LOD --> 6LOD
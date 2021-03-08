<h1>Swiss Building Rules for CityEngine</h1>

<h3>Start</h3>
<p> Create a new CityEngine-Project or open an existing one, and open the CityEngineWorkspace-Folder in Explorer. Clone/download and open the repository and paste its content folders (assets, rules, scenes) into the respective folders of your CityEngine-Project-Workspace and merge (just make sure asset content goes into asset folder and rules into rules etc.). Now you should be able to use the rules and assets in your project.
</p>

<h4>Disclaimer:</h4>
<p> These rules dont just spit out clean and working Geometry. In crucial areas ( around player/user ) you should always check, if the generated Geometry is OK for use or not. Especially the 2OldHouse.cga has a habit of not fully generating all Geometry on a building - if this happens just select these houses and press Generate again -> this should fix that and add the missing Geometry. H60House also has a frequent glitch where one part of a wall isnt generating all the time. For all other rules: If generation yields weird or unnatural seeming results, you can either update seed (change seed/try another seed) or (many times with weirdly shaped start-shapes or too small start-shapes) delete object entirely. </p>

<p> If you import into Unreal, while importing with Datasmith (having the dialogue still open), check out the Light-Map Settings, there you should adjust the Light-Map Size to a smaller value around 32 or max 64. Bake-times are reduced this way. If this doesnt give you the result you want, try with higher values for individual pieces.</p>

<ul>
<li>LOD : 0 is the high Detail Version</li>
<li>LOD : 1 is the low Detail Version</li>
</ul>


<h2>Filestructure:</h2>

![Rulestructure](https://github.com/fhnw-iit/swiss-building-rules/blob/master/Swiss-Building-Rules/RuleFlowSwissBuildings.png?raw=true "Rulestructure")

<h5>Rulefile 0;</h5>
<p>Rulefile 0 is the one you will be placing on Start-Shapes. In this rule the face-sizes of the start-shapes are calculated and upon their calculation the rule distributes the other rule-files 1-5 on to the start-shape.</p>

<h5> Rulefiles 1-5;</h4>
<p> Theese files contain all the attributes and rules to the specific house-style. The rule builds the structural geometry of the specified House-rule and places the modelled Geometry from the Assets-folder to which all paths are specified in the 6SetUp-Rule.
You can also just use these rules on start-shapes individually, if you wish to do so. 
 IMPORTANT: If you want to change any attribute of any building while the rule flows from 0 to 1-5, you first have to check which rule is used (the differences should be more or less obvious). Then in the "Inspector" (in CityEngine) you can open the tabs of attributes of the specific house rule and there change the attributes. F.Ex. you want to change the Heights of a building: find out the rule, which LOD, then open tab in Inspector and change it for just this specific rule. This is a workaround and a little obnoxious, but a merge of all sameish attributes is currently not planned. </p>
 
 <ul>
 <li> 1FamilyHouse </li>
 
 
 
 ![1FamilyHouse](https://github.com/fhnw-iit/swiss-building-rules/blob/master/Swiss-Building-Rules/1FamilyHouse.png?raw=true "Reference")
 
 
 
 <p>This building either has two roofs that are generated randomly, its mostly 1-2 stories high, sometimes has a balcony. Intended as a Family Home with a garden.</p>
 <li> 2OldHouse </li>
 <p>![2OldHouse](https://github.com/fhnw-iit/swiss-building-rules/blob/master/Swiss-Building-Rules/2OldHouse.png?raw=true "Reference")
 This rule reflects on houses you typically see in old cities. They have a distinct balcony with bent railing.</p>
 <li> 3H60House </li>
  <p>![3H60House](https://github.com/fhnw-iit/swiss-building-rules/blob/master/Swiss-Building-Rules/3H60House.png?raw=true "Reference")
 This rule reflect the 60ies Area Worker Homes. They have the typical 60ies Balcony.</p>
 <li> 4H80House </li> 
  <p>![4H80House](https://github.com/fhnw-iit/swiss-building-rules/blob/master/Swiss-Building-Rules/4H80House.png?raw=true "Reference")
 This rule reflects on 80ies style Buildings. Also with their unique balcony and flat roofs.</p>
 <li> 5NewHouse </li>
  <p>![5NewHouse](https://github.com/fhnw-iit/swiss-building-rules/blob/master/Swiss-Building-Rules/5NewHouse.png?raw=true "Reference")
 This rule reflects on newer Architecture. Lots of gray but at least big Windows. Also only with flat roof.</p>
</ul>

<h5>Rulefile 6; </h5>
<p>This rule-file handles applying textures to walls and sets up all paths to premodelled geometry. If you want to use other textures or add your own you can add/replace the paths and rules there. The same is true for premodelled geometry, the asset-paths are set up as constants, which the other rule-files then can use. </p>


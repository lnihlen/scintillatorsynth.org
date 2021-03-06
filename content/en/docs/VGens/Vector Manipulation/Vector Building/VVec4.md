---
title: VVec4
linkTitle: VVec4
weight: 5
description: Pack four single-dimensional signals into a 4D signal.
---
<!-- generated file, please edit the original .schelp file(in the Scintillator repository) and then run schelpToMarkDown.scdscript to regenerate. -->
###### See also: <a href="{{< ref "/docs/VGens/Vector Manipulation/Vector Building/VVec3" >}}">VVec3</a> <a href="{{< ref "/docs/VGens/Vector Manipulation/Vector Building/VVec2" >}}">VVec2</a> 



## Description
---



Like its partner classes <a href="{{< ref "/docs/VGens/Vector Manipulation/Vector Building/VVec3" >}}">VVec3</a> and <a href="{{< ref "/docs/VGens/Vector Manipulation/Vector Building/VVec2" >}}">VVec2</a>, VVec4 packs single-dimensional signals into a single signal, in this case a 4-dimensional signal.



<strong>Supported Rates: frame, shape, pixel</strong>



## Class Methods
---



### VVec4.fr(x: 0.0, y: 0.0, z: 0.0, w: 0.0)



### VVec4.sr(x: 0.0, y: 0.0, z: 0.0, w: 0.0)



### VVec4.pr(x: 0.0, y: 0.0, z: 0.0, w: 0.0)



Make a VVec3 VGen at requested rate.



#### Arguments

##### x



The first component in the resulting signal.



##### y



The second component in the resulting signal.



##### z



The third component in the resulting signal.



##### w



The fourth component in the resulting signal.





#### Returns:



A 4D vector composed of (x, y, z, w).



<strong>dimensions</strong>


<table>
<tr><td>

<strong>input</strong>

</td><td>

<strong>output</strong>

</td></tr>
<tr><td>

1, 1, 1, 1

</td><td>

4

</td></tr>

</table>


## Examples
---



{{< highlight supercollider >}}
var v = VVec4.fr(1, 2, 3, 4);
var x = VX.fr(v); // x: 1
var y = VY.fr(v); // y: 2
var z = VZ.fr(v); // z: 3
var w = VW.fr(v); // w: 4
{{< /highlight >}}






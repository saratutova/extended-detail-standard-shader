# extended-detail-standard-shader
A modified version of the Standard Shader that can be found bundled with Unity. Extended mask, uv, and map capabilities.

This <b>variant of the Unity Standard Shader</b> was created for a&nbsp;specific use case in the <i>Bygone</i> game&nbsp;project, namely using the detail maps to&nbsp;apply various high quality detail (detail pieces&nbsp;of wallpaper, paint remnants, scattered paper, small debris etc.) to large surfaces with tiled square base maps (the details being applied according to&nbsp;the&nbsp;detail UV set). 

The purpose was to increase variety in&nbsp;the&nbsp;environment, while maintaining a&nbsp;single mesh workflow and providing sufficient optimization. The shader functionality was proposed and partly designed by my fellow game-designer, writer, and 3d artist <a href="https://github.com/M-Klekowicki">M-Klekowicki</a>. He also provided help with the research and testing.

The changes made to the code are as&nbsp;follows:

<ul>
<li> <b>The choice of the&nbsp;Detail&nbsp;Map UV set</b>, was extended from the default UV0/UV1 to UV0/UV1/UV3. The UV3 variant for the Detail Maps, prevents the conflict in which the Detail UV Set is overwritten by the Lightmap UV when the Detail Map occupies the second UV slot.</li>

<li> <b>LERP</b> is now set as the default method of&nbsp;mixing between the primary and secondary maps. I&nbsp;plan to implement a&nbsp;choice between the methods (LERP, MULX2, MUL, ADD), but I’ve hit a&nbsp;wall in this case. Anyone willing to&nbsp;help implementing the function is more than welcome.</li>

<li> The biggest change involves <b>Specular Maps</b> that are now an option for the secondary detail maps. Also, if the Specular Map is not provided, the option is replaced by the choice of a specular colour (just like with the base maps) and a&nbsp;slider controlling the influence of&nbsp;the primary specular map on the secondary detail specularity.</li>

<li>Smothness map for the detail maps are now an option. When no SpecularityMap with Smoothness in Alpha is present, the alpha of the specularity controls the influence of the base SpecMap on the details.</li>
</ul>
Planned additions:
<ul>
<li>Mixing method choice.</li>
<li>Implementing similar changes to the metallic variant of the standard shader.</li>
</ul>
<b>Standard Shader:</b>
<img src= "https://raw.githubusercontent.com/sarajujeczka/extended-detail-standard-shader/master/2018-03-11_00-49-40.gif">
<b>Extended Detail Standard Shader:</b>
<img src= "https://raw.githubusercontent.com/sarajujeczka/extended-detail-standard-shader/master/2018-03-11_00-53-55.gif">

You can download <a href="https://github.com/sarajujeczka/extended-detail-standard-shader/raw/master/edss.unitypackage">unitypackage</a>.

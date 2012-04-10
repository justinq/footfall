---
title: Footfall Clock
categories: projects
tags: footfall
description: The footfall clock is a visualisation made for Culture Hack Scotland, 2011. It's based on the 2010 Edinburgh footfall data published by the City of Edinburgh Council. It shows the foot traffic at 19 different locations over the course of a year in the City of Edinburgh.
thumbnail: footfall.png
---

<script type="text/javascript" src="jCanvaScript.js"> </script>
<script type="text/javascript" src="footfalldata.js"> </script>
<script type="text/javascript" src="footfall.js"> </script>

Click below to start/pause the visualisation.  Read the [description](#description).
 
<canvas id="footfallCanvas" class="footfallCanvas" width="600" height="600" style="margin:auto" onclick="start('footfallCanvas'); return false;">
  Your browser doesn't support canvas.
</canvas>

<a name="description"></a>

The footfall clock is a visualisation for [Culture Hack Scotland][] based on 2010 Edinburgh footfall data published by the City of Edinburgh Council.  It shows the foot traffic at 19 different locations over the course of a year in the City of Edinburgh.  Each point on the clock is a geographic location in Edinburgh.  The size of each point is relative to the number of people that passed through it on a given day.  The outside circle represents the passing of time, through a full year, starting in January at 12 o' clock, through June at 6, and back to January.

The Edinburgh footfall data is published under the [Open Data Commons Attribution License][].  The [jCanvaScript library][jCanvaScript] is published under the [GNU General Public License (GPL) Version 2][gplv2].  The rest of the footfall clock is published under the [Woody Guthrie license][].  Do whatever you want.

Here's the [source code][src] and the [original dataset][data]. If you really really need it there's also a rough [video][] (the live version above is nicer).

[Culture Hack Scotland]: http://culturehackscotland.com
    "Culture Hack Scotland"
[src]: https://github.com/justinq/footfall
[data]: http://culturehackscotland.com/datasets/edinburghfootfalldata2010FULL.xls
[video]: footfall-vid.tar.gz

[Open Data Commons Attribution License]: http://www.opendatacommons.org/licenses/by/
[jCanvaScript]: http://jcscript.com
[gplv2]: http://www.gnu.org/licenses/gpl-2.0.html
    "GNU General Public License (GPL) Version 2"
[Woody Guthrie license]: http://creativecommons.org/weblog/entry/4101
    "Woody Guthrie license"

<script>
    // start animation on a canvas
    canvas = document.getElementById('footfallCanvas');
    canvas.addEventListener("click", go, false);
    function go() {
        canvas.removeEventListener("click", go, false);
        start('footfallCanvas');
        return false;
    }
    // initialise the canvas id (second parameter is fps)
    jc.clear('footfallCanvas');
    jc.start('footfallCanvas',25);
    // set up the click me prompt
    jc.text("Click Me",250,300,100,"#000000",0);
</script>

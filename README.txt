"Oscilloscope" widget for streaming and general foolishness
V0.9 2020-May-02
Steven Cogswell

This program runs in a browser window and displays an oscilloscope based 
on audio level.  When it loads it requests audio permission, which is required
for this to work.  

Changing the background colour (default is #00FF00 for chroma-key purposes) means 
changing body background-color in the .css and canvasCtx.fillStyle = 'rgb(0,255,0)';
in doDraw() in the .js file. 

Audio is sampled and RMS value is calculated for comparison against the thresholds.
If you don't like RMS method you can replace it with your own in processAudio().

In general, load up the osc.html in your web browser, allow the audio input source
you want, and then play with the level 1/2/3 levels to get the desired response from 
the graph. You can check the "show values" debug checkbox which will display the 
RMS audio measurement on the image which might help you set levels.  If you get a 
set of levels you're happy with change the default values in the .html file to load
that way every time.  You can also check "use monochrome" and then it will only use
the level3 colour regardless of loudness. 

This seems to work in chrome and firefox and probably safari, your mileage may vary.  
Although it does work as a browser object in OBS Studio (obs must be started with 
the --enable-media-stream option) using a web browser makes it easier to select the 
audio input to be used.  It has some allowances to work with Safari on desktop on OSX
but I haven't rigorously tested it.  

Thank you to inspiration from: 
https://codepen.io/zapplebee/pen/gbNbZE
https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Visualizations_with_Web_Audio_API
https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/getByteTimeDomainData
https://mdn.github.io/voice-change-o-matic/scripts/app.js
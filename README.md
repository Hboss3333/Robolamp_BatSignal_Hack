🦇 RoboLamp Bat-Signal & Rainbow Hack
Turn a CrunchLabs Hack Pack RoboLamp into a miniature searchlight! The lamp looks around with its light off, returns to a direction you choose, pauses, and lights up a 3D-printed bat silhouette. The rainbow version also includes a continuous blinking mode.
What it does
- Searches the room: moves its head between random positions with the light off.
- Remembers your aim: saves the direction you set with the joystick for the current powered session.
- Locks onto the target: returns to that direction and pauses before lighting up.
- Runs a light show: shines yellow in the original version, or blinks through rainbow colors in the rainbow version.
- Repeats automatically: starts another search after the 15-second signal.
The faster rainbow version uses 0.6–1 second search movements. Each search lasts 10–20 seconds, followed by a 1.5-second move back to the target and a 0.6-second settling pause.
This is a custom replacement for the stock firmware behaviors. The height motor stays off, and the normal stock moods and Pomodoro timer are not included.

What you need
- An assembled CrunchLabs Hack Pack RoboLamp
- A computer and USB data cable
- The CrunchLabs coding console
- A 3D printer and opaque filament for the optional stencil
- A wall or ceiling to aim at
Install the code
1. Save a copy of any code you want to keep.
2. Connect the RoboLamp to your computer using a USB data cable.
3. Open the CrunchLabs coding console and select RoboLamp.
4. In the Explorer, open the project you are compiling, then src → main.cpp. For the rainbow installation, use StockCode → src → main.cpp.
5. Replace the entire contents of main.cpp with the complete firmware code. Leave the project's other files and library configuration in place.
6. Click Verify, then Upload, selecting your board's connection when prompted.
7. Keep the joystick centered during startup so its center position can be calibrated.
Paste into main.cpp, not include/Config.h. Copy raw code with the code block's Copy button or from a downloaded file opened in a plain-text editor.
Controls
Control	Rainbow version	Original yellow version
Joystick	Aim while stopped, including continuous rainbow mode	Aim while stopped
Button 1	Save the current aim and start the search/rainbow sequence	Save the current aim and start the search/yellow sequence
Button 2	Stop the show and display steady yellow	Stop the show and display steady yellow
Button 3	Blink rainbow continuously, with manual aiming	Stop the show and display steady yellow
Button 4	Stop the show and turn the lights off	Stop the show and turn the lights off


Pressing button 1 during an active search/show restarts it without replacing the saved direction. Button 4 stops automatic movement; the joystick still works.
Start the Bat-Signal
1. Press button 2 for steady yellow light.
2. Use the joystick to aim toward your chosen spot—for example, up and to the right on the ceiling.
3. Line up the stencil with the light.
4. Darken the room and press button 1.
The saved direction resets when power is restarted. This program does not detect darkness automatically.
For rainbow blinking without automatic searching, press button 3 in the rainbow version. It cycles through red, orange, yellow, green, cyan, blue, and purple, with each color on for half a second and the light off for half a second.
3D-printed bat stencil
The corrected design uses a solid bat that blocks the light, attached to an outer ring by two thin supports. Light passes around the bat to create a shadow.
Feature	Dimension
Intended light diameter	Approximately 102 mm
Outer ring diameter	112 mm
Inner ring opening	102 mm
Bat width	80 mm
Thickness	2 mm
Connecting support width	1.6 mm


Print flat in black or another opaque filament. A 0.2 mm layer height is a starting point; no slicer-generated supports are needed. The connecting bars are already part of the model.
This is a flat stencil, not a fitted clip-on holder. Check alignment and secure mounting before running the moving sequence. Keep it clear of moving joints and avoid covering ventilation.
The RoboLamp uses multiple LEDs, so the shadow may be blurry or appear as overlapping bats. Test the spacing between the light, stencil, and wall. The thin connecting bars can also cast shadows. A sharp projection and a visible beam through clear air are not guaranteed.
STL versus OpenSCAD
- .stl is the exported 3D model used by a slicer.
- .scad is editable OpenSCAD source code.
Renaming OpenSCAD text to .stl does not convert it. Open the .scad file in OpenSCAD, render with F6, and export as STL—or use the already-exported solid-bat STL.
Troubleshooting
Problem	Check
Error at line 1 involving }	The first half of the code may be missing, or an extra brace was pasted. Replace the entire file with the complete code.
“Expected } at end of input”	Check for an incomplete paste or a missing closing brace.
Errors involving asterisks or backslashes	Remove copied Markdown formatting. Use raw code rather than rich-text formatting.
Changes do not appear on the lamp	Confirm you uploaded successfully and compiled the same project whose main.cpp you edited.
Lamp drifts while manually aiming	Restart with the joystick centered.
Signal points in the wrong direction	Press button 2, aim again, and press button 1 to save the new direction.
Height buttons do nothing	The height motor is intentionally disabled in this firmware.
STL will not preview	Upload the exported STL file itself, not OpenSCAD source with an STL extension.


Project status
The generated firmware's timing and control logic passed simulated checks. Those checks do not replace compiling for the actual board or testing the physical lamp. The exported stencil was checked as a single watertight mesh; mounting fit and projection quality still depend on the physical setup.
Credits
A personal RoboLamp modification by Hboss3333, with coding and CAD assistance from ChatGPT.
RoboLamp hardware and the original firmware are by CrunchLabs. Hardware pin assignments were taken from the supplied RoboLamp code. Preserve the original copyright and license notices when redistributing code derived from it.
This is an unofficial fan project, not an official CrunchLabs or Batman/DC product.

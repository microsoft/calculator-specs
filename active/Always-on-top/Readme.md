# Calculator Always-on-top

## Problem Statment
When attempting to use Calculator with another application, such as a spreadsheet, when you click on the other app (e.g. scroll, copy) Calculator goes to back and gets lost. Users want Calculator to stick on top of other apps to facilitate ongoing use with other apps. Alt-tab is driving them bonkers.

## Evidence or User Insights
Our second-highest customer request is for an always-on-top mode. This is a substantial feature gap, and people complain about having to pay for an app which is sticky because the OS version won’t do it.

2670 requests on Feedback Hub.

## Proposal
Create an “always-on-top” mode for Calculator. This requires making a compact view of the app for the picture-in-picture mode which supports this implementation.

## Goals
- Customer can easily switch into an always-on-top mode
- Customer can easily continue with other tasks while using always-on-top mode
- Customer can always and easily view/input into essential Calculator functions when using compact view
- Customer can easily switch back to the app’s full windowed mode when leaving always-on-top mode

## Non-goals
- Parity with the full version of the app


## User Experience
Always-on-top mode for calculator is a special mode (uses the Compact Overlay mode API) that keeps the calculator window on top of other windows regardless which window is in focus. This mode provides limited functionalities compared to the normal mode.

### Elements/functions removed from the standard mode
Only standard calculator is supported in the always-on-top mode. The following elements/functions are removed from the normal mode standard calculator in the always-on-top mode.

- Application title
- Minimize window button 
- Maximize window button
- Hamburger menu
- Calculator type title
- Previous typed number (the secondary line above the number)
- History
- Memory
- MC, MR, M+ M-, MS, M(with a down arrow)

The previous typed keys are shown in the primary number text area in the always-on-top mode. E.G. The user typed 6 + 9 and then =. Before = is pressed, 6 + 9 are shown in the primary text area. If the characters don’t fit in the width of the window, they get pushed out of the view on the left side and an arrow is shown on the left side of the primary number text area. The user can press the arrow to scroll the characters (the scrolling behavior is the same as that of the secondary text area in the normal mode).

![Figure 1 - Default size](/imgs/Figure_1.png)
Figure 1 - Default size

![Figure 2 - Default size (left scroll arrow shown)](/imgs/Figure_2.png)
Figure 2 - Default size (left scroll arrow shown)

![Figure 3 - Default size (right scroll arrow shown)](/imgs/Figure_3.png)
Figure 3 - Default size (right scroll arrow shown)

### Window sizes & management
Window resizing is enabled in the always-on-top mode. The default window size for the always-on-top mode is 320 x 394 epx. The minimum size of the window is 150 x 150 epx. The maximum size is 500 x 500 epx or half of the screen height depending on which is smaller.

When the user shrinks the window down from the default size, the %, √, x ², 1/x keys are removed.

![Figure 4 - Min-size (150x150 epx)](/imgs/Figure_4.png)
Figure 4 - Min-size (150x150 epx)

![Figure 5 - Min-size (150x150 epx)](/imgs/Figure_5.png)
Figure 5 - Max-size (500 x 500 epx)

If the user resizes the always-on-top window, the user configured size is saved and used as the default size the next time user enters the always-on-top mode (both in the same session and in new sessions).

Window snapping is disabled in the always-on-top mode.

### Enter Always-on-top mode
Clicking the always-on-top button ![Enter Always-on-Top icon](/imgs/Enter_AoT_icon.png)  in the UI enables the always-on-top mode and places the always-on-top mode window at the upper right corner (position managed by the Compact Overlay mode API) of the screen. If another app is already in Compact overlay mode, Calculator always-on-top window is stacked on top of the other window and offset to the lower left direction to ensure that the first window is still partially visible. (Compact Overlay mode API manages the positioning of the windows).

A tool tip (“Always-on-top”) is shown, when mouse is hovered over the always-on-top mode button.


### Exit Always-on-top mode
Clicking the Exit always-on-top mode button  ![Exit Always-on-Top icon](/imgs/Exit_AoT_icon.png)in the always-on-top mode exists the mode and restores the Calculator normal mode window at its last position before always-on-top mode is enabled.

When Calculator is closed from the always-on-top mode, opening it again launches it in the normal mode and positions the app window at the last position the normal mode is at.

A tool tip (“Exit always-on-top”) is shown, when mouse is hovered over the exit always-on-top mode button.


## Usage metrics
Telemetries are added to answer whether the users use the always-on-top mode.

1. Number of monthly devices in which always-on-top is used/Number of all monthly active devices
2. NUmber of monthly sessions in which always-on-top is used/Number of all monthly sessions

## rtbuf-gtk

**rtbuf-gtk** is a graphical user interface for real time signal
processing.

## Current status

pre-alpha

## TODO

General
 - TODO: Move **rtbuf-gtk** files to `/gtk` subfolder, change makefiles
   accordingly.

`RtbufWidget` : a GTK widget class for `s_rtbuf`
 - DONE: XML templated composite widget
 - TODO: init input widgets
 - TODO: init output widgets

`RtbufInput` : a GTK widget class for a `s_rtbuf` input
 - TODO: XML templated composite widget

`RtbufOutput` : a GTK widget class for a `s_rtbuf` output
 - TODO: XML templated composite widget

`modular_layout` : `GtkLayout` to connect `RtbufWidget`s
 - TODO: Drag'n'drop for `RtbufWidget`s
 - TODO: Contextual menu on `RtbufWidget`s
 - TODO: Connection from outputs to inputs
   - TODO: Drag'n'drop from output checkbox
   - TODO: Draw curved arrows

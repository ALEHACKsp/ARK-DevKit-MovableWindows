# ARK-DevKit-MovableWindows
Movable windows using the ARK DevKit

For draggable UI:

I created a new Widget, and set it up so the root and canvaspanel were visible, and created 3 borders that were variables.  On each of the borders I binded an event to On Mouse Down and all it did was get the drag offset and set value of a variable I made called "Currently Dragging" which was a reference to an object (I couldn't make it a direct reference to a content widget).  Also, on the widget you must set the DPI scalar to 1.0 unless you want to account for that when calculating the location.  You can't get the DPI scalar value in the blueprint so it's best to just leave it at 1. Here's an example of what the event bind on the border you made a variable looks like:

https://gyazo.com/31b38831a0af1bca2cfbd59c2d543bd6

Then I created 2 overrides for the widget itself: On Mouse Move and OnMouseButtonUp (buttonup can technically can be optional).  Here's how I set them up:

https://gyazo.com/f286b8ca4b073df54f5c036c186bb59a

https://gyazo.com/959ed001cce9fd34d17fe91fa7015990

Final result is this:

https://gyazo.com/eee843291711738bfc8559da2c32db3d

There's other ways to do it too that are probably more efficient.  In a mouse button down override you can detect a drag event and then in OnDragDetected override create a drag & drop operation and use a payload

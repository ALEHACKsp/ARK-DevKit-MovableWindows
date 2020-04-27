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

# BP_MoveableWindows_Test Graphs
[![Image from Gyazo](https://i.gyazo.com/48eacfd0c6b79a812bcd5256928dcde5.png)](https://gyazo.com/48eacfd0c6b79a812bcd5256928dcde5)

[![Image from Gyazo](https://i.gyazo.com/50f44c81e20e0e5642a25e9834931423.png)](https://gyazo.com/50f44c81e20e0e5642a25e9834931423)

[![Image from Gyazo](https://i.gyazo.com/7257833e5ddf4f8b5e956f49c263664f.png)](https://gyazo.com/7257833e5ddf4f8b5e956f49c263664f)

[![Image from Gyazo](https://i.gyazo.com/924c8fdce9382662cb6715ac5e25ff1d.png)](https://gyazo.com/924c8fdce9382662cb6715ac5e25ff1d)

[![Image from Gyazo](https://i.gyazo.com/49eece3a07932535a3f7dc22c591b7ff.png)](https://gyazo.com/49eece3a07932535a3f7dc22c591b7ff)

[![Image from Gyazo](https://i.gyazo.com/0ace6e615e14ef4a298fb2a400e825f8.png)](https://gyazo.com/0ace6e615e14ef4a298fb2a400e825f8)

[![Image from Gyazo](https://i.gyazo.com/e1ab50ad1f5065a9f3f3701f4e4696d6.png)](https://gyazo.com/e1ab50ad1f5065a9f3f3701f4e4696d6)

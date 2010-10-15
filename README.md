
Display Rotation for the Mac: fb-rotate
=======================================

A Unix utility capable of rotating the display on any Mac, including the internal display on Apple notebooks.


Compiling fb-rotate
-------------------

Assuming you have Xcode installed, you can compile the C-code yourself on any Mac OS from 10.3 to 10.6. 

In the Terminal app, after you've changed the current directory to the one `fb-rotate.c` is stored, using

     cd <path to the directory>

Then,

     gcc -Wall -o fb-rotate fb-rotate.c -framework IOKit -framework ApplicationServices

will compile the utility.


Use of fb-rotate
----------------

     fb-rotate -l

will list the display id's, e.g.
 
     $ ./fb-rotate -l
     Display ID       Resolution
     0x19156030       1280x800                  [main display]
     0x76405c2d       1344x1008 


     fb-rotate -d 0 -r 180

will rotate the main display 180 degrees, e.g. in Terminal,

     $ ./fb-rotate -d 0 -r 180

(You can rotate to the 0, 90 and 270 degree orientations as well.)


     fb-rotate -d <display ID> -r 0

will rotate the display with the indicated ID back to the standard orientation, e.g.

     $ ./fb-rotate -d 0x19156030 -r 0

(Again, you can also rotate to the 90, 180 and 270 degree orientations.)


Caveats
-------

Warning: Some white MacBooks, namely those using Intel's integrated graphics, have difficulty rotating 90º or 270º and the resulting display may be difficult to use. 


Credits and License 
-------------------

The original code for fb-rotate comes from a programming example in
the book **Mac OS X Internals: A Systems Approach** by Amit Singh (© 2006). The source is made available under the GNU General Public License (GPL). For more information, see the book's associated web site: [http://osxbook.com][osxbook]

[osxbook]: http://osxbook.com

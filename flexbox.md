lex box is
just a new CSS display type which is
designed to help us craft those CSS
layouts much much easier so basically it
lets us control the position of elements
the size of them and the spacing of them
relative to their parent container
elements and each other and it also
works great responsively too 

some of the benefits of using flexbox
are that we can create navigation bars
and menus really easily without having
to use floats or worrying about
polluting elements that we can also
create
read layouts really easily as well
things like bar charts and also equal
height columns plus all the stuff as
well now before I go any further it
would be wrong of me not to mention that
flexbox is not fully supported out of
the box in every single browser and
you're going to find that a lot of the
problems are in IE like this right here
and it tells you all these problems down
here so if you're going to use flexbox
then you want to provide for back
options for those browsers which don't
support it now one way we can do that is
by using
moderniser now moderniser is a really
cool javascript library and basically it
just detects which browser the user is
viewing your website on so say you're
using flexbox in your website now if a
user visits that on an IE browser which
doesn't support flexbox then moderniser
is going to say hey and no you don't
support this so add a class into the
body tag on your web page then we can
use that class to create specific styles
in our CSS for just that browser so I
just thought I'd warn you about that I'm
not going to be using moderniser in this
tutorial series I'm going to be using
Chrome which works pretty well with
flexbox as is I just wanted to kind of
include this in case you're using
Internet Explorer or some other browser
which does not fully support it


floexcontainers


his we
first have to create a container an
element with a display type of flex so
that every direct descendent element
within it then becomes a flex item so
once we've done that we can then control
the behavior of those flex items using
several flexbox CSS properties I applied
to the items themselves or the container
and that behavior includes things like
how they grow within the container I'll
have a shrink
relative to each other or whether they
stack on top of each other or side by
side and that kind of thing so there's a
lot of things we can do with them in


ach one of these
elements right here is going full width
and that's the default behavior right of
block level elements they take off the
full width of the available space
horizontally and these all block level
elements so that's why it's doing it
currently ok check out what happens when
I uncomment this and set the container
to fle


all of these are flex
items and this is the default behavior
of flex items they stack left to right
in a row like that okay and now that
these are Flex items we can do all kinds
of cool things with them to change how
they grow how they shrink we can add
space between them we can make them
stack on top of each other lots of
different things

flex-grow
does not depend on screen size


flex-shrink
bigge the number the more that it shrinks


flex-wrap: wrap
flex-wrap: wrap-reverse
flex-wrap: no-wrap default

flex-basis instead of the min-width

flex: 1 0 200px
grow shrink basis


flex:1
(basis = 0)



space around (even borders)
space between 






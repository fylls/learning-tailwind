``` HTML

<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <div>
    <div>
      <nav>
        <div>
          <h1>
            <a href="/">Food Ninja</a>
          </h1>
        </div>
        <ul>
          <li>
            <a href="#">
              <span>Home</span>
            </a>
          </li>
          <li>
            <a href="#">
              <span>About</span>
            </a>
          </li>
          <li>
            <a href="#">
              <span>Contact</span>
            </a>
          </li>
        </ul>
      </nav>
    </div>
  
    <main>
      <div>
        <a href="#">Log in</a>
        <a href="#">Sign up</a>
      </div>

      <header>
        <h2>Recipes</h2>
        <h3>For Ninjas</h3>
      </header>

      <div>
        <h4>Latest Recipes</h4>
  
        <div>
          <!-- cards go here -->
          <div> 
            <img src="img/stew.jpg" alt="stew">
            <div>
              <span>5 Bean Chili Stew</span>
              <span>Recipe by Mario</span>
            </div>
          </div>
        </div>

        <h4>Most Popular</h4>

        <div>
          <!-- cards go here -->
        </div>
      </div>

      <div>
        <div>Load more</div>
      </div>    
    </main>
  </div>

</body>
</html>

```

Class
Properties
text-xs	font-size: 0.75rem;
line-height: 1rem;

text-gray-800
text-6xl

font-bold
font-light

uppercase
lowercase


# margin paffng borders

.p-0
.p-4 (1rem)

.py-0 top and bottom

.p left and right

.pt
.pb
.pr
.pl

same for margin

.mt
.mb
.mr
.ml

.border-0
.border-8 (piel)

.border-t-8
.border-b-8
.border-r-8
.border-l-8

border-b-gray-200

# tailwind config file

 when tell when
processes our sauce CSS file it uses a
default configuration to do that under
the hood now this configuration dictates
the values of properties controlled by
different classes that we use in our
HTML


for example it would say that the
text - SM class would give a font size
of 0.875 Rams or text Excel would be a
font size of 1.25 rome's it would also
say things like the color red - 500
should be a specific hex code etc 

we
can also create our own Tailwind config
file to either extend those rules or add
extra classes for colors or fonts or
spacing or anything else or to change
the current ones as well 


hat this extra flag does
is create as a config file with all of
the default values that tailwind uses
under the hood included in it 


npx tailwindcss init --full

tailwind.config

if we wanted to we could change
these values right here and then if we
were to use that class it would change
how it looks
dependent on the value that we pass
through here because when we then use
tailwind to process our CSS it will look
for the values and match them up okay so
if we wanted to we could also add new
properties 


reprocess file base on new config


doesn't matter that there wasn't one
there before we never used to have this
config file when we don't have one it
just uses all of these default Styles
under the hood without this file even
being there but now we have one it's
gonna look for it and it's going to
apply all of these different values
including our new one s


npm run build-css


I wouldn't recommend changing values
inside the default config setup if you
do this it's hard to see what values
you've actually changed and what new
values you've added and therefore it's
going to be tough to distinguish between
the default values already there and
your own so instead we should create a
blank config file to extend the default
rules and that way we're not altering
the core values and it's easier to see
which extra values we've added ourselves
as well 


new blank config file

npx tailwindcss init

extend the themethat tailwind is using

```JAVASCRIPT
module.exports = {
  purge: [],
  darkMode: false, 
  theme: {
    extend: {
        colors:{
            primary: '#FF6363'
            secondary: {
                100: '#E2E2D5',
                200: '#888883',
            }
        }
    },
  },
  variants: {
    extend: {},
  },
  plugins: [],
}
```

now i can
class="text-primary"
class="bg-secondary-100 text-secondary-200"







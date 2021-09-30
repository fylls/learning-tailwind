## Base HTML

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

---

## Text & Font

```HTML
<tag class="class properties"></tag>
```

`.text-xs`	
`.text-gray-800`
`.text-6xl`

`.font-bold`
`.font-light`

`.uppercase`
`.lowercase`

---

## Margin, Padding  & Borders

**padding**

`.p-0`
`.p-4 `

top and bottom
`.py-10 `

left and right
`.px-10`

`.pt` - top
`.pb` - bottom
`.pr` - right
`.pl` - left

<br>

same for **margin**

`.mt` - top
`.mb` - bottom
`.mr` - right
`.ml` - left

<br>

**border**

`.border-0`
`.border-8 `

`.border-t-8`
`.border-b-8`
`.border-r-8`
`.border-l-8`

`border-b-gray-200`

---

## Tailwind Config File

when Tailwind processes our sauce CSS file it uses a default configuration to do that under the hood now this configuration dictate the values of properties controlled by different classes that we use in our HTML

for example it would say that the `text-sm` class would give a `font-size: 0.875ram` or `text-xl` would be a `font-size: 1.25ram` it would also say things like the color red -500 should be a specific hex code etc 

we can also create our own Tailwind config file to either extend those rules or add extra classes for colors or fonts or spacing or anything else or to change the current ones as well 

```bash
npx tailwindcss init
```

the created file will be called `tailwind.config.js`

---

## Tailwind FULL Config File

this extra flag creates a config file with all of the default values that tailwind uses under the hood included in it 

```bash
npx tailwindcss init --full
```

if we wanted to we could change these values right here and then if we were to use that class it would change how it looks dependent on the value that we pass through here because when we then use tailwind to process our CSS it will look for the values and match them up okay so if we wanted to we could also add new properties 

"reprocess file base on new config"

doesn't matter that there wasn't one there before we never used to have this config file when we don't have one it just uses all of these default Styles under the hood without this file even being there but now we have one it's gonna look for it and it's going to apply all of these different values including our new one

```bash
npm run build-css
```

I wouldn't recommend changing values inside the default config setup if you do this it's hard to see what values you've actually changed and what new values you've added and therefore it's going to be tough to distinguish between the default values already there and your own so instead we should create a blank config file to extend the default rules and that way we're not altering the core values and it's easier to see which extra values we've added ourselves as well 

run this command for a blank config file
```bash
npx tailwindcss init
```

---

## Example of "tailwind.config.js"

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

now i can type this in my HTML and it will be translated correctly, also the helper for VScode will suggest our own custom styles.

```HTML
<div class="text-primary">
<div class="bg-secondary-100 text-secondary-200">
```

---

## Flexbox

flexbox is just a new CSS display type which is designed to help us craft those CSS layouts much much easier so basically i lets us control the position of elements the size of them and the spacing of them relative to their parent container elements and each other and it also works great responsively too. Some of the benefits of using flexbox are that we can create navigation bars and menus really easily without having to use floats or worrying about polluting elements 

would be wrong of me not to mention that flexbox is not fully supported out of the box in every single browser and you're going to find that a lot of the problems are in IE like this right here and it tells you all these problems down here so if you're going to use flexbox then you want to provide for back options for those browsers which don't support it now one way we can do that is by using `moderniser`.

`moderniser` is a really cool javascript library and basically it just detects which browser the user is viewing your website on so say you're using flexbox in your website now if a user visits that on an IE browser which doesn't support flexbox then moderniser is going to say hey and no you don't support this so add a class into the body tag on your web page then we can use that class to create specific styles in our CSS for just that browser so I just thought I'd warn you about that I'm not going to be using moderniser in this tutorial series I'm going to be using Chrome which works pretty well with flexbox as is I just wanted to kind of include this in case you're using Internet Explorer or some other browser which does not fully support it.

---

flex-item (child) & flex-container (parent)

```HTML
<div class="flex justify-end">
    <p>text1</p>
    <p class="ml-2" >text2</p>
</div>
```

`flex justify-center`
`flex justify-start`
`flex justify-end`
`flex justify-between`
`flex justify-around`
`flex justify-evenly`

`h-4 w-6`

h = height
w = width

---

## Flexbox Example #1

blocks stack one on top of one another

```HTML
<div class="">
    <div class="bg-red-500 h-4 w-6"></div>
    <div class="bg-blue-500 h-8 w-6"></div>
    <div class="bg-gree-500 h-12 w-6"></div>
</div>
```

---

## Flexbox Example #2

block all stacked horizontally - aligned to the start of the component
(they sit next to each other)

```HTML
<div class="flex">
    <div class="bg-red-500 h-4 w-6"></div>
    <div class="bg-blue-500 h-8 w-6"></div>
    <div class="bg-gree-500 h-12 w-6"></div>
</div>
```

align on X - `item-start` `item-end` `item-center` 

align on Y - `justify-center` 


---

## Media Queries & Responsive Design

media queries in Tailwind?

normally when we're creating mobile designs we'd use media queries in our CSS file to style things differently at different screen sizes.

in tailwind we don't have to manually create any media queries at all, we can just prefix our tailwind classes with responsive classes and then that class would only apply to that screen size and up.

now the responsive classes are these right here SM MD LG and XL, so if we prefix a class with SM: it means okay only target things from small screens and up if we prefix it with MD: only target that class from medium-sized
screens and up now all of these breakpoints that they use are `min-width` which means this is a `mobile first approach` so by default all classes that you apply to an element will apply at all widths including the smallest screen sizes but then when we prefix them with one of these things right here then those classes would only apply for that device width and up

`text-green-500 sm:text-red-500  lg: text-blue-500`

`flex justify-center md:justify-end`

---

## Cards

custom card component

`rounded overflow-hidden shadow-md`

`w-full` fully contain width of its parent, no overflow
`object-cover`  take out image distortion, image zooms in if w changes (tablink)

```HTML

<div class="rounded bg-white border-gray-200 shadow-md overflow-hidden"> 
    <img src="img/stew.jpg" alt="stew" class="h-32 sm:h-48 w-full object-cover">
    <div class="m-4">
        <span class="font-bold">5 Bean Chili Stew</span>
            <span class="block text-gray-500 text-sm">Recipe by Mario</span>
        </div>
    </div>
</div>#

```

that is some ugly HTML uh?

---

## Badges

`bg-secondaty-100 text-secondaty-200 text-xs uppercase font-bold rounded-full`

position at the top? position: absolute

`relative` in parent
`absolute` in child

```HTML
<div class="mt-8">
    <div class="rounded bg-white border-gray-200 shadow-md overflow-hidden relative"> 
        <img src="img/stew.jpg" alt="stew" class="h-32 sm:h-48 w-full object-cover">
        <div class="m-4">
            <span class="font-bold">5 Bean Chili Stew</span>
            <span class="block text-gray-500 text-sm">Recipe by Mario</span>
        </div>
        <div class="absolute top-0 ml-2 mt-2 p-2 bg-secondary-100 text-secondary-200 text-xs uppercase font-bold rounded-full">
        <span>25 mins</span>
        </div>
    </div>
</div>
```

---

## @apply directive

if we wanted to make multiple cards or multiple budgets, we'd have to use all of these classes on each one we created now imagine as well if we wanted to change the style of a card then we'd have to change it in every place that we have a card and the same would be true for badges, so that's not a great idea and it's also looking a bit messy as well

would be nice if we could extract these different classes into an external selector using some nifty tailoring syntax and we can do.

so all I need to do now is give this a class of card and we have a reusable component which we only have to update over here and not in every place we create a card now that's a bit better and it's also much tidier - it becomes much more reusable

```CSS
@import url('https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,200;0,300;0,400;0,600;0,700;0,800;0,900;1,200;1,300;1,400;1,600;1,700;1,800;1,900&display=swap');

@tailwind base;
@tailwind components;
@tailwind utilities;

.card{
  @apply rounded bg-white border-gray-200 shadow-md overflow-hidden relative;
}

.badge{
  @apply absolute top-0 ml-2 p-2 mt-2 bg-secondary-100 text-secondary-200 text-xs uppercase font-bold rounded-full;
}

```

<br>

so now we can write the components like this

```HTML
<div class="card hover:shadow-lg"> 

    <img src="img/stew.jpg" alt="stew" class="h-32 sm:h-48 w-full object-cover">
    
    <div class="m-4">
        <span class="font-bold">5 Bean Chili Stew</span>
        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
    </div>

    <div class="badge">
        <object data="clock.svg" type="image/svg+xml"></object>
        <span>25 mins</span>
    </div>

</div>
```

---

## Miscellaneous

**grid**

parent
 `grid grid-col-3 gap-10`

child
`col-span-1`
`col-span-2`

<br>

**button**

```CSS
.btn{
  @apply rounded-full py-2 px-3 uppercase text-xs font-bold tracking-wider cursor-pointer;
}
```

<br>

**icons**

tailwind itself doesn't actually come with any icons built into it we have to use some kind of external library or your own SVG's you can use whichever you prefer.

<br>

**hover**

`hover:` only for hovering apply this
`md:` only for medium sceens and up apply this

**shadow**

`shadow-inner`

```HTML
<div class="flex justify-center md:justify-end">
    <a href="#" class="btn text-primary border-primary md:border-2 hover:bg-primary hover:text-white">Log in</a>
    <a href="#" class="btn text-primary ml-2 border-primary md:border-2 hover:bg-primary hover:text-white">Sign up</a>
</div>
```


**nav**

`cursor-pointer`
`md:hidden`

`flex justify-between item-center`

<br>

**hidden for small screes**

`hidden md:block`

<br>

**transitions**

(from initial to hover state) -  what kind of easing function do yu want to use?

`transition ease-out durration-500`
`transform hover:scale-125 hover:ng-opacity-50 transition ease-out durtation-300`
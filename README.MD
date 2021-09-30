
![0_AVzIJzp8ecO-wfjO](https://user-images.githubusercontent.com/55017307/135221317-95dfa98a-9b3d-4d69-b6b4-e3349d7a8562.jpg)

# What?

tailwind is a massive collection of tiny css utility classes for quickly and consistently building good-looking websites

it is hard to design with CSS, naming your css classes in a sane way is virtually impossible.

frameworks like `bootstrap` and `materialUI` address this challenge by creating styles for high level components things like buttons drop downs and forms, `tailwind` takes a more functional approach by providing you with utility classes that can be composed together to build components.

instead of using the "card class" like you might in bootstrap you combine utility classes like flex to make it a flexbox p to give it padding m for margin and hundreds of others to control things like color shadows and so on

## Conditional CSS

sm: lg: hover: dark: focus:

allowing the rules of a design system that you don't get with plain css, it lives in the sweet spot between convention and configuration, however it does produce some ugly HTML.

another concern you may have is performance because tailwind weighs in at over 3 500 kilobytes but when you go to build for production it will automatically purge any unused utility from the final bundle resulting in minimal dead code and thus faster page loads

but who has time to learn and memorize all these different utility classes where tailwind really shines is with its tooling you don't need to memorize much because vs code will auto-complete every tailwind class. if you're not sure what it does just hover over it and it will show you the equivalent code in plain css and if you're not happy with what it does you can easily customize everything from the color palette to the spacing to build your own unique design 

---

framework packed with utility classes 

I guess you could say it's a bit like bootstrap or materialize CSS but it's also very different as well because whereas bootstrap and materialize and all the CSS frameworks give you fully styled components like cards buttons dropdowns and all that kind of just right out-of-the-box, tailwind doesn't do that.

it's much more low-level and it gives you a ton of low-level utility classes to make your own components instead

```HTML
<--card--!>
<div class="rounded shadow p-2 bg-white"></div>
```


so we kind of make these components ourselves based on these low-level utility classes but I hear you say "doesn't that mean more work and isn't something like bootstrap then easier"?

well yes and no.

you can easily make your own reusable components in tailwind so it's really not that much extra work to be honest and aside from that it also gives you a lot more flexibility than bootstrap and any other frameworks do as well and it allows you to customize your designs in a more unique way, so whereas you can generally look at a bootstrap website and you can tell it's made with bootstrap or maybe look at a materialize website and you can tell it's made with materialize, you can't really do that with tailwind because it's just made up of these types alone of all utility classes and it doesn't really have a set look or feel.

It is down to you so it's much less assuming that other frameworks as to how you want your page designs to look 

---

## Installation & Setup

```bash
npm install tailwindcss
```

so when we use tailwind we create a source file where we import all of the tailwind core styles and functionality and then we can also write our own CSS if we want to (but it is no recommended)

Then we use tailwind to process that source file into a vanilla CSS output file at Build time with all of the final CSS rules inside it and then we can link to that CSS from our HTML page.

so then every time we make some kind of change to this sauce CSS file we'd have to run a tailwind script to process that into a new output CSS file now that might seem arduous but the good thing is is that with tailwind we mainly use utility classes inside the HTML file itself so we only rarely have to change the source file the sauce CSS and then reprocess it into the output file

---

`src/styles.css` - here you can put your own tailwind config

```CSS
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---


`index.html` link your HTML & CSS

```HTML
  <link rel="stylesheet" href="styles.css">
```

---

`package.json` - create this new script to build your CSS

```JSON
  "scripts": {
    "build-css": "tailwindcss build src/styles.css -o public/styles.css"
  },
```

---

`command line` - run this to build your CSS

```bash
npm run build-css
```

---
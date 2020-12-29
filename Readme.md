### Getting Started with Tailwindcss

CSS technology was one of the biggest game changers in web development. It allowed for more styling capabilities and freedoms. As CSS grew, so did it's difficulty. CSS in retrospect is not difficult in terms of usage, but can be difficult in terms of implementation.

The next phase in CSS was development of libraries and frameworks. These libraries and frameworks had different problems to solve, but mostly and commonly the repetition, modularization and complexity of writing css. One of the most famous examples of css frameworks is bootstrap by twitter.

The CSS frameworks like Boostrap however have one major disadvantage that came about from increased growth and usage. They became too big and offered less control over the styles. The learning path became hard since the developer has to learn hundreds of classes that are pre-written.

### What is Tailwindcss

Tailwindcss is also a CSS framework created by [Adam Wathan](https://twitter.com/adamwathan). Unlike other frameworks, it does not come prebuilt with classes that you can just add to the HTML tags and apply styling instantly. Instead it uses a different approach. It brings a much lower level of control by using utility-based classes.

### Installation

Let's get right into it and install tailwind so we can discover more about it. There are two ways to install tailwind css depending on the use case.

<!-- Also include postcss and why it is important -->

#### Method 1: Using CDN

Using a CDN is the most common way of using any CSS frameworks and tailwind is no exception. A CDN is a link to the tailwind files that is put in the Head section of the HTML page.

Create a HTML file and name it anything. We will name ours `index.html`. Inside it, Write the boilerplate code for HTML and add the CDN as shown below:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Section Tailwind Demo</title>
    <link
      href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css"
      rel="stylesheet"
    />
  </head>
  <body></body>
</html>
```

And just like that, we have installed tailwind into our project.
Note: This might not be the best way to install Tailwind into your project because it has a few setbacks like:

- You cannot add any third-party plugins
- Since Tailwind files are downloaded when the file loads, you cannot purge unused files
- You cannot configure some configurations like the theme

#### Method 2: Using npm

This method is highly adviced and prefered because it bestows the full freedom of tailwind on the developer. It is also common because all Javascript frameworks use a similar approach to install tailwind, with minimal differences depending on the framework architecture.

Let's get started. First, let's create a directory we will be working from. Within the folder, initialize npm. In your terminal, run

```terminal
mkdir section-tailwind-demo && cd section-tailwind-demo

npm init -y // to initialize npm with everything set to true or yes
```

Now let's install tailwindcss. We need a few things alongside tailwindcss. We need a preprocessor because tailwind relies on a prepocessor. Tailwind uses a postcss plugin called autoprefixer to transpile the css into vanilla css.

In the terminal run :

```terminal
npm install tailwindcss@latest postcss@latest autoprefixer@latest
```

the command above will install all the dependencies we need. Next we have to create script for tailwind and postcss to tell configure them. To generate the scripts we make use of the tailwind CSS utility provided by tailwindcss.

In the terminal run :

```terminal
npx tailwind init -p
```

It will generate two files, `tailwind.config.js` and `postcss.config.js`.
The tailwind.config.js looks like this:

```js
module.exports = {
  purge: [],
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {
    extend: {},
  },
  plugins: [],
};
```

and the postcss.config.js should look like this:

```js
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};
```

We set up the environment, now let's setup tailwind in our project.

Lets create 2 files. A html page called `index.html` and a stylesheet called `style.css`.

The html part can have the basic boilerplate syntax for html. In the CSS file, we need to tell autoprefixer that we will use tailwind. We do this by importing the tailwind files as shown below:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Finally, we need to build our tailwindcss, so in the terminal run:

```js
npx tailwindcss-cli@latest build -o css/tailwind.css
```

This command will create a tailwind.css file in a css folder. We then need to add our tailwind file to the html like we would a normal css file.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="css/tailwind.css">
</head>
<body>
    
</body>
</html>

```

And just like that we have everything set up.

### Working with Utility Classes

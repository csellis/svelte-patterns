# Svelte Patterns

Your favorite patterns for building in Svelte.

## Please contribute

What we're looking for here is to share some of your favorite patterns with Svelte.

Hoping to get some help finishing out this site as well.

## How you can help

1. Contribute your favorite patterns in Svelte with code examples
2. Help build out this site

### How to change the code editor theme

The syntax highlighting is powered by [PrismJS](https://github.com/PrismJS) under the hood, and this project comes with a default theme of Visual Studio Code Dark+ by [tabuckner](https://github.com/tabuckner).

You can find an availble list of PrismJS themes [here on GitHub.](https://github.com/PrismJS/prism-themes)

In order to change the syntax highlighting theme for the project, just follow these steps.

1. Go to the [PrismJS themes repo](https://github.com/PrismJS/prism-themes) and select the theme you want.
2. Click on the name of the theme you wnat to use.
3. Now that you are on the page showing the CSS for the theme, go ahead and click the "Raw" button.
4. Now press `Cmd + A` or `Ctrl + A` to select all, and then press `Cmd + C` or `Ctrl + C` to copy all of the CSS.
5. Create a new CSS file in the `~/static/prism-theme` folder, and name it whatever you would like.
6. Using `Cmd/Ctrl + V` paste in the copied CSS of the Prism theme.
7. Save the file.
8. Open the file `~/src/app.html` and edit the `<link>` tag on line 6 so that it matches the name of your CSS file in the `~/static/prism-theme` folder. Then save the file.

You should not have to restart the development server, the theme should just be updated client side.

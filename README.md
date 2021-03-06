# Lithials' React Webpack Template

I created this repo to learn more about how webpack works and to have a template that I can use in future projects.

## TODO:

- ~~Integrate eslint, prettier~~.
- ~~Staged linting~~
- ~~Build create component scripts and templates. or snippets.~~
- ~~make new sass files start with \_ and import them into the index.scss~~
- ~~Storybook setup~~
- Integrate testing, ~~jest~~, cypress (storyshots, loki, sinon).
- Create a branch for react native.
- ~~Investigate why to use css variables over sass ones. (inconclusive)~~
- Investigate React Sass best practices.
- See if bem is right for react.
- Look into asset loading for lazy images like gatsby has.

## How to use:

1. Clone the repo.
2. Select the branch to determine which template you want to use.
3. Run Yarn to install dependencies.
4. See the package.json for available scripts.

### Staged-linting

This repo uses husky and lint-staged to do a lint and format on commit.

If you have trouble getting this to work with your IDE on WSL,
make sure your IDE is using the WSL node and not the Windows node.

## Resources:

Based on this [Youtube Video](https://youtu.be/TOb1c39m64A), with more information found on [GitHub](https://github.com/Jimmydalecleveland/webpack-starters/tree/react-full-project-latest)

## Features

- Built with yarn.
- Auto staged linting and formatting on commit.
- Component creation script with templating. Now adds new components to the right files automatically. (index.js/scss)
- (Fast) Hot and Live Reloading.
- Latest stable ES version transpiling through @babel/preset-env and babel-loader.
- JSX syntax through @babel/preset-react and babel-loader.
- .jsx file extensions, and importing them without adding the extension.
- importing .css files into javascript files through css-loader.
- Sass: .scss and .sass formats through sass-loader and dart sass (sass) package.
- importing images (including .svg) through import syntax in javascript and url() syntax in css.
- automatically inlining images less than 8kb (webpack default, which is configurable) into the javascript bundle output. Anything over 8kb will be created as a resource file in the final output folder.
- html-webpack-plugin@next for outputting an index.html from a template for proper production builds support.
- clean-webpack-plugin for automatic cleanup of the output directory (dist/) on each build.
- Built in storybook with the addons for accessibility, linking and measuring.
- Testing with Jest.

### Useful tips and tricks

`// @refresh reset` at the top of the file will stop fast refresh from keeping state on that component

Running `yarn gc {name}` will create all the appropriate scripts with good templates in the src/components folder. Files include
component.jsx, component.stories.jsx, component.test.jsx, component.scss, index.js

## Thoughts on Testing:

### Visual Regression Testing

For this, chromatic with storybook seems super useful, thought it does look to cost money after 5000 snapshots a month.
It seems that the hosting and approval system could be useful for checking design changes for components depending on the size of the project.

### Accessibility Testing

This can be done with the a11y plugin on storybook. It will catch the most blatant of WCAG issues and other best practices.
This can be further automated with Jest using these [instructions.](https://storybook.js.org/docs/react/writing-tests/accessibility-testing).

### Interactions Testing

This can be done using the interactions addon for storybook with instructions found [here.](https://storybook.js.org/docs/react/writing-tests/interaction-testing)

### Unit Testing

Unit tests can be written for hooks and functions using React testing library, React

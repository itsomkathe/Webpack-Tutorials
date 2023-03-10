<p align="center">
    <img src="./public/static/webpack.svg" width="50px"/>
</p>
<div align="center">
  <h3 align="center">Webpack Basics</h3>

  <p align="center">
    Playing with webpack 5 loaders, source-maps, dev server
    <br />
    <a href="https://webpack.js.org/configuration/dev-server/#devserverstatic" target="_blank" ><strong>Webpack Docs ↗</strong></a>
    <br />
    <br />
  </p>
</div>

<summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#getting-started">Development and Production Mode</a>
      <ul>
        <li><a href="#dependencies">Dependencies</a></li>
        <li><a href="#development">Development</a></li>
        <li><a href="#production">Production</a></li>
      </ul>
    </li>
    <li>
      <a href="#entry-and-output">Entry and Output</a>
      <ul>
        <li><a href="#entry">Entry</a></li>
        <li><a href="#output">Output</a></li>
      </ul>
    </li>
    <li><a href="#development-server">Development Server</a></li>
    <li><a href="#babel-config">Babel Config</a></li>
  </ol>

<br/>

## Development and Production Mode

Set up different builds for dev and prod at different locations. 

**webpack.config.js**

    const mode = process.env.NODE_ENV === 'production' ? 'production' : 'development';

    module.exports = {
        mode: mode
    }

### Dependencies

Script for setting up NODE_ENV in package.json is different in Windows and Unix based systems. 
Use the <a href="https://www.npmjs.com/package/cross-env" target="_blank">cross-env</a> package as a dev dependency to run the project on muliple platforms.

### Development

Run the command to generate a development build in the *dist* folder. 

    npm run build-dev

### Production

Run the command to generate a production build in the *public/build* folder. 

    npm run build

## Entry and Output

### Entry

Entry is the point from which the webpack starts making it's dependency graph for the bundle. *index.js* is the entry point. There can be multiple entry points, used in features like code splitting.

### Output

Output is the minified file generated by webpack. The development build is *main.js* located at */dist*. The production build is *bundle.js* located at */public/build*.

## Development Server

Webpack provides a local dev server. *static* specifies the directory which should be served. Use the follwing commands to run dev server

    npm run webpack serve
or

    npm start

### Hot Reloading

Watch mode is used for hot-reloading. In dev server watch mode is endabled by default.

### Source Maps

Source maps are used in dev server for debugging, where we get actual file location while inspecting in browser.

    devtool: 'source-map'

## Babel Config

Configure babel transpiler to get modern JavaScript working with older browsers.

> Note: Newer methods of ES versions are not transpiled by babel. To support them, polyfills need to be set up.

<br/>
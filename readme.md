# Spring Boot w/ SASS Demo

Demo project incorporating sass/scss in a spring boot application.

## Setup

1. Initialize the npm project `npm init -y`

    Make sure to add `node_modules` to your `.gitignore`.
   
2. Add `node-sass` (or whatever you prefer)

    ```
    npm install node-sass
    ```

3. Make a scss source file in `src/main/scss/index.scss`
   
4. Configure a build command to output to `src/main/resources/static`

    Within `package.json`

    ```json
    ...
    "scss:build": "node-sass src/main/scss/index.scss -o src/main/resources/static"
    ...
    ```

    You may also wish to setup a `watch` command for development
   
    ```json
    ...
    "scss:watch": "node-sass -w src/main/scss/index.scss -o src/main/resources/static"
    ...
    ```

## Usage

- Pre-commit/deployment

    ```
    npm run scss:build
    ```

- During development

    ```
    npm run scss:watch
    ``` 
  
    And the index.css file will be rebuilt as you make changes to `src/main/scss/index.scss`.

## Notes

We are assuming you are committing the css artifacts, i.e. you `git add` and `git commit` `src/main/resources/static/index.css`.

A more complex way to do this might be to ignore the build css and build the css as part of the spring boot application's build process using something like the [frontend-maven-plugin](https://github.com/eirslett/frontend-maven-plugin).

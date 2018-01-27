# TypeScript Learning Project


# Introduction

I'm using this project to figure out best practices for developing TypeScript project.
My background is a Java Server Side developer with some front-end experience.

# PreReq: TypeScript using JavaScript tooling: Node

* Install node and npm from [https://nodejs.org/en/download/]



# Beginning a Node Project.

* Create a empty directory for your project.
* ``git init``
* Write a [README.md](https://medium.com/@meakaakka/a-beginners-guide-to-writing-a-kickass-readme-7ac01da88ab3)
* Initialize your node project by creating a [package.json-file](https://docs.npmjs.com/getting-started/using-a-package.json).
** ``npm init``


# Making it a TypeScript project

You should add typescript as a devDependency in your project.
You can do this manuall in the `package.json`-file or use the following command line command:

* ``npm install typescript --save-dev``

The ``--save-dev`` option indicates this dependency is only using at build time and not a runtime, so it should not
become part of the final build product.

This command updates the package.json file and downloads the module into the `node_modules`-directory.
It's is kind of a local repository and it should NOT be part of the git repository, so add 'node_modules/' to the .gitignore of your project.
The `npm install` command alo generate or updates the package-lock.json, which contains all information about the 
resolved dependency tree with fixed versions. It will identify how a version of the project was build at any point in time and should be added to the git repository


# Preparing for Unit testing: devDependencies and config

## Install mocha chai ts-node and the types

Since TypeScript is a superset of JavaScript, we can use JavaScript tooling, for instance mocha and chai.
For those tools the '@types' have been develop, so that TypeScript and IDE's can understand those frameworks properly.

All of this does have to be added to the project.

```npm install chai mocha ts-node @types/chai @types/mocha --save-dev```

## Configure npm to use mocha when we execute `npm test`

In a Node-project running the Unit tests can be done by running `npm test` from the command line / in a terminal. 
Your project does need to be configured in such a way that it will use mocha with typescript to run all `*.spec.ts`-file from your project.

Therefor make sure the test-script in your package.json takes care of this:

```
"scripts": {
        "test": "mocha --require ts-node/register src/**/**.spec.ts"
    }
```

# Directory structure

Of course you should use package-by-feature, so underneath `/src/` you will create directories for each component.
For now I will add the `.spec.ts` next to the component.ts-files

```
/src
    /hello-world
        /hello-world.ts
        /hello-world.spec.ts
```






# References

1. [Unit testing node applications with TypeScript — using mocha and chai](https://journal.artfuldev.com/unit-testing-node-applications-with-typescript-using-mocha-and-chai-384ef05f32b2)




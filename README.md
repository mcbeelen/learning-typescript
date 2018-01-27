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



# Some more devDependencies for testing


```npm install chai mocha ts-node @types/chai @types/mocha --save-dev```


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

# [https://journal.artfuldev.com/unit-testing-node-applications-with-typescript-using-mocha-and-chai-384ef05f32b2]




# Solidok: Documentation Generator for Solidity

This command-line utility creates markdown-based documentation for your Solidity project(s) for the following platforms:

* Ethereum
* Ethereum Classic
* Tron
* Qtum
* Wanchain
* Aeternity
* Counterparty
* Rootstock
* Ubiq
* Monax

Supports Solidity up to 0.7.
Able to also generate docs for events and state variables with tags like `@notice`, `@dev` and `@param`.
## Getting Started

**Global instalation**

```npm
yarn global add solidok
```
Make sure your `yarn/global/.bin` is exported to PATH.

**Project instalation**

```npm
yarn add solidok --dev
```


**CLI Arguments**

1. Path to Truffle project (or similar) root.
2. Path to generate documentation to.
3. Do not recompile. Optional, default: false.
4. Compiler. Truffle compiler (use `npx truffle compiler` to use the same compiler as the project, instead of global install of Truffle).
5. Language. Optional, default: en.
6. Version. Optional, refers to contracts version (depends on the project).
7. Ignore files. Optional, array with filenames to ignore.

Using a [configuration file](#configuration-file) is recommended (mostly if you want to ignore files).


**Usage**

In your project root, run the following commands based on your setup:

If installed globally:
```npm
solidok ./ ./docs true
```

If you have a `solidok.json` file set up, just run:
```npm
solidok
```

If installed to project:
```npm
node node_modules/.bin/solidok
```


This will generate documentation to the `docs` directory.

**Or edit package.json**

```json
  "scripts": {
    "docgen": "solidok ./ ./docs"
  }
```

and run:

```npm
yarn docgen
```

**Note**

Do not use recompilation (third argument) if you are using this on a non Truffle project.

## Configuration File

Alternatively, you can create `solidok.json` configuration file in your project root:

```json
{
  "pathToRoot": "./",
  "outputPath": "./docs",
  "noCompilation": true,
  "compiler": "truffle compile",
  "language": "en",
  "version": "0.1.10",
  "ignoreFiles": []
}
```

and then call `solidok` instead of passing any command line argument.


## Overrides

If you wish to change bits and pieces of the documentation generated, place `solidok templates` on the following directory:

`./.solidok/templates/`

[solidok Templates](templates)


You can also override language literals by copying and editing `i18n` files on the following path:

`./.solidok/i18n/`



## Before You Try

- [OpenZeppelin Solidity Documentation](https://github.com/binodnp/openzeppelin-solidity/blob/master/docs/ERC721.md)
- [Open Source Vesting Schedule by Binod](https://github.com/binodnp/vesting-schedule/blob/master/docs/VestingSchedule.md)
- [Virtual Rehab Token](https://github.com/ViRehab/VirtualRehabToken/blob/master/docs/VRHToken.md)
- [Virtual Rehab Private Sale](https://github.com/ViRehab/VirtualRehabPrivateSale/blob/master/docs/PrivateSale.md)

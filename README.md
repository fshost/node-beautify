# Node-Beautify

Node-Beautify is a node.js module that can be easily required and used to beautify assets from within a Node.js script. It is not meant to be a command-line tool, there are plenty of existing tools for that. The purpose of Node-Beautify is for javascript based build scripts or the like that want to be able to 'require' a beautifier module.  Currently it only supports javascript.  The original intent was to encapsulate additional syntax support, such as css.  I may still do that at some point, but if you would like to add another formatting parser in the meantime, feel free to fork this repo and send a pull request.

## Installation

    npm install node-beautify

## Usage

to beautify javascript:

        require('node-beautify').beautifyJs(source, options);
        
where
    source is a string of javascript source code and options (optional) allows overriding the defaults (see below)

## Default Options 

- indentSize            : 4
- indentChar            : ' ' (space character)
- preserveNewlines      : true
- bracesOnOwnLine       : false
- keepArrayIndentation  : false
- spaceAfterAnonFunction: true
- indentLevel           : 0


## Example
    // require the module
    var nb = require('node-beautify');

    // pass a string of ugly javascript to the beautifyJs method
    var prettyJs = nb.beautifyJs("function test(){console.log('test');}");

    // the results should be a nicely formatted javascript string
    console.log(prettyJs);

## To run tests
Mocha should be installed globally.  If it is not, you can install it by typing

    npm install mocha -g

Clone the repository using git, e.g.

    git clone https://github.com/fshost/node-beautify
    
After the repo has been cloned, in the repo directory type

    npm install

After all dependencies are installed, the tests can be run by typing
    
    mocha

## Requirements

* node.js


## Acknowledgements

The original [JS Beautifier](http://github.com/einars/js-beautify) is written by [Einar Lielmanis](mailto:einar@jsbeautifier.org).


## License

MIT-License, see `LICENSE.txt`.

## Roadmap

- Add support for other asset types
- Integrate into Node Build Tool

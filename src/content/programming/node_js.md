#Node js

##Setup

The best way to install node is through homebrew
`brew install`

Make sure that 
```
export NODE_PATH="/usr/local/lib/node"
export PATH="/usr/local/share/npm/bin:$PATH"
```


####Where is Node installed
`npm root` shows where modules are installed
`npm root -g`

`npm config set prefix /usr/local` this allows you to change your root of global Npm packages



##NPM 
The Node Package manager allows you to easily manage modules in projects

####Local Install
Instal a package locally if you are going to `require()` it for a specific project

Installing a module automatically creates a `node_modules` folder in the present directory

####Global Install
Install globally if you need it on the command line

Install a package globally by `npm install -g <module_name>` installs the module in `/usr/local` or wherever node is installed

##Express



- **Node Package Manager**
- `npm` is the standard package manager for Node.js
- `npm` manages downloads of dependencies of your project.
- If a project has `package.json` file, by running 
```bash
  npm install
```

it will install everything the project needs, in the `node_modules` folder, creating it if it's not existing already

- You can also install specify package by running
```bash
npm install <package-name>
```

Often you'll see more flags added to this command:

- `--save-dev` installs and adds the entry to the `package.json` file`devDependencies`
- `--no-save` installs but does not add the entry to the `package.json` file `dependencies`
- `--save-optional` installs and adds the entry to the `package.json` file `optionalDependencies`
- `--no-optional` will prevent optional dependencies from being installed

Shorthand's of the flags can also be used:

- -S: `--save`
- -D: `--save-dev`
- -O: `--save-optional`

Updating packages is made easy by running 
```bash
npm update
```

`npm` can also manage **versioning**, so you can specify the version of a package
```bash
npm install <package-name>@version
```

For running tasks
```bash
npm run <task-name>
```
will run any task that is specified in the `package.json` file
```JSON
{
	"script":{
		"start-dev": "node lib/server-developement",
		"start": "node lib/server-production"
	}
}
```

so instead of typing those commands all we have to do is write
```bash
npm run start-dev
```

When using `bun install` on a local registry (verdaccio) some packages are not being downloaded/extracted correctly. This however is not the case when using another package manager. 

```
$ bun install
$ bun run start

$ NPM_CONFIG_REGISTRY=http://localhost:4444 bun install --no-save @schematics/angular
$ tree node_modules/@schematics/angular -L 1

node_modules/@schematics/angular
├── application
├── app-shell
├── files
├── LICENSE
└── README.md

4 directories, 2 files


$ NPM_CONFIG_REGISTRY=http://localhost:4444 npm install --no-save @schematics/angular
$ tree node_modules/@schematics/angular -L 1

node_modules/@schematics/angular
├── application
├── app-shell
├── class
├── collection.json
├── component
├── config
├── directive
├── e2e
├── enum
├── environments
├── guard
├── interceptor
├── interface
├── library
├── LICENSE
├── migrations
├── module
├── ng-new
├── package.json
├── pipe
├── README.md
├── resolver
├── server
├── service
├── service-worker
├── ssr
├── third_party
├── utility
├── web-worker
└── workspace

27 directories, 4 files
```

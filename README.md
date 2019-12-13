# README

Repo to reproduce a bug in `yarn PNP`.

## steps to reproduce

Just clone this repo to a path containing a space (in my case `/Users/%user%/Documents/Path with space/code/`) and try to run `yarn node index.js`.

It will fail with an error showing that having a space in the path is breaking execution:

```bash
| $ yarn node index
internal/modules/cjs/loader.js:797
    throw err;
    ^

Error: Cannot find module '/Users/%user%/Documents/Path'
Require stack:
- internal/preload
    at Function.Module._resolveFilename (internal/modules/cjs/loader.js:794:15)
    at Function.Module._load (internal/modules/cjs/loader.js:687:27)
    at Module.require (internal/modules/cjs/loader.js:849:19)
    at Module._preloadModules (internal/modules/cjs/loader.js:1125:12)
    at loadPreloadModules (internal/bootstrap/pre_execution.js:443:5)
    at prepareMainThreadExecution (internal/bootstrap/pre_execution.js:62:3)
    at internal/main/run_main_module.js:7:1 {
  code: 'MODULE_NOT_FOUND',
  requireStack: [ 'internal/preload' ]
}
```
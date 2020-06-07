salesforcecodex-dx-plugin
========

Salesforce Codex DX Plugin for generating Apex template code.

[![Version](https://img.shields.io/npm/v/salesforcecodex-dx-plugin.svg)](https://npmjs.org/package/salesforcecodex-dx-plugin)
[![CircleCI](https://circleci.com/gh/52000290/salesforcecodex-dx-plugin/tree/master.svg?style=shield)](https://circleci.com/gh/52000290/salesforcecodex-dx-plugin/tree/master)
[![Appveyor CI](https://ci.appveyor.com/api/projects/status/github/52000290/salesforcecodex-dx-plugin?branch=master&svg=true)](https://ci.appveyor.com/project/heroku/salesforcecodex-dx-plugin/branch/master)
[![Codecov](https://codecov.io/gh/52000290/salesforcecodex-dx-plugin/branch/master/graph/badge.svg)](https://codecov.io/gh/52000290/salesforcecodex-dx-plugin)
[![Greenkeeper](https://badges.greenkeeper.io/52000290/salesforcecodex-dx-plugin.svg)](https://greenkeeper.io/)
[![Known Vulnerabilities](https://snyk.io/test/github/52000290/salesforcecodex-dx-plugin/badge.svg)](https://snyk.io/test/github/52000290/salesforcecodex-dx-plugin)
[![Downloads/week](https://img.shields.io/npm/dw/salesforcecodex-dx-plugin.svg)](https://npmjs.org/package/salesforcecodex-dx-plugin)
[![License](https://img.shields.io/npm/l/salesforcecodex-dx-plugin.svg)](https://github.com/52000290/salesforcecodex-dx-plugin/blob/master/package.json)

<!-- toc -->
* [Debugging your plugin](#debugging-your-plugin)
<!-- tocstop -->
<!-- install -->
<!-- usage -->
```sh-session
$ npm install -g salesforcecodex-dx-plugin
$ sfdx COMMAND
running command...
$ sfdx (-v|--version|version)
salesforcecodex-dx-plugin/0.0.2 win32-x64 node-v12.10.0
$ sfdx --help [COMMAND]
USAGE
  $ sfdx COMMAND
...
```
<!-- usagestop -->
<!-- commands -->
* [`sfdx scdx:apex:code:create [-n <string>] [-t <string>] [-o <string>] [-d <string>] [-v <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`](#sfdx-scdxapexcodecreate--n-string--t-string--o-string--d-string--v-string---json---loglevel-tracedebuginfowarnerrorfataltracedebuginfowarnerrorfatal)

## `sfdx scdx:apex:code:create [-n <string>] [-t <string>] [-o <string>] [-d <string>] [-v <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`

```
USAGE
  $ sfdx scdx:apex:code:create [-n <string>] [-t <string>] [-o <string>] [-d <string>] [-v <string>] [--json] 
  [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]

OPTIONS
  -d, --outputdir=outputdir                                                         folder for saving the created files
  -n, --name=name                                                                   file or bundle name
  -o, --object=object                                                               Provide Object name
  -t, --template=template                                                           code template name
  -v, --vars=vars                                                                   variables required by the template
  --json                                                                            format output as json

  --loglevel=(trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL)  [default: warn] logging level for
                                                                                    this command invocation
```

_See code: [lib\commands\scdx\apex\code\create.js](https://github.com/52000290/salesforcecodex-dx-plugin/blob/v0.0.2/lib\commands\scdx\apex\code\create.js)_
<!-- commandsstop -->
<!-- debugging-your-plugin -->
# Debugging your plugin
We recommend using the Visual Studio Code (VS Code) IDE for your plugin development. Included in the `.vscode` directory of this plugin is a `launch.json` config file, which allows you to attach a debugger to the node process when running your commands.

To debug the `hello:org` command: 
1. Start the inspector
  
If you linked your plugin to the sfdx cli, call your command with the `dev-suspend` switch: 
```sh-session
$ sfdx hello:org -u myOrg@example.com --dev-suspend
```
  
Alternatively, to call your command using the `bin/run` script, set the `NODE_OPTIONS` environment variable to `--inspect-brk` when starting the debugger:
```sh-session
$ NODE_OPTIONS=--inspect-brk bin/run hello:org -u myOrg@example.com
```

2. Set some breakpoints in your command code
3. Click on the Debug icon in the Activity Bar on the side of VS Code to open up the Debug view.
4. In the upper left hand corner of VS Code, verify that the "Attach to Remote" launch configuration has been chosen.
5. Hit the green play button to the left of the "Attach to Remote" launch configuration window. The debugger should now be suspended on the first line of the program. 
6. Hit the green play button at the top middle of VS Code (this play button will be to the right of the play button that you clicked in step #5).
<br><img src=".images/vscodeScreenshot.png" width="480" height="278"><br>
Congrats, you are debugging!
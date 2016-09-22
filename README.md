
# Welcome to WDIO-ALLURE-ADDONS-REPORTER
- Based on wdio-allure-reporter
-Allow to use more Allure options ( test descr, features, stories, environment, arguments, severity, issue, subSteps, attachments )


## Added event listener :


- test:meta  :  manage testcase meta-data for allure
```json
meta : {
 (mandatory) cid : ...,
 (mandatory) event : 'test:meta'
 (optional) description : string
 (optional) feature : string | array
 (optional) strory : string | array
 (optional) issue : string | array
 (optional) severity : [ 'blocker','critical','normal','minor','trivial' ]
 (optional) argument : {name: value, name2: value }
 (optional) environment : {name: value, name2: value }
}
```
      

- step:start   : start a new sub step

```json
start : {
 (optional) title : string
}
```
  

- step:end   :  close current step

```json
end : {
 (optional) status : passed, failed ( default : passed )
}
```

- test:attach   : attach resource to test 

```json
attachment : {
  cid: ...,
  event: 'test:attach',
  title: string,
  file: string,
  type: string
}
```

- test:log   : log message with optional details

```json
log : {
  cid: ...,
  event: 'test:log',
  message: string,
  detail: object
}
```


## Install reporter with npm

```bash
$ npm install wdio-allure-addons-reporter --save
```
  
- Usage wdio.conf.js :

```json
reporters: [..., 'allure-addons'],
reporterOptions: {
    'outputDir': 'outputDir',
    'allure-addons': {
        outputDir: 'allure-results',
        debug: true,
        debugSeleniumCommand: true
    }
}, 
```

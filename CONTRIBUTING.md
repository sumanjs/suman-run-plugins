

Plugin contract:

Suman run plugins can be loaded in a Node.js runtime via:

```javascript
require('suman-run-plugins/plugins/x')
```

this will load the index.js file of your plugin.
Because of the structure of this repo, 'x' will be a unique name.


## API Contract

1. <b>Your index.js file should have the following contract:</b>

```javascript

const fs = require('fs');
const path = require('path');

exports.getTransformStream = function () {
  return fs.createReadStream(exports.getTransformPath());
};

exports.getTransformPath = function(){
  return path.resolve(__dirname + '/index.sh');
};

```

2. <b> your index.sh file must be able to handle a JSON array of test paths</b>
<br>
 => the JSON array is an env variable with name `${SUMAN_TEST_PATHS}`
 => these test paths are absolute filepaths.


3. <b>your index.sh file must use the correct exit code.</b> 
<br>
To ensure this, the best thing to do
is to make the last line of your index.sh file the command which runs your tests.


4. <b>Your plugin should pass the following test:</b>
<br>

```suman-tools --test-run-plugin=<plugin-name>```

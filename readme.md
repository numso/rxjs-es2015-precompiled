Upstream source: https://github.com/ReactiveX/rxjs
Published as: @numso/rxjs-es2015-precompiled

## Usage

```
import * as rxjs from '@numso/rxjs-es2015-precompiled'
import { pluck } from '@numso/rxjs-es2015-precompiled/operators'
```

## Why

I want to load rxjs/operators from pika.dev. They're not working right now. This precompiled version does the trick.

## Build Steps

```
yarn create snowpack-app rxjs-precompiled --template @snowpack/app-template-react --use-yarn
cd rxjs-precompiled
yarn add rxjs
echo -e "import 'rxjs'\nimport 'rxjs/operators'" > src/index.jsx
yarn build
cp build/web_modules/rxjs.js <ROOT>/rxjs.js
cp build/web_modules/rxjs/operators.js <ROOT>/operators.js
cp build/web_modules/common/zip-9224ffb3.js <ROOT>/common.js
# Update references to common/zip-###.js
```

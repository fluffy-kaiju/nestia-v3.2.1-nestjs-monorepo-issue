## project-name-npm

Install walkthrough

```
$ npm i -g @nestjs/cli

$ nest -v
10.3.2

$ node -v
v20.10.0

$ nest new project-name-npm
? Which package manager would you ❤️  to use? npm

$ cd project-name-npm

$ npx nestia setup
----------------------------------------
 Nestia Setup Wizard
----------------------------------------
? Package Manager npm
? TS Config File tsconfig.json

```

Edit controller

```ts
// src/app.controller.ts:
import { Controller } from '@nestjs/common';
import { AppService } from './app.service';
import { TypedRoute } from '@nestia/core';

@Controller()
export class AppController {
  constructor(private readonly appService: AppService) {}

  @TypedRoute.Get()
  getHello(): string {
    return this.appService.getHello();
  }
}
```

Start nest success fully

```
$ npm run start

> project-name-npm@0.0.1 start
> nest start

[Nest] 91722  - 06/16/2024, 9:05:12 PM     LOG [NestFactory] Starting Nest application...
[Nest] 91722  - 06/16/2024, 9:05:12 PM     LOG [InstanceLoader] AppModule dependencies initialized +17ms
[Nest] 91722  - 06/16/2024, 9:05:12 PM     LOG [RoutesResolver] AppController {/}: +8ms
[Nest] 91722  - 06/16/2024, 9:05:12 PM     LOG [RouterExplorer] Mapped {/, GET} route +4ms
[Nest] 91722  - 06/16/2024, 9:05:12 PM     LOG [NestApplication] Nest application successfully started +3ms
```

## project-name-npm-mono

Install walkthrough

```
$ cp -r project-name-npm/ project-name-npm-mono/

$ cd project-name-mono/

$ nest generate app my-app
DELETE src
DELETE test
CREATE apps/project-name-npm/tsconfig.app.json (231 bytes)
CREATE apps/project-name-npm/src/app.controller.spec.ts (617 bytes)
CREATE apps/project-name-npm/src/app.controller.ts (323 bytes)
CREATE apps/project-name-npm/src/app.module.ts (249 bytes)
CREATE apps/project-name-npm/src/app.service.ts (142 bytes)
CREATE apps/project-name-npm/src/main.ts (208 bytes)
CREATE apps/project-name-npm/test/app.e2e-spec.ts (630 bytes)
CREATE apps/project-name-npm/test/jest-e2e.json (183 bytes)
CREATE apps/my-app/tsconfig.app.json (221 bytes)
CREATE apps/my-app/src/main.ts (215 bytes)
CREATE apps/my-app/src/my-app.controller.spec.ts (645 bytes)
CREATE apps/my-app/src/my-app.controller.ts (287 bytes)
CREATE apps/my-app/src/my-app.module.ts (265 bytes)
CREATE apps/my-app/src/my-app.service.ts (144 bytes)
CREATE apps/my-app/test/jest-e2e.json (183 bytes)
CREATE apps/my-app/test/app.e2e-spec.ts (639 bytes)
UPDATE tsconfig.json (1596 bytes)
UPDATE package.json (2286 bytes)
UPDATE nest-cli.json (867 bytes)
```

```
$ npm run start

> project-name-npm@0.0.1 start
> nest start

webpack 5.90.1 compiled successfully in 2875 ms

/tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/node_modules/@nestia/core/src/decorators/internal/NoTransformConfigureError.ts:5
  return new Error(
         ^
Error: Error on nestia.core.TypedRoute.Get(): no transform has been configured. Run "npx typia setup" command, or check if you're using non-standard TypeScript compiler like Babel or SWC.
    at NoTransformConfigureError (/tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/node_modules/@nestia/core/src/decorators/internal/NoTransformConfigureError.ts:5:10)
    at /tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/node_modules/@nestia/core/src/decorators/internal/get_path_and_stringify.ts:30:63
    at /tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/node_modules/@nestia/core/src/decorators/internal/get_path_and_stringify.ts:21:44
    at Object.route [as Get] (/tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/node_modules/@nestia/core/src/decorators/TypedRoute.ts:90:79)
    at Object.<anonymous> (/tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/dist/apps/project-name-npm/main.js:74:23)
    at __webpack_require__ (/tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/dist/apps/project-name-npm/main.js:137:42)
    at Object.<anonymous> (/tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/dist/apps/project-name-npm/main.js:24:26)
    at __webpack_require__ (/tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/dist/apps/project-name-npm/main.js:137:42)
    at /tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/dist/apps/project-name-npm/main.js:151:22
    at /tmp/nestia-v3.2.1-nestjs-monorepo-issue/project-name-npm-mono/dist/apps/project-name-npm/main.js:158:3
```
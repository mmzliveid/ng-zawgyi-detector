# Zawgyi and Standard Myanmar Unicode Detector for Angular

[![GitHub Actions Status](https://github.com/myanmartools/ng-zawgyi-detector/workflows/Main%20Workflow/badge.svg)](https://github.com/myanmartools/ng-zawgyi-detector/actions)
[![Azure Pipelines Status](https://dev.azure.com/myanmartools/ng-zawgyi-detector/_apis/build/status/myanmartools.ng-zawgyi-detector?branchName=master)](https://dev.azure.com/myanmartools/ng-zawgyi-detector/_build/latest?definitionId=2&branchName=master)
[![codecov](https://codecov.io/gh/myanmartools/ng-zawgyi-detector/branch/master/graph/badge.svg)](https://codecov.io/gh/myanmartools/ng-zawgyi-detector)
[![npm version](https://badge.fury.io/js/%40myanmartools%2Fng-zawgyi-detector.svg)](https://www.npmjs.com/package/@myanmartools/ng-zawgyi-detector)
[![Gitter](https://badges.gitter.im/myanmartools/community.svg)](https://gitter.im/myanmartools/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

Zawgyi-One and standard Myanmar Unicode detector library for Angular applications.

## Features

* Accurate & performance optimized detection for both Zawgyi-One (ဇော်ဂျီ) and standard Myanmar Unicode (မြန်မာ ယူနီကုဒ်)
* Intelligent chunk by chunk detection on mix-typed input (Mixed Zawgyi and Unicode)
* Fully tested with Myanmar Spelling Book (မြန်မာ စာလုံးပေါင်း သတ်ပုံကျမ်း) data
* Deep detection on `A That` (အသက်), `Pahsin` (ပါဌ်ဆင့်), `Kinsi` (ကင်းစီး), etc.
* Work with latest version of Angular
* Compatible with Angular Universal (Node.js Server Side Rendering - SSR)
* Open source and MIT license!

## Get Started

### Installation

npm

```bash
npm install @myanmartools/ng-zawgyi-detector
```

or yarn

```bash
yarn add @myanmartools/ng-zawgyi-detector
```

### Module Setup (app.module.ts)

```typescript
import { ZawgyiDetectorModule } from '@myanmartools/ng-zawgyi-detector';

@NgModule({
  imports: [
    // Other module imports

    // ng-zawgyi-detector module
    ZawgyiDetectorModule
  ]
})
export class AppModule { }
```

Live edit [app.module.ts in stackblitz](https://stackblitz.com/github/myanmartools/ng-zawgyi-detector/tree/master/samples/demo-app?file=src%2Fapp%2Fapp.module.ts)

### Usage (app.component.ts)

```typescript
import { Component } from '@angular/core';

import { ZawgyiDetector } from '@myanmartools/ng-zawgyi-detector';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html'
})
export class AppComponent {
  constructor(private readonly _zawgyiDetector: ZawgyiDetector) {
    const result = this._zawgyiDetector.detect('ျမန္မာစာ');
      if (result.detectedEnc === 'zg') {
          console.log('ZAWGYI DETECTED');
      } else if (result.detectedEnc === 'uni') {
          console.log('UNICODE DETECTED');
      }
  }
}
```

Live edit [app.component.ts in stackblitz](https://stackblitz.com/github/myanmartools/ng-zawgyi-detector/tree/master/samples/demo-app?file=src%2Fapp%2Fapp.component.ts)

## Samples

Demo app [view source](https://github.com/myanmartools/ng-zawgyi-detector/tree/master/samples/demo-app) / [live edit in stackblitz](https://stackblitz.com/github/myanmartools/ng-zawgyi-detector/tree/master/samples/demo-app)

## Live Application

[Zawgyi Unicode Converter - Angular PWA](https://zawgyi-unicode-converter.myanmartools.org)

## Build & Test Tools

We use [lib-tools](https://github.com/lib-tools/lib-tools) for bundling, testing and packaging our library projects.

[![Lib Tools](https://repository-images.githubusercontent.com/273890506/28038a00-dcea-11ea-8b4a-7d655158ccf2)](https://github.com/lib-tools/lib-tools)

## Feedback and Contributing

Check out the [Contributing](https://github.com/myanmartools/ng-zawgyi-detector/blob/master/CONTRIBUTING.md) page.

## License

This repository is licensed with the [MIT](https://github.com/myanmartools/ng-zawgyi-detector/blob/master/LICENSE) license.

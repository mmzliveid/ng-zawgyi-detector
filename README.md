# Zawgyi / Myanmar Unicode Detector for Angular

[![Gitter](https://badges.gitter.im/myanmartools/community.svg)](https://gitter.im/myanmartools/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

Zawgyi-One or Myanmar Unicode font encoding detection modules for [Angular](https://angular.io/) applications.

## Get Started

### Installation

npm

```shell
npm install @myanmartools/ng-zawgyi-detector
```

or yarn

```shell
yarn add @myanmartools/ng-zawgyi-detector
```

### Module Setup (app.module.ts)

```typescript
import { CommonModule } from '@angular/common';
import { HttpClientModule } from '@angular/common/http';
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

import { ZawgyiDetectorModule } from '@myanmartools/ng-zawgyi-detector';
import { HttpZgUniRuleLoaderModule } from '@myanmartools/ng-zawgyi-detector/http-loader';

@NgModule({
    imports: [
        BrowserModule,
        CommonModule,
        HttpClientModule,
        // Other module imports

        // ng-zawgyi-detector
        ZawgyiDetectorModule,
        HttpZgUniRuleLoaderModule
    ],
    bootstrap: [AppComponent]
})
export class AppModule { }
```

### Usage (app.component.ts)

```typescript
import { Component } from '@angular/core';

import { ZawgyiDetector } from '@myanmartools/ng-zawgyi-detector';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html'
})
export class AppComponent {
    input = 'ေဇာ္ဂ်ီ';

    constructor(private readonly _zawgyiDetector: ZawgyiDetector) {
        this._zawgyiDetector.detect(this.input).subscribe(result => {
            if (result.detectedEnc === 'zg') {
                console.log('ZAWGYI DETECTED');
            } else if (result.detectedEnc === 'uni') {
                console.log('UNICODE DETECTED');
            }
        });
    }
}
```

## Example Project

[Zawgyi-One or Myanmar Unicode Font Detector Demo](https://github.com/myanmartools/ng-zawgyi-detector/tree/master/samples/zawgyi-unicode-detector-demo)

## Feedback and Contributing

Check out the [Contributing](https://github.com/myanmartools/ng-zawgyi-detector/blob/master/CONTRIBUTING.md) page to see the best places to log issues and start discussions.

## License

This repository is licensed with the [MIT](https://github.com/myanmartools/ng-zawgyi-detector/blob/master/LICENSE) license.
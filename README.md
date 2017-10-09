# puppeteer-plugin-tester
> Utilities for testing puppeteer plugins


### Usage

```javascript
import pluginTester from 'puppeteer-plugin-tester';
import yourPlugin from '../your-plugin';

pluginTester({
  plugin: myPlugin,
  tests: [
    {
      content: `
        <!DOCTYPE html>
        <html lang="en">
        <head>
          <title>Puppeteer plugin tester demo</title>
        </head>
        <body></body>
        </html>
      `,
      assertion(result) {
        const title = result.getTitle();

        expect(title).toBeEqual('Puppeteer plugin tester demo');
      }
    },
    {
      content: `
        <!DOCTYPE html>
        <html lang="en">
        <head>
          <title></title>
        </head>
        <body></body>
        </html>
      `,
      snapshot: true
    }
  ]
})
```
# The screenshot API for developers

With [ScreenshotOne](https://screenshotone.com/) you can render screenshots in one simple API call, instead of managing browser clusters, and handling all the corner cases.

It supports a wide range of programming languages including TypeScript, Python, Java, and more. This flexibility makes it an excellent tool for developers looking to integrate screenshot functionality into their applications regardless of their development environment. 

## Key features 

The [ScreenshotOne API](https://screenshotone.com/) offers powerful features that make it a go-to solution for developers:

1. Ability to take clean screenshots by blocking cookie banners, ads, chat, and other widgets to make the screenshots look clean.
2. Supports rendering screenshots in a variety of image formats including PNG, JPEG, WebP, GIF, and more.
3. Provides options to customize the screenshot rendering, such as setting the screen size, enabling dark mode, and extracting metadata like fonts used.
4. Offers asynchronous screenshot execution and webhooks to upload the rendered screenshots or HTML content to services like Amazon S3.
5. Provides SDKs and no-code integrations with tools like Zapier to easily incorporate screenshot functionality into applications.

## Code Examples 

Run the next command to install the JavaScript and TypeScript Node.js SDK to take screenshots:

```bash
npm install screenshotone-api-sdk --save
```

Generate a screenshot URL without executing the request. Or download the screenshot. It is up to you:

```javascript
import * as fs from "fs";
import * as screenshotone from "screenshotone-api-sdk";

// create API client
const client = new screenshotone.Client("<access key>", "<secret key>");

// set up options
const options = screenshotone.TakeOptions.url("https://example.com")
    .delay(3)
    .blockAds(true);

// generate URL
const url = client.generateTakeURL(options); // or generateSignedTakeURL(options) for signed URLs
console.log(url);
// expected output: https://api.screenshotone.com/take?url=https%3A%2F%2Fexample.com&delay=3&block_ads=true&access_key=%3Caccess+key%3E

// or download the screenshot
const imageBlob = await client.take(options);
const buffer = Buffer.from(await imageBlob.arrayBuffer());
fs.writeFileSync("example.png", buffer);
// the screenshot is store in the example.png file
```

[The API supports other languages, too.](https://screenshotone.com/docs/code-examples/)

## Conclusion

[The ScreenshotOne screenshot API](https://screenshotone.com/) is a robust tool designed to accommodate a variety of programming needs across different languages. 

Its versatility in supporting multiple languages and its extensive feature set make it an ideal choice for developers looking to integrate screenshot capabilities into their applications. Whether for automation, testing, or documentation, ScreenshotOne provides the tools necessary to capture and manage screenshots effectively.

# Cue2Cue

Cue2Cue is an application which helps solve the issue of attendance and announcements for cultural orgs who host dance performances for their cultural shows. Need a way to communicate with your dancers about call times and hell week updates? Choose Cue2Cue a UF student built and maintained application.

## Tools
Built a static frontend using Vue.js, TypeScript, and Tailwind hosted on **S3** and served using **CloudFront**. 

User Authentication handled by **AWS Cognito** allowing for Google Auth.

Built a serverless event-driven backend using **AWS Lambda** functions exposed on API Gateways. **AWS EventBridge** allow for reminders and scheduled texts. **AWS DynamoDB** and **AWS SNS** for texts and Lambda functionality.

## Website

Hosted On:

```bash
in-progress
```

## Architecture

![Website Architecture](/Cue2CueArchitecture.png)

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
**MIT License**

*Copyright* © [2025] [Loc Dinh]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
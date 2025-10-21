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

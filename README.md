# Political Race API

I haven't looked too far into it but it seems like the [Google has an API to recieve information about particular political race](https://developers.google.com/civic-information/docs/v2).

# Donations API

So there is preexisting logic on this repo for login verification. I don't know if it is needed or should be used. Either way if I was planning on using [DynamoDB](https://aws.amazon.com/dynamodb/) as the main database. If you(Caroline) could figure out how to standup the Dynamo instance either using the [Docker Image](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.DownloadingAndRunning.html#docker) or [downloading it locally](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.DownloadingAndRunning.html#download-locally) and then use the [SDK](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/DynamoDB.html) to put an object similar to below in the Database that would be great! The logic should be in a `PUT` command in the route `/donations`

```json
{
    "CustomerID": "abc123",
    "CanidateID": "def456",
    "CharityID": "hij789",
    "Donation": {
        "Amount": "$2.00",
        "Currency": "USD",
        "Time": "1669334542",
        "Platform": "Desktop"
    }
}
```

## About Express

This project was created with [express-generator-typescript](https://github.com/seanpmaxwell/express-generator-typescript).


## Available Scripts

### `npm run dev`

Run the server in development mode.

### `npm test`

Run all unit-tests with hot-reloading.

### `npm test -- --testFile="name of test file" (i.e. --testFile=Users).`

Run a single unit-test.

### `npm run test:no-reloading`

Run all unit-tests without hot-reloading.

### `npm run lint`

Check for linting errors.

### `npm run build`

Build the project for production.

### `npm start`

Run the production build (Must be built first).

### `npm start -- --env="name of env file" (default is production).`

Run production build with a different env file.


## Additional Notes

- If `npm run dev` gives you issues with bcrypt on MacOS you may need to run: `npm rebuild bcrypt --build-from-source`. 

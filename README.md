# Visual Recognition + AlchemyVision Demo
[![Build Status](https://travis-ci.org/watson-developer-cloud/visual-recognition-nodejs.svg?branch=master)](https://travis-ci.org/watson-developer-cloud/visual-recognition-nodejs?branch=master)
[![codecov.io](https://codecov.io/github/watson-developer-cloud/visual-recognition-nodejs/coverage.svg?branch=master)](https://codecov.io/github/watson-developer-cloud/visual-recognition-nodejs?branch=master)

[Visual Recognition][visual_recognition_service] partnered with [Alchemy Vision](www.alchemyapi.com/products/alchemyvision), allows you to derive insights from an image based on its visual content. You can organize image libraries, understand an individual image, and create custom classifiers for specific results that are tailored to your needs.

Give it a try! Click the button below to fork into IBM DevOps Services and deploy your own copy of this application on Bluemix.

[![Deploy to Bluemix](https://bluemix.net/deploy/button.png)](https://bluemix.net/deploy?repository=https://github.com/filipmadej/visual-recognition-demo)


## Running locally
  The application uses [Node.js](http://nodejs.org) and [npm](https://www.npmjs.com) so you will have to download and install them as part of the steps below.

1. Copy the credentials from your `visual-recognition-service` service in Bluemix to `app.js`, you can see the credentials using:

    ```sh
    $ cf env <application-name>
    ```
    Example output:
    ```sh
    System-Provided:
    {
    "VCAP_SERVICES": {
      "visual_recognition": [{
          "credentials": {
            "url": "<url>",
            "password": "<password>",
            "username": "<username>"
          },
        "label": "visual_recognition",
        "name": "visual-recognition-service",
        "plan": "free"
     }]
    }
    }
    ```
  Create env.json file locally.
  
  Example:
  {
   "vcap": {
   "services": {
      "visual_recognition": [
         {
            "name": "visual-recognition-service",
            "label": "visual_recognition",
            "plan": "free",
            "credentials": {
               "url": "https://gateway.watsonplatform.net/visual-recognition-beta/api",
               "password": "U3aw2JDDH4X1",
               "username": "24103cf3-ac08-44a5-95cf-47a2d5f5fe73"
            }
         }
      ],
      "alchemy_api": [
         {
            "name": "alchemy-service",
            "label": "alchemy_api",
            "plan": "free",
            "credentials": {
               "url": "https://gateway-a.watsonplatform.net/calls",
               "apikey": "fb5bb86167936009da131e8dbdf9c9b634b27512",
               "note": "It may take up to 5 minutes for this key to become active. This is your previously active free apikey. If you want a different one, please wait 24 hours after unbinding the key and try again."
            }
         }
      ]
   }
   }
}

2. Install [Node.js](http://nodejs.org/)
3. Go to the project folder in a terminal and run:
    `npm install`
4. Start the application
5.  `npm start`
6. Go to `http://localhost:3000`

## Troubleshooting

To troubleshoot your Bluemix app the main useful source of information are the logs, to see them, run:

  ```sh
  $ cf logs <application-name> --recent
  ```

## License

  This sample code is licensed under Apache 2.0. Full license text is available in [LICENSE](LICENSE).

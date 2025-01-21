# Google Gemini Setup

This setup uses the Google Gemini free tier for automatic tagging. At the time of this writing, users are unlikely to incur any costs under this model. However, you will not be able to use the service if you reach the usage limits.

:::info
Google's warning: "In order to use any features that incur costs, link a billing account with this project."
:::

## Important Note:
Each model comes with its respective limits, so please review these carefully.

## Access Pricing Information:

[Google AI Pricing](https://ai.google.dev/pricing) (URL is subject to change at Google's discretion)

## Choose the Model:
Select the model you would like to use for Hoarder by clicking "Try in Google AI Studio."

## Get API Key:
In Google AI Studio, click on "Get API Key."

On the next screen, click on "Create API Key."

Save the key in a secure location as you will need to enter it in your Hoarder docker-compose file. Alternatively, you can store it in an .env file.

## Configure Docker Compose File:
Add the following environment settings to your docker-compose.yml file:

```
environment:
  OPENAI_BASE_URL: https://generativelanguage.googleapis.com/v1beta/ # Please note the "Beta" aspect to the URL. It is likely to change at any given point
  OPENAI_API_KEY: Your API Key From Google AI Studio  # API key you generated from the steps above
  INFERENCE_TEXT_MODEL: gemini-1.5-flash # Make sure to swap out the name with the model you selected

```
Deploy or redeploy, automatic tagging should start working next time your Hoard.

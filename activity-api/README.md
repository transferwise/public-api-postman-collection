# Activity API flow Postman Collections

A set of Postman collections containing the example flows to demonstrate usage of Activity API.

For use with the Postman client, please use the latest version: [download it here](https://www.getpostman.com/).

## Set Up

### Import the Postman collections

Import the appropriate collection file into Postman: `Activity API.postman_collection.json`

Also import the `Activity API Sandbox.postman_environment.json` file, found in the top level of this project, to add the environment variables used to manage your sandbox/production credentials.

### Set up your Postman environment variables

Set environment variables for `client_id`, `client_secret` and `client_redirect_uri` credentials issued to you by TransferWise.

Use our [oauth flow](https://transferwise.github.io/api-docs-partners/#connected-apps-integration-guide-user-authorization) to generate an authorization code and set this to an environment variable called `client-auth-code`.

Sandbox API Host: `https://api.sandbox.transferwise.tech`
Production API Host: `https://api.wise.com`

### Getting started

To simulate activities on Sandbox, a user has to perform certain actions such as creating a transfer, ordering a card, and etc...
For more information, please read our simulation guide [here](https://api-docs.transferwise.com/api-reference/simulation).

## Help

If you need any help using the API please [contact our support team](mailto:api@transferwise.com).

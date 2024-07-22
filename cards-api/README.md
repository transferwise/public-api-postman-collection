# Cards API flow Postman Collections

A set of Postman collections containing the example flows to demonstrate and test the [Wise Card Issuance API for partners](https://api-docs.transferwise.com/card-issuance#card-issuance-integration-guide).

For use with the Postman client, please use the latest version: [download it here](https://www.getpostman.com/).

## Set Up

### Import the Postman collections

Import the appropriate collection file into Postman: `Cards API.postman_collection.json`

Also import the `Cards API Sandbox.postman_environment.json` file, found in the top level of this project, to add the environment variables used to manage your sandbox/production credentials. 

### Set up your Postman environment variables

Set environment variables for `client-id`, `client-secret` and `client-redirect-uri` credentials issued to you by TransferWise.

Use our [oauth flow](https://transferwise.github.io/api-docs-partners/#connected-apps-integration-guide-user-authorization) to generate an authorization code and set this to an environment variable called `client-auth-code`.

Sandbox API Host: `https://api.sandbox.transferwise.tech`
Production API Host: `https://api.wise.com`

### Getting started

The flow has 10 parts: 
1. Authentication
2. Card Issuance: To generate a card, you need to create a card order. The card order availability API endpoint tells which Card Programs are available for your profile. A Card Program is we call all of the cards you will be issuing with us, grouped by card type and by issuing country. If your profile is verified, the card will be generated in a few seconds. If your profile is not verified, the card order status will be PLACED until your profile gets verified. For Preset Card PIN, the request and response are encrypted. We recommend you to use our `preset-pin` Node module instead. Please [contact our support team](mailto:api@transferwise.com) if you don't have the Node module to preset card PINs.
3. Card Management: This section lets you retrieve cards (without the PANs), set transactional, daily, monthly and lifetime limits, retrieve the card transactions, temporarily freeze cards and permanently block cards.
4. Sensitive Card Details: This section lets you retrieve the card PANs. Because the request and response are encrypted, we recommend you to use our `get-card-details` Node module instead. Please [contact our support team](mailto:api@transferwise.com) if you don't have the Node module to retrieve card PANs.
5. Spend controls: This section lets you create, retrieve, apply, unapply and delete authorization rules, which dictate whether transactions should be declined or approved based on a pre-determined set of rules. 
6. Spend limits: This section lets you manage spend limits that can be applied to your profile or card. You can create, retrieve and update limits for both profile and card, and delete limits for card. 
7. Disputes: This section lets you raise, retrieve disputes by profile or ID, and withdraw disputes on Wise. 
8. Activity: This section lets you retrieve activities for a profile.
9. Push provisioning: This section lets you obtain payment tokens associated with a card. 
10. Simulation: This section lets you simulate payment processing (authorization, clearing, reversal) by changing transfer statuses. 

## Help

If you need any help using the API please [contact our support team](mailto:api@transferwise.com).

# Multi-Currency Account (MCA) API flow Postman Collections

A set of Postman collections containing the example flows to demonstrate and test the [Wise Multi-Currency Account API for partners](https://api-docs.transferwise.com/#multi-currency-account).

For use with the Postman client, please use the latest version: [download it here](https://www.getpostman.com/).

## Set Up

### Import the Postman collections

Import the appropriate collection file into Postman: `Multi-Currency Account.postman_collection.json`

Also import the `MCA Sandbox.postman_environment.json` file, found in the top level of this project, to add the environment variables used to manage your sandbox/production credentials. 

### Set up your Postman environment variables

1. Set environment variables for `client-id`, `client-secret` and `client-redirect-uri` credentials issued to you by TransferWise.
2. Change the environment variables for `registrationCode` and `account-email` if needed.

Sandbox API Host: `https://api.sandbox.transferwise.tech`

Production API Host: `https://api.wise.com`

### Getting started

## Creating New User (Banks Only)

Creating a new user in the background is a feature enabled only to bank partners.
For partners who are not having this feature enabled, please use the `Linking Existing User` flow instead.

1. In the `Common (User & Profile)` section, run the `Create User` and `User Token from Registration Code` APIs.
2. This will create a user using the regisration code API, and get the access token and refresh token of that user.

## Linking Existing User (OAuth)
Due to some limitations in the sandbox, we are not able to send out emails from the sandbox.
For that reason, for pure API use case (without building an integrated oauth flow), we would suggest that you use a `Show Code` flag when running OAuth.

Sandbox OAuth URL: 

`https://sandbox.transferwise.tech/oauth/authorize/?client_id=CLIENT_ID&redirect_uri=REDIRECT_URI&forwardingMode=showCode`

Production OAuth URL: 

`https://wise.com/oauth/authorize/?client_id=CLIENT_ID&redirect_uri=REDIRECT_URI&forwardingMode=showCode`


1. Copy the OAuth URL of your selected environment.
2. Replace `CLIENT_ID` and `REDIRECT_URI` with the appropriate value configured for your client ID (Check with your Implementation Manager if unsure).
3. Paste the OAuth URL into your browser address bar.
4. Login to your Wise user account.
5. After authorizing the access, you will be given an authorization code.
6. In the Postman Collection, `Common (User & Profile)` section, select the `User Token from Authorization Code` API.
7. Replace the `code` with the authorization code and run the API.
8. You should now get the access token and refresh token of the user.

## Getting User Profile
The Multi-Currency Account API requires the user to have a profile.
To get or generate the user profile, in the Postman Collection, `Common (User & Profile)` section, run the `Create personal profile` and/or `Get personal profile` API(s).

## Setting Up MCA for the First Time
Before any user account can start using the Multi-Currency Account feature and API, it has to be KYC-ed and verified.

### Prodcution
In production, a real verification would be needed. In this case, please contact your Implementation Manager for help.

### Sandbox
In the sandbox, we have provided an API to simulate verification. In the Postman Collection, `First Time Setup` section, run the `Simulate Profile Verification` API and your account should be verified in seconds.


Once you have your user verified, you can then start creating an MCA Balance.

1. In the Postman Collection, `First Time Setup` section, select the `Create Balance` API.
2. Change the currency to a currency you desire.
3. Run the API.
4. You should now have access to that currency balance.

## Managing MCA and Account Details
We have included 2 sections for managing your MCA balances as well as your Account Details.

- `Account and Balance`: MCA Balances management
- `Account Details`: Bank Account Details management

## Useful Flows
We have 3 flows added for your convenience in running and testing different use cases.

- `Top Up`: Topping up money into the MCA balance. This is similar to a standard Send Money flow, with the recipient as your MCA balance. For Sandbox, we have an API `Simulate Top Up` to provide easy top up for your MCA balance.
- `Send Money`: Sending money from your MCA Balance to an external recipient.
- `Convert Money`: Convert money from one of your MCA Balance (currency A) to another of your MCA Balance (currency B).

## Help

If you need any help using the API please [contact our support team](mailto:api@transferwise.com).

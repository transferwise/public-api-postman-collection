# TransferWise API Bank Flow Postman Collection

A Postman collection containing example requests to demonstrate and test the [TransferWise public API for banks](https://transferwise.github.io/api-docs-banks).

For use with the Postman client, created using v7.1: [download it here](https://www.getpostman.com/).

## Set Up

### Import Collection

Import the `TransferWise for Banks API flow.postman_collection.json` file to Postman to add all of the REST calls to your app in a dedicated collection.

Import the `TransferWise For Banks (Sandbox).postman_environment` file to Postman to add the _Evironment_ used to manage variables for use in the calls.

### Set up your Environment variables

To begin with set the `client-id`, `client-secret` and `client-redirect-uri` variables based ont those issued to you by TransferWise.

### Get user access

 Follow the flows set out in the first section of the collection, "Creating or accessing existing users" to create or get access to TransferWise user accounts. Please use [this guide]( https://transferwise.github.io/api-docs-banks/#bank-integrations-guide-get-user-authorization-for-existing-accounts) to help understand these flows.

All endpoints in section 1 which generate tokens for users (`/oauth/token`) have tests that automatically set the `refresh` and `token` environment variables when you successfully generate them.

## Next Steps

Continue working on the flows set out in the collection alongside the [bank docs](https://transferwise.github.io/api-docs-banks) to create user profiles, quotes, create recipients and transfers.

## Help

If you need any help using the API please [contact our support team](mailto:api@transferwise.com).

# AWS Cognito

AWS Cognito is a service that handles authentication. It abstracts the table of stored users into a 'user pool' that is then managed accordingly.

## Initial Thoughts

- Heavily relies on UI code to properly send the properly formatted data
  - UI code would need to be re-written if Cognito updated / a different auth service was used

## Cost

Pricing is based on monthly active users ( MAU ).

A MAU is defined as someone who does any of the following actions in a calendar month:

- Signs up
- Logs in
- Changes password

### Normal Users

A normal user is defined as someone who signs up with their own information, be it username, email, phone number etc.

#### Normal Pricing

- The first 50,000 users are free.
- Up to 900,000 users, the price is \$0.00550 ( 1/2 a penny ) per active user
- After 900,000, the MAU price drops to \$0.00460
- 500,000 MAU is approximately \$2750 / mo
- 250,000 MAU is approximately \$1375 / mo

### Federated Identities ( OAuth )

The flat fee for federated users is \$0.015, regardless of quantity

#### Federated Pricing

- 250,000 MAU would be approximately \$3750 / mo
- 125,000 MAU would be approximately \$1875 / mo

## Features

### Error Handling

The error handling messages are great, and very reliable

- Very clear error messages for a variety of situations.
- Automatically detects if a phone number or email has already been used
- Example error from duplicate submission: `An account with the given email already exists`
  - Easily plug message into UI without customization or use case conditional rendering

### Resetting Password

Simple API call to send a link to the verified phone number or email.

More information can be found [here](https://docs.aws.amazon.com/cognito-user-identity-pools/latest/APIReference/API_ForgotPassword.html)

### Multi-option login

When initializing a user pool, you can specifiy which options you wish the user to be able to use to login.

- Username
- Email
- Phone number
- Either phone number or email

### OAuth

A number of federated identity providers can be utilized

- Google
- Facebook
- Amazon
- SAML
- OpenID

### Email / SMS Verification

Uses the SNS to send, subject to SNS pricing

- Verifies phone number or email
- Password reset, etc

### Cross Platform Integration

Easily implemented in IOS development, and draws from the same user pool.

### Abstraction of Encyption and security management

Abstracts away the need to manage hashing, salt rounds, and the security of users

## Implementation

Almost exclusively implemented through the UI, using a series of API calls provided by the SDK

The [docs](https://github.com/aws-amplify/amplify-js/tree/master/packages/amazon-cognito-identity-js) are a bit outdated, but provide the general flow.

The basic premise is that you instantiate a userpool ( outside of the class declaration if using Vue, React, etc )

## Pros

## Cons

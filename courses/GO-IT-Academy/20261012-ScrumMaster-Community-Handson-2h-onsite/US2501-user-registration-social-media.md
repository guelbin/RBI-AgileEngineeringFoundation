# User Story: User Registration with Social Media
## US2501-Register Using Google, LinkedIn, or GitHub

As a new customer
I want to register for an account using my Google, LinkedIn, or GitHub account
So that I can create an account quickly without creating and remembering another password.

## Description

The webshop shall allow a new customer to start registration from the registration page by selecting Google, LinkedIn, or GitHub. The customer shall be redirected to the selected provider for authentication and consent, then returned to the webshop where a customer account is created and associated with that provider identity.

## The implementation should include:

- A clearly labelled registration option for Google, LinkedIn, and GitHub
- OAuth authentication and consent through the selected provider
- Creation of a webshop customer account after successful provider authentication
- Association of the new account with the selected provider identity
- No separate webshop password required for an account created through social registration
- A clear message when the provider authentication is cancelled or fails
- A clear message and sign-in path when the provider email already belongs to an existing webshop account
- Protection against creating duplicate accounts for the same provider identity

## Acceptance criteria

- ACC-01: The registration page displays options to register with Google, LinkedIn, and GitHub.
- ACC-02: Selecting a provider starts authentication with that provider and requests only the permissions required for registration.
- ACC-03: After successful authentication for an email not yet registered, the webshop creates one customer account linked to the selected provider identity.
- ACC-04: A socially registered customer can complete registration and use the account without setting a separate webshop password.
- ACC-05: If the provider email already belongs to a webshop account, the webshop does not create a duplicate account and instructs the customer to sign in instead.
- ACC-06: If the customer cancels or the provider returns an error, the webshop does not create an account and displays a recoverable error message.
- ACC-07: Repeating registration with the same provider identity does not create additional customer accounts.


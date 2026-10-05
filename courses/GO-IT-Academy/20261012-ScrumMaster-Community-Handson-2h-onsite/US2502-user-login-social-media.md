# User Story: User Login with Social Media
## US2502-Login Using Google, LinkedIn, or GitHub

As a registered customer
I want to log in using my Google, LinkedIn, or GitHub account
So that I can access my webshop account without entering a separate webshop password.

## Description

The webshop shall allow a registered customer to start login from the login page by selecting Google, LinkedIn, or GitHub. The customer shall be redirected to the selected provider for authentication and consent, then returned to the webshop and signed in to the existing customer account associated with that provider identity.

## The implementation should include:

- A clearly labelled login option for Google, LinkedIn, and GitHub
- OAuth authentication through the selected provider
- Authentication against the existing provider-to-customer association
- Creation and persistence of the webshop session or access token after successful login
- A clear message when the provider authentication is cancelled or fails
- A clear message when the provider identity is not associated with a registered webshop account
- Protection against signing in to a different account through an unverified or mismatched provider identity

## Acceptance criteria

- ACC-01: The login page displays options to log in with Google, LinkedIn, and GitHub.
- ACC-02: Selecting a provider starts authentication with that provider and requests only the permissions required for login.
- ACC-03: After successful authentication with a provider identity linked to a registered customer, the webshop signs the customer in and grants access to the correct account.
- ACC-04: A successful social login persists the authenticated session or access token according to the webshop's existing authentication rules.
- ACC-05: If the provider identity is not linked to a registered webshop account, the webshop does not silently sign the customer into another account and displays guidance to register or use another login method.
- ACC-06: If the customer cancels or the provider returns an error, the webshop keeps the customer unauthenticated and displays a recoverable error message.
- ACC-07: A social login cannot access a different customer's account when the provider identity or returned account data does not match the stored association.


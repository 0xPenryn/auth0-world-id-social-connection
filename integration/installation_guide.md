Sign in with Worldcoin allows users to verify that they're a unique human without revealing any private information.

## Prerequisites

1. An Auth0 account and tenant. [Sign up for free](https://auth0.com/signup).
2. A [Worldcoin Developer Portal](https://developer.worldcoin.org) account. New users can [sign up for free](https://worldcoin.org/auth0-invite).
   * You will need to download the [World App](https://worldcoin.org/download) and complete phone number verification in order to sign in.

## Set up World ID

1. Navigate to the [Worldcoin Developer Portal](https://developer.worldcoin.org).
2. Create a new app in the "Select App" menu.
3. Name your app something that your users will recognize -- it's shown to users in the World App when they're signing in.
4. Select **Staging** or **Production** to match your Auth0 tenant.
   * For **Staging**, you must use the [Worldcoin Simulator](https://simulator.worldcoin.org) to sign in. This allows you to create temporary identities for testing purposes. Please note that it may take up to 5 minutes after creating an identity in the Simulator for sign-in to succeed.
   * For **Production**, you must use the [World App](https://worldcoin.org/download) to sign in. 
5. Select **Cloud**.
   * "On-chain" apps will _not_ work for Sign-in use cases.
6. Navigate to the **Sign In** configuration section.
7. Add a Redirect URI to `https://{domain}/login/callback`, replacing `{domain}` with your Auth0 tenant domain.
8. Note the `Client ID` and `Client Secret`, you'll need these when configuring the Connection in Auth0.

## Add the Connection

1. Select **Add Integration** (at the top of this page).
2. Read the necessary access requirements, and select **Continue**.
3. Configure the integration using the following fields:
   * **Client ID** and **Client Secret** must use the values found in the Worldcoin Developer Portal. **Client ID** will begin with "app_staging_" or "app_".
4. Select the **Permissions** needed for your applications.
5. Choose and configure whether to sync user profile attributes at each login.
   * It is recommended to enable this option, as a user may receive additional proof-of-personhood credentials after their first login.
6. Select **Create**.
7. In the **Applications** view, choose the Applications that should use this Connection to log in.

## Test connection

You're ready to [test this Connection](https://auth0.com/docs/authenticate/identity-providers/test-connections).

## Troubleshooting

* For support, consult the following resources:
   * [Sign in with Worldcoin documentation](https://docs.worldcoin.org/id/sign-in)
   * [Sign in API Reference](https://docs.worldcoin.org/api/sign-in-reference)
   * [Worldcoin Discord Developers Channel](https://discord.com/channels/956750052771127337/964549879722545192)
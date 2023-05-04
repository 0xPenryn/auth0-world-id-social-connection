Sign in with Worldcoin allows users to verify that they're a unique human without revealing any private information.

## Prerequisites

1. An Auth0 account and tenant. [Sign up for free](https://auth0.com/signup).
2. Sign up for the [World ID SDK](https://developer.worldcoin.org/).
   * You will need the [World App](https://worldcoin.org/download) to sign in to the Developer Portal.
   * Alternatively, you can follow the instructions below for the **`/register` API Endpoint** without creating an account on the Worldcoin Developer Portal.

## Set up World ID

There are two methods to set up World ID: the **Developer Portal** and the **`/register` API Endpoint**.

**Developer Portal:**
1. Create a new app in the "Select App" menu.
2. Name your app something that your users will recognize -- it's shown to users in the World App when they're signing in.
3. Select **Staging** or **Production** to match your Auth0 tenant.
   * For **Staging**, you must use the [Worldcoin Simulator](https://simulator.worldcoin.org) to sign in. Please note that it may take up to 5 minutes after creating an identity in the Simulator for sign-in to succeed.
   * For **Production**, you must use the [World App](https://worldcoin.org/download) to sign in. 
4. Select **Cloud**.
   * "On-chain" apps will _not_ work for Sign-in use cases.
5. Navigate to the **Sign In** configuration section.
6. Add a Redirect URI to `https://{domain}/login/callback`, replacing `{domain}` with your Auth0 tenant domain.
7. Note the `Client ID` and `Client Secret`, you'll need these when configuring the Connection in Auth0.

**`/register` API Endpoint:**
1. Follow the instructions to [register a Sign-in App via the API](https://docs.worldcoin.org/api/sign-in-reference#register-app).
   * Set `client_name` to something that your users will recognize -- it's shown to users in the World App when they're signing in.
   * Set `logo_uri` to a link to your application's logo.
   * Set `redirect_uris` to `["https://{domain}/login/callback"]`, replacing `{domain}` with your Auth0 tenant domain.
   * Leave `application_type` and `grant_types` as the default values.
2. Note the `Client ID` and `Client Secret` in the response, you'll need these when configuring the Connection in Auth0.

## Add the Connection

1. Select **Add Integration** (at the top of this page).
2. Read the necessary access requirements, and select **Continue**.
3. Configure the integration using the following fields:
   * **Client ID** and **Client Secret** must use the values found in the Worldcoin Developer Portal. **Client ID** will begin with "app_staging_" or "app_".
4. Select the **Permissions** needed for your applications.
5. Choose and configure whether to sync user profile attributes at each login.
6. Select **Create**.
7. In the **Applications** view, choose the Applications that should use this Connection to log in.

## Test connection

You're ready to [test this Connection](https://auth0.com/docs/authenticate/identity-providers/test-connections).

## Troubleshooting

* For support, consult the following resources:
   * [Sign in with Worldcoin documentation](https://docs.worldcoin.org/id/sign-in)
   * [Sign in API Reference](https://docs.worldcoin.org/api/sign-in-reference)
   * [Worldcoin Discord Developers Channel](https://discord.com/channels/956750052771127337/964549879722545192)
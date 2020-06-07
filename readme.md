# Elisp OAuth 2

- This package aims to make oauth2 simpler for elisp
- Many of the Emacs packages tend to have their own oauth2 implementations and
each one of them. Although each implement tations are slightly different
there are the core flow of oauth2 that can be abstracted out.
- This is still an early stage alpha version so please keep this is mind when
using

# Usage

Please register http://localhost:8080 as your redirect uri.

Call ```elisp-oauth-2-init``` first to set the parameters needed for requesting
and setting token. It accepts the following argumets:

```
elisp-oauth-2-api-token-url
elisp-oauth-2-api-auth-url
elisp-oauth-2-client-id
elisp-oauth-2-client-secret
elisp-oauth-2-scopes
elisp-oauth-2-oauth-refresh-token
```

This last argument ```elisp-oauth-2-oauth-refresh-token``` can be nil at first
because you won't have it until after you have gone through authorization and
received access token and refresh token.

When you call ```elisp-oauth2-request``` first, it should launch a web browser
and it should show authorization UI of the API provider. Once you have
authorized, you should be redirected to localhost:8080 where you see a very
basic UI showing the box to copy access token. Go back to your emacs, and paste
it in the prompt. Please also consider saving refresh token saved
automatically at this point to this variable
```elisp-oauth-2-oauth-refresh-token``` to your init file so you don't have to
go through the authorization process next time you relaunch emacs.

You can get the value of the refresho token by for example running ```C-h v```
and look for ```elisp-oauth-2-oauth-refresh-token```.



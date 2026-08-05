# Auth

```python
auth_api = client.auth
```

## Class Name

`AuthApi`

## Methods

* [Sign In](../../doc/controllers/auth.md#sign-in)
* [Forgot Password](../../doc/controllers/auth.md#forgot-password)
* [Change Password](../../doc/controllers/auth.md#change-password)
* [Refresh Token](../../doc/controllers/auth.md#refresh-token)


# Sign In

Okta signin

:information_source: **Note** This endpoint does not require authentication.

```python
def sign_in(self,
           body)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SignInInputModel`](../../doc/models/sign-in-input-model.md) | Body, Required | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`SignInOutputModel`](../../doc/models/sign-in-output-model.md).

## Example Usage

```python
body = SignInInputModel(
    email='abc@abc.com',
    password='Gpattm@#124'
)

result = auth_api.sign_in(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "AuthenticationResult": {
    "AccessToken": "",
    "ExpiresIn": 3600,
    "IdToken": "",
    "RefreshToken": "",
    "Scope": "offline_access openid",
    "TokenType": "Bearer"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ValidationMessageTwoException`](../../doc/models/validation-message-two-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessage1Exception`](../../doc/models/internal-server-message-1-exception.md) |


# Forgot Password

Okta forgot password

:information_source: **Note** This endpoint does not require authentication.

```python
def forgot_password(self,
                   body)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ForgotPasswordInputModel`](../../doc/models/forgot-password-input-model.md) | Body, Required | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ForgotPasswordOutputModel`](../../doc/models/forgot-password-output-model.md).

## Example Usage

```python
body = ForgotPasswordInputModel(
    email='abc@abc.com'
)

result = auth_api.forgot_password(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "success": true
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ValidationMessageTwoException`](../../doc/models/validation-message-two-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessage1Exception`](../../doc/models/internal-server-message-1-exception.md) |


# Change Password

Okta forgot password

:information_source: **Note** This endpoint does not require authentication.

```python
def change_password(self,
                   body)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ChangePasswordInputModel`](../../doc/models/change-password-input-model.md) | Body, Required | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChangePasswordOutputModel`](../../doc/models/change-password-output-model.md).

## Example Usage

```python
body = ChangePasswordInputModel(
    email='abc@abc.com',
    old_password='oldpass@#&7',
    new_password='newpass@#&7'
)

result = auth_api.change_password(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "success": true
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ValidationMessageTwoException`](../../doc/models/validation-message-two-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessage1Exception`](../../doc/models/internal-server-message-1-exception.md) |


# Refresh Token

Okta refresh token

:information_source: **Note** This endpoint does not require authentication.

```python
def refresh_token(self,
                 body)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`RefreshTokenInputModel`](../../doc/models/refresh-token-input-model.md) | Body, Required | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RefreshTokenOutputModel`](../../doc/models/refresh-token-output-model.md).

## Example Usage

```python
body = RefreshTokenInputModel(
    refresh_token='HEpb6yNYH68XTFING3a_RkqLHOgFosQv5-7W0_So3VE'
)

result = auth_api.refresh_token(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "AuthenticationResult": {
    "TokenType": "Bearer",
    "ExpiresIn": 3600,
    "AccessToken": "",
    "Scope": "offline_access openid",
    "RefreshToken": "",
    "IdToken": ""
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`RefreshTokenStatusException`](../../doc/models/refresh-token-status-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessage1Exception`](../../doc/models/internal-server-message-1-exception.md) |


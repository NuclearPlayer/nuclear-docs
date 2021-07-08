---
description: How to authenticate with the services
---

# Authentication

The identity service allows you to sign up to create an account, and sign to receive an authentication token that can be used to authenticate with all Nuclear web services. Those are regular JWTs.

{% api-method method="post" host="/signup" path="" %}
{% api-method-summary %}
Sign up
{% endapi-method-summary %}

{% api-method-description %}
This method allows the user to create a new account.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="password" type="string" required=true %}
Must be at least 6 characters long. Stored in a hashed and salted form.
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Must be a valid email. It will be used for account confirmation and for sending forgotten password emails.
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
Username. Has a minimum length of 4 characters. The username cannot be changed later, but it will be used to set an initial `displayName`  which will be displayed to other users, and can be changed at any time.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
In case of success
{% endapi-method-response-example-description %}

```
{
    "username": "testUser",
    "displayName": "testUser",
    "email": "test@example.com"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="/signin" path="" %}
{% api-method-summary %}
Sign in
{% endapi-method-summary %}

{% api-method-description %}
This method allows the user to sign in and receive an authentication token.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="password" type="string" required=false %}
Current password.
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
Username used for signing up.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


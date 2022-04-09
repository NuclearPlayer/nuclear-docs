---
description: How to authenticate with the services
---

# Authentication

The identity service allows you to sign up to create an account, and sign to receive an authentication token that can be used to authenticate with all Nuclear web services. Those are regular JWTs.

{% swagger baseUrl="/signup" path="" method="post" summary="Sign up" %}
{% swagger-description %}
This method allows the user to create a new account.
{% endswagger-description %}

{% swagger-parameter in="body" name="password" type="string" %}
Must be at least 6 characters long. Stored in a hashed and salted form.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="string" %}
Must be a valid email. It will be used for account confirmation and for sending forgotten password emails.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
Username. Has a minimum length of 4 characters. The username cannot be changed later, but it will be used to set an initial 

`displayName`

  which will be displayed to other users, and can be changed at any time.
{% endswagger-parameter %}

{% swagger-response status="201" description="In case of success" %}
```
{
    "username": "testUser",
    "displayName": "testUser",
    "email": "test@example.com"
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="/signin" path="" method="post" summary="Sign in" %}
{% swagger-description %}
This method allows the user to sign in and receive an authentication token.
{% endswagger-description %}

{% swagger-parameter in="body" name="password" type="string" %}
Current password.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
Username used for signing up.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

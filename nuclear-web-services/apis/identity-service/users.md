# /users

{% swagger baseUrl="" path="/users/:id" method="get" summary="Get user" %}
{% swagger-description %}
Retrieves a user.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
User uuid
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  id: string;
  username: string;
  displayName: string;
  email: string;
}
```
{% endswagger-response %}
{% endswagger %}


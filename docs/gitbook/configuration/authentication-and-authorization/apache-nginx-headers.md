# Plain-Text Headers

Perhaps you already have a homegrown solution that will authenticate your users, like an Apache or Nginx module. ConsoleMe can be configured to extract a user and their groups from plain text headers provided by these modules.

{% hint style="warning" %}
These headers are sensitive, and you'll need to ensure the web server that you have in front of ConsoleMe drops these headers if the user passes them with their request
{% endhint %}

ConsoleMe expects the groups header to be a comma separated list of the user's groups.

We have an example configuration [here](https://github.com/Netflix/consoleme/blob/master/example_config/example_config_alb_auth.yaml).

```text
auth:
  get_groups_by_header: true
  get_user_by_header: true
  groups_header_name: group_header
  user_header_name: user_header
```

 

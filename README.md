# About

_Extracted from [pay-per-task.com](http://pay-per-task.com)_.

TODO

# Features

- Highlights any paragraph containing the word 'TODO'.

# Installation

```
# Assuming you're in the top-level repository:
bower install botanicus/doxxu
```

## Nginx Vhost

Doxxu is just a very simple AngularJS app, you can serve it with anything you want. Let's use Nginx for our example:

```nginx
server {
  listen 80;
  server_name docs.pay-per-task.dev;

  # This returns HTTP 200 on any route and serves app.html.
  # Useful for HTML5 routing in AngularJS.
  error_page 404 = /app.html;

  location / {
    index app.html;
    root /webs/ppt/webs/docs.pay-per-task.com/bower_components/doxxu;
  }

  location /source {
    alias /webs/ppt;

    # Serve it as plain text.
    default_type 'text/plain';
  }
}
```

# TODO

- I want to be able to use ng-include
<div ng-include="/source/webs/api.pay-per-task.com/puma.config.rb">
</div>
- Integrate subl:// to open files.
- Instead of using two subdomains, use just one. Code shall live on `/source/:path`. By doing so we can also eliminate the SCE whitelist.
- Come up with production settings (authentication etc).
- Make it OSS.
- Make it installable through Bower?
- Add it as a submodule OR install through Bower.
- Handling non-existing files like http://docs.pay-per-task.dev/docs/i-do-not-exist.md

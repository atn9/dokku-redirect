# dokku-redirect

dokku-redirect is a plugin for [dokku][dokku] that gives the ability to set simple redirects for an application.

This plugin only redirects one domain to another and does not handle complete URLs. If both domains are managed by dokku and are TLS enabled, then nginx configuration for https redirects will be handled automatically.

## Installation

```sh
# dokku 0.3.26
$ sudo git clone https://github.com/dokku/dokku-redirect.git /var/lib/dokku/plugins/redirect
$ dokku plugins-install

# dokku 0.4+
$ dokku plugin:install https://github.com/dokku/dokku-redirect.git
```

## Commands

```
$ dokku help
    redirect <app>                            Display the redirects set on app
    redirect:set <app> <source> <destination> Set a redirect from <source> domain to <destination> domain
    redirect:unset <app> <source>             Unset a redirect from <source>
```

## Usage

Check redirects on my-app
```shell
$ dokku redirect my-app

SOURCE       DESTINATION
ma.dokku.me  my-app.dokku.me
```

Set a new redirect on my-app
```shell
$ dokku redirect:set my-app ma.dokku.me my-app.dokku.me

-----> Setting redirect for my-app...
       done
```

Unset an existing redirect
```shell
$ dokku redirect:unset my-app ma.dokku.me

-----> Unsetting redirect for my-app...
       done
```

## License

This plugin is released under the MIT license. See the file [LICENSE](LICENSE).

[dokku]: https://github.com/progrium/dokku

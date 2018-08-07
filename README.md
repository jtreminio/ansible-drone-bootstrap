# Ansible + Drone bootstrap

Configures an existing server. Installs Docker, Docker Compose, Traefik Proxy.

Installs [Drone](https://drone.io/).

* Copy `.env.dist` to `.env`
* Set all values
* Run `./init`

If `SERVER_IP` is set, Drone is setup on the single server.

Else if `SERVER_BLOG_IP` and `SERVER_DRONE_IP` are set,
Drone is installed on `SERVER_DRONE_IP`.

All servers will have Docker and Docker Compose installed.

All servers will have [Traefik Proxy](https://traefik.io/) installed.

`LE_EMAIL` is used for automatic Let's Encrypt certificates.

`BLOG_HOST` is blog URL. Your DNS should already point to your server.

`DRONE_HOST` is drone URL. Your DNS should already point to your server.

Drone requires Github API credentials.
[Generate new OAuth App credentials](https://github.com/settings/developers)
and populate `DRONE_GITHUB_CLIENT` and `DRONE_GITHUB_SECRET`.

`DRONE_SECRET` is the shared secret between Drone server and Agent(s) and
allows them to connect to each other automatically.

A Let's Encrypt SSL cert will automatically be generated for both `BLOG_HOST`
and `DRONE_HOST`.

Full blog post on usage
[can be found here](https://jtreminio.com/blog/setting-up-a-static-site-with-hugo-and-push-to-deploy-from-scratch).

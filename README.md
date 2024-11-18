# ghost-docker

Host the [Ghost publishing platform](https://ghost.org) using
[Docker Compose](https://docs.docker.com/compose/). This project
has the following goals:

- Run as microservices, not monolithic containers
- Use least privilege for security
- SSL enabled automatically using [Let's Encrypt](https://letsencrypt.org)
- Serve static content directly
- Don't Repeat Yourself (DRY)
- Don't embed or hard-code passwords

This runs 3 services using the official Docker images:

- Ghost software
- Caddy, as a web proxy and static content
- MySQL to power Ghost

## Instructions:

### Quickstart

1. Clone this repository
2. Create a .env file with your configuration data
3. Run: docker compose up -d
4. There is no step 4 ;)

### Configuration fields

| Field | Required | Description |
| --- | ----- | ---- |
| URL | Yes | The URL to your Ghost instance; if you use a non-default port, you must specify it here, ex: http://192.168.32.100:8080 |
| MYSQL\_ROOT\_PASSWORD | Yes | The root password for MySQL |
| MYSQL\_USER\_PASSWORD | Yes | The password that ghost will use to connect to MySQL |
| EMAIL\_ADDRESS | Yes | The email address for Ghost email and SSL verification |
| EMAIL\_SERVICE | Yes | A name to describe the email service you use |
| EMAIL\_HOST | Yes | Address of the email SMTP server |
| EMAIL\_PORT | No | Port name for SMTP server (default: 587) |
| EMAIL\_USER | Yes | User name for SMTP server |
| EMAIL\_PASSWORD | Yes | Password name for SMTP server |
| HTTP\_PORT | No | Specify the port for HTTP (default: 80) |
| HTTPS\_PORT | No | Specify the port for HTTPS (default: 443) |

### Configuration for local development

By default, Caddy will use Let's Encrypt to create and update a SSL certificate.
However, this can be an issue if you are running on a local system that is
not exposed to the internet. In this case, use http in the URL field.

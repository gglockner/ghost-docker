# Host Ghost blogging platform using Docker

## Goals for this project
- Host Ghost via Docker Composer
- System built as microservices, not monolithic containers
- SSL enabled by default
- Serve static content directly
- Don't Repeat Yourself (DRY)
- Don't embed or hard-code passwords
- Least privilege

## HOWTO
TODO

## Stack used
- Docker composer
- Ghost
- Caddy
- MySQL

## TODO
- make/configure instructions/script/howto
- Publish to Github with license

## Done
- Serve static content
- SSL
- Let's Encrypt certificate
- Cleanup
- Dev instance where SSL is optional: use URL as http instead of https
- Handle unprivileged ports (e.g. 8080) on Caddy: set HTTP\_PORT or HTTPS\_PORT
- Test new instance
- Configure email for AWS SES

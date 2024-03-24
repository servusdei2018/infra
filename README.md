# infra

Collection of scripts/playbooks for managing my cloud infrastructure.

## Getting Started

Although these playbooks were created for original use, they may be easily repurposed for use elsewhere.

To get up and running, populate `servers_example.yml` with your server information, rename it to `servers.yml` and run

```shell
$ ansible-playbook -i servers.yml ./playbooks/update_apt.yml
```

to initiate an apt update and upgrade on all of your servers.

## Playbooks

- **update_apt.yml**: performs an apt upgrade on all servers, rebooting each system if necessary

- **update_bot.yml**: updates *Werewolf* with the latest source for [elmobot](https://github.com/servusdei2018/elmobot) from the Git repository, builds it, and restarts the elmobot service

- **update_site.yml**: updates *Vampire* with the latest static content for [bracy.dev](https://bracy.dev) from the Git repository, and restarts the caddy service

## Assets

Each server is catalogued below. Additionally and more importantly, each server is defined in `servers.yml` so that Ansible may deal with them appropriately.

> [!NOTE]
> The actual IP addresses of my servers were redacted from `servers_example.yml`, as well as the Ansible login user.

For ease of administration, all servers currently run Ubuntu 22.04 LTS. Playbooks take this into account, and if you're running another distro you will need to account for differences accordingly.

### Cyclops

```
Specs:
  - 4 cores (aarch64)
  - 24 GB RAM
  - 100 GB storage
  - Ubuntu 22.04 LTS

Services:
  - Cloud Development Environment
  - Flutter Toolchain
  - Go Toolchain
  - Rust Toolchain
```

### Vampire

```
Specs:
  - 1 core (amd64)
  - 1 GB RAM
  - 50 GB storage
  - Ubuntu 22.04 LTS

Services:
  - Caddy (personal website)
```

### Werewolf

```
Specs:
  - 1 core (amd64)
  - 1 GB RAM
  - 50 GB storage
  - Ubuntu 22.04 LTS

Services:
  - Elmobot (personal Discord bot)
  - Go toolchain
```

## License

```
The MIT License (MIT)

Copyright (c) 2024-present Nathanael Bracy

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```
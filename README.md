# decK: Declarative configuration for Kong

decK is a CLI tool to configure Kong declaratively using a single config file.

[![Build Status](https://travis-ci.com/hbagdi/deck.svg?branch=master)](https://travis-ci.com/hbagdi/deck)

[![asciicast](https://asciinema.org/a/238318.svg)](https://asciinema.org/a/238318)

## Table of Content

- [**Features**](#features)
- [**Compatibility**](#compatibility)
- [**Roadmap**](#roadmap)
- [**License**](#license)

## Features

- **Export**  
  Exisitng Kong configuration to a YAML configuration file
  This can be used to backup Kong's configuration.
- **Import**  
  Kong's database can be populated using the exported or a hand written config
  file.
- **Diff and sync capabilities**  
  decK can diff the configuration in the config file and
  the configuration in Kong's DB and then sync it as well.
  This can be used to detect config drifts or manual interventions.
- **Reverse sync**:  
  decK supports a sync the other way as well, meaning if an
  entity is created in Kong and doesn't add it to the config file,
  decK will detect the change.
- **Reset**  
  This can be used to drops all entities in Kong's DB.
- **Parallel operations**  
  All Admin API calls to Kong are executed in parallel using threads to
  speed up the sync.
- **Supported entities**
  - Routes and services
  - Upstreams and targets
  - Certificates and SNIs
  - Consumers
  - Plugins (Global, per route, per service and per consumer)
- **Authentication with Kong**
  Custom HTTP headers can be injected in requests to Kong's Admin API
  for authentication/authorization purposes.
- **Manage Kong's config with multiple config file**
  Split your Kong's configuration into multiple logical files based on a shared
  set of tags amongst entities.

## Compatibility

decK is compatible with Kong 1.x.

## Roadmap

- Default attributes
  Support filling in defaults for configs of plugins
  for cases when the config file doesn't contain the attribute.
- Complete end to end integration tests with Kong.
- Add support for credentials in Kong
- Certificate encryption  
  Support in decK to fetch certificate from Vault or a cloud
  secret storage and then sync it to Kong.

## License

decK is licensed with Apache License Version 2.0. Please read the LICENSE
file for more details.

# rs-collector

[![Build Status](https://travis-ci.org/lukaspustina/rs-collector.svg?branch=master)](https://travis-ci.org/lukaspustina/rs-collector)

## Todo

- [x] Fix memory leak in chan::tick
  cf. [https://github.com/BurntSushi/chan/issues/11](https://github.com/BurntSushi/chan/issues/11) and branch mem_leak_chan_tick.

  This is known behaviour of chan::tick. The memory leak led to 236 KB allocated memory during 64 hours. That doesn't hurt too much especially because we plan to restart the process every 24 because of log rotation. Skipping this for now.

- [x] Transform all wsrep values to metrics
- [x] Add metadata for all wsrep values
- [x] Check additional state for metrics
- [x] Handle tags
- [x] Automate packaging for Ubuntu
  - [x] Ansible Role
  - [x] Update Readme: Link to package and Ansible role
- [ ] Failure Modes
  - [x] Reinitialize collector if collection fails.
    - [x] Reconnect Logic for Galera Collector
  - [ ] Remove collector if too many collection failures.
  - [ ] Remove collector collection thread does not respond anymore.
  - [ ] Remove collector collection thread does not respond anymore.
- [ ] Add timestamps to log messages
- [ ] Tests
- [ ] Fix Todos
- [ ] Extend bosun_emitter to send multiple data points
- [ ] Support multiple Galera Collectors -- also change in Ansible role
- [ ] Add internal metrics `rs-collector.*`


## Releases

Travis CI creates Ubuntu Trusty packages for each release. Please see the [Repository](https://packagecloud.io/lukaspustina/opensource) for details.

## Installation

There is also an Ansile role available at [Ansible Galaxy](https://galaxy.ansible.com/Rheinwerk/rs_collector/) that automates the installation of rs-collector.


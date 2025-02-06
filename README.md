# The Whale Of The Night

[![Build Status](https://travis-ci.com/travis-ci/nightwhale.svg?branch=master)](https://travis-ci.com/travis-ci/nightwhale)

Nightly build docker stuff, specifically for use with things at Travis via
[packer-templates](https://github.com/travis-ci/packer-templates).

## How, specifically

- This repository is enabled on
  [travis-ci.com](https://travis-ci.com/travis-ci/nightwhale) with nightly
(daily) cron builds.
- When a given job succeeds, and is on the `master` branch, and is not a pull
  request job, the resulting docker image is pushed to [Docker
Hub](https://hub.docker.com/r/travisci/).
- The generated images are used as the `FROM` image during docker (packer)
  builds of higher-level images, mostly as a way of saving time by cutting down
on duplicate work.

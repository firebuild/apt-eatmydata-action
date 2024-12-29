# APT eatmydata for GitHub Actions

A GitHub Action to speed up package installation using
[eatmydata](https://manpages.debian.org/testing/eatmydata/eatmydata.1.en.html).

Works on Ubuntu, Debian, and other Debian derivatives.

## Usage

```yaml
jobs:
  myjob: 
    steps:
    - uses: firebuild/apt-eatmydata-action@v1
    ...
```

## How it works

The action installs eatmydata and configures APT to wrap dpkg calls with eatmydata.

This way dpkg does not perform `fsync()` calls which would slow down package installation significantly.

To speed up the build as well, you may want to take a look at the [Firebuild Action](https://github.com/marketplace/actions/firebuild-for-github-actions).

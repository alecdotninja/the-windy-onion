# The Windy Onion

This repository contains information about [TheWindyOnion](https://metrics.torproject.org/rs.html#details/89094DFA4158C7A1583EC3A332CDCBC74A28CC0E) (a high-capacity [Tor relay](https://2019.www.torproject.org/about/overview.html.en#overview) in Chicago, IL).
At the time of this writing, it is one of [the top exit nodes in the US](https://metrics.torproject.org/rs.html#search/flag:exit%20country:us).

My goal in making this information public is that others may setup their own relays using this configuration as a starting point and suggest improvements.

## Hardware

The Windy Onion is a 1U [Supermicro X10SLH-LN6TF](https://www.supermicro.com/en/products/motherboard/X10SLH-F) with an [Intel Xeon E3-1270v3](https://ark.intel.com/content/www/us/en/ark/products/75056/intel-xeon-processor-e3-1270-v3-8m-cache-3-50-ghz.html) running at 3.5 GHz (with hyperthreading _disabled_) and 32 Gb of RAM.

## Operating System

In order to support more diversity among relays, The Windy Onion runs [FreeBSD 12.1](https://www.freebsd.org/).

## Packages

Tor and [Nyx](https://nyx.torproject.org/) (a monitoring tool for Tor) are both installed and updated via the built-in package manager `pkg`:

  $ sudo pkg install tor nyx

  $ sudo pkg update
  $ sudo pkg upgrade

## Configuration

With the notable exception of key and login information, files which have been customized from their default are included in this repository. Of particular interest to other FreeBSD operators is probably [torrc](usr/local/etc/tor/torrc) and [sysctl.conf](etc/sysctl.conf).

## Deployment

Currently, all deployments must be performed manually by [me](https://keybase.io/alecdotninja); however, it should be possible to automate this process with [TravisCI](https://travis-ci.org).

## Contributing

Bug reports and pull requests are welcome on [GitHub](https://github.com/PrivacyInPractice/the-windy-onion).

## License

The contents of this repository is [released into the public domain](LICENSE).

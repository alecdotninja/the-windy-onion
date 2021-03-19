# The Windy Onion
[![Deployment Status](https://img.shields.io/travis/alecdotninja/the-windy-onion?label=Deployment)](https://travis-ci.org/alecdotninja/the-windy-onion)
[![Tor Relay Status](https://img.shields.io/badge/Tor%20Relay-89094DFA4158C7A1583EC3A332CDCBC74A28CC0E-%237d4698)](https://metrics.torproject.org/rs.html#search/family:89094DFA4158C7A1583EC3A332CDCBC74A28CC0E)

This repository contains information about [TheWindyOnion](https://metrics.torproject.org/rs.html#search/family:89094DFA4158C7A1583EC3A332CDCBC74A28CC0E) (a high-capacity [Tor relay](https://2019.www.torproject.org/about/overview.html.en#overview) in Chicago, IL).
At the time of this writing, it is one of [the fastest exit nodes in the US](https://metrics.torproject.org/rs.html#search/flag:exit%20country:us).

My goal in making this information public is that others may setup their own relays using this configuration as a starting point and suggest improvements.

## Hardware

The Windy Onion is a custom-built 1U with the following components:

* Case (1U): [iStarUSA D-118V2-ITX](https://www.newegg.com/black-istarusa-d-118v2-itx/p/N82E16811165402)
* IO Shield: [Universal IO shield for PLINKUSA RACKBUY 1U chassis](https://www.amazon.com/gp/product/B01L0D7JMC)
* Power Supply (250W): [FSP Flex Guru 250-50FGBBI(M)](https://www.newegg.com/p/1HU-0095-000J6)
* Case Fans (x2): [Noctua NF-A4x10](https://www.newegg.com/p/13K-001X-000E3)
* CPU (6-Core @ 3.7 GHz): [AMD Ryzen 5 5600X](https://www.newegg.com/amd-ryzen-5-5600x/p/N82E16819113666)
* CPU Fan: [Dynatron A18](https://www.newegg.com/dynatron-a18/p/N82E16835114143)
* Motherboard: [GIGABYTE A520I AC](https://www.newegg.com/gigabyte-a520i-ac/p/N82E16813145239)
* RAM (32GB): [Crucial 32GB (2 x 16GB) 288-Pin DDR4](https://www.newegg.com/crucial-32gb-288-pin-ddr4-sdram/p/N82E16820156267)
* NIC (4 x 1GigE): [Intel EXPI9404PTL PT](https://www.newegg.com/intel-expi9404ptl/p/N82E16833106019)
* PCIe Riser: [Asiahorse PCIe 3.0 16x Flexible Extension Riser](https://www.newegg.com/p/1W7-00AB-00011) 

## Operating System

In order to support [more diversity among relays](https://nusenu.github.io/OrNetStats/#os-distribution-relays), The Windy Onion runs [FreeBSD 12.1](https://www.freebsd.org/).

At this time, updates are applied manually:

    $ sudo freebsd-update fetch
    $ sudo freebsd-update install

## Packages

Tor and [Nyx](https://nyx.torproject.org/) (a monitoring tool for Tor) are both installed via the built-in package manager `pkg`:

    $ sudo pkg install tor nyx

At this time, updates are applied manually:

    $ sudo pkg update
    $ sudo pkg upgrade

## Configuration

With the notable exception of key and login information, files which have been customized from their default are included in this repository. Of particular interest to other FreeBSD operators is probably [torrc](overlay/usr/local/etc/tor/torrc) and [sysctl.conf](overlay/etc/sysctl.conf).

## Deployment

The latest `master` is automatically deployed by [TravisCI](.travis.yml).

Run `script/deploy` to perform the deployment locally (this requires a [deploy key](secrets)).

## Contributing

Bug reports and pull requests are welcome on [GitHub](https://github.com/alecdotninja/the-windy-onion).

## License

The contents of this repository is [released into the public domain](LICENSE).

# block

A collection of domains, wildcards and substrings designed for [`dnscrypt-proxy`](https://github.com/DNSCrypt/dnscrypt-proxy) filter method.

- __allowed-names.txt:__ it's the file used to bypass a specific domain blocked by a rule contained in the `blocked-names.txt` file.
- __domains-blocklist.conf:__ it's used to configure the sources to merge during the build process.
- __domains-blocklist-local-additions.txt:__ it's used during the generation process to add your own additions and remove duplicates from the sources.
- __domains-allowlist.txt:__ it's used during the generation process to remove legit domains.
- __generate-domains-blocklist.py:__ it's the script used to launch the build process.

## Sources

Updated sources from the following locations are always merged and included.

#### blocked-names.txt

| Source | Maintainer(s) | Description | Home Page | RAW Source | License |
|--------|:-------------:|-------------|:---------:|:----------:|:-------:|
1Hosts: Xtra - Level 4 | badmojr | A merged list from a variety of other lists. | [LINK](https://github.com/badmojr/1Hosts) | [RAW](https://raw.githubusercontent.com/badmojr/1Hosts/master/Xtra/domains.wildcards) | [MPL-2.0](https://github.com/badmojr/1Hosts/blob/master/LICENSE) |
Developer Dan: Ads & Tracking | Daniel (lightswitch05) | Block advertisements and tracking. | [LINK](https://github.com/lightswitch05/hosts) | [RAW](https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt) | [Apache-2.0](https://github.com/lightswitch05/hosts/blob/master/LICENSE) |
Developer Dan: AMP Hosts | Daniel (lightswitch05) | Block Google's Accelerated Mobile Pages (AMP). | [LINK](https://github.com/lightswitch05/hosts) | [RAW](https://www.github.developerdan.com/hosts/lists/amp-hosts-extended.txt) | [Apache-2.0](https://github.com/lightswitch05/hosts/blob/master/LICENSE) |
domains-blocklist-local-additions.txt | quindecim | Domains, wildcards and substrings collection. | [LINK](https://codeberg.org/quindecim/block) | [RAW](https://codeberg.org/quindecim/block/raw/branch/master/config/domains-blocklist-local-additions.txt) | [GPLv3](https://codeberg.org/quindecim/block/src/branch/master/LICENSE.md) |
domains-allowlist.txt | quindecim | Legit domains collection. | [LINK](https://codeberg.org/quindecim/block) | [RAW](https://codeberg.org/quindecim/block/raw/branch/master/config/domains-allowlist.txt) | [GPLv3](https://codeberg.org/quindecim/block/src/branch/master/LICENSE.md) |
Energized Protection: Regional Extension | Team Boltz | Regional annoyance blocking. | [LINK](https://energized.pro/) | [RAW](https://block.energized.pro/extensions/regional/formats/domains.txt) | [MIT](https://github.com/EnergizedProtection/block/blob/master/LICENSE) |
Energized Protection: Xtreme Extension | Team Boltz | Privacy protection at its best. | [LINK](https://energized.pro/) | [RAW](https://block.energized.pro/extensions/xtreme/formats/domains.txt) | [MIT](https://github.com/EnergizedProtection/block/blob/master/LICENSE) |
Geoffrey Frogeye: First-party trackers | Geoffrey Frogeye | First-party trackers blocklist | [LINK](https://hostfiles.frogeye.fr/) | [RAW](https://hostfiles.frogeye.fr/multiparty-trackers.txt) | [MIT](https://git.frogeye.fr/geoffrey/eulaurarien/src/branch/master/LICENSE) |
GoodbyeAds | jerryn70 | A merged list from a variety of other lists. | [LINK](https://github.com/jerryn70/GoodbyeAds) | [RAW](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds.txt) | [MIT](https://github.com/jerryn70/GoodbyeAds/blob/master/LICENSE) |
hBlock | Héctor Molinero Fernández (hectorm) | A merged list from a variety of other lists. | [LINK](https://github.com/hectorm/hblock) | [RAW](https://hblock.molinero.dev/hosts_domains.txt) | [MIT](https://github.com/hectorm/hblock/blob/master/LICENSE.md) |
NoTracking | notracking | A merged list from a variety of other lists. | [LINK](https://github.com/notracking/hosts-blocklists) | [RAW](https://raw.githubusercontent.com/notracking/hosts-blocklists/master/dnscrypt-proxy/dnscrypt-proxy.blacklist.txt) | All Rights Reserved |
OISD: full | Stephan (sjhgvr) | A merged list from a variety of other lists. | [LINK](https://oisd.nl/) | [RAW](https://dbl.oisd.nl/) | All Rights Reserved |
OISD: extra | Stephan (sjhgvr) | OISD's controversial domains list. | [LINK](https://oisd.nl/) | [RAW](https://dbl.oisd.nl/extra/) | All Rights Reserved |
Oneoffdallas: DoH Servers List | oneoffdallas | A list of publicly available DNS over HTTPS (DoH) servers. | [LINK](https://github.com/oneoffdallas/dohservers) | [RAW](https://raw.githubusercontent.com/oneoffdallas/dohservers/master/list.txt) | [MIT](https://github.com/oneoffdallas/dohservers/blob/master/LICENSE) |

#### blocked-ips.txt

| Source | Maintainer(s) | Description | Home Page | RAW Source | License |
|--------|:-------------:|-------------|:---------:|:----------:|:-------:|
DNSCrypt: Rebind Protection | jedisct1 | DNS rebinding protection | [LINK](https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Filters#dns-rebinding-protection) | - | [ISC](https://github.com/DNSCrypt/dnscrypt-proxy/blob/master/LICENSE) |

## Build

To generate your own list you can clone this repo, move into the `config` folder, edit files according to your needs and run this command:
```
python3 generate-domains-blocklist.py > list.txt.tmp && mv -f list.txt.tmp list
```
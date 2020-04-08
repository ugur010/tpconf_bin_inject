# tpconf_bin_inject.py
Simple command line utility to inject and enable root credentials on some TP-Link modem router backup config files from binary to XML and back:
- conf.bin => decrypt, md5hash, uncompress, inject, compress, md5hash, encrypt => outconf.bin

# [tpconf_bin_xml.py](https://github.com/sta-c0000/tpconf_bin_xml)

Please visit the original repository at [https://github.com/sta-c0000/tpconf_bin_xml](https://github.com/sta-c0000/tpconf_bin_xml) for more information.

Simple command line utility to convert TP-Link TD-W9970 and TD-W9980 (_thanks to [d3dave](https://github.com/d3dave)_) modem router backup config files from binary to XML and back:
- conf.bin ➡ decrypt, md5hash and uncompress ➡ conf.xml
- conf.xml ➡ compress, md5hash and encrypt ➡ conf.bin

*May or may not work with other TP-Link modem / routers (not tested)*

## Prerequisites

- Python 3.x
- pycrypto
  - `sudo apt-get install python3-crypto`
  - *OR* `pip install pycrypto`
  - *OR* `pip install pycryptodome`
    - Try `pip3` if your default Python setup is on 2.x.
    - On Windows, usage of `py -3 -m pip` is encouraged.

## Getting Started (with tpconf_bin_inject.py)

Single python file, download, optionally `chmod +x`, and run.

First, download a backup conf.bin file from your router using its web interface (System Tools → Backup & Restore → Backup).
```sh
[python3] tpconf_bin_inject.py -h
[python3] tpconf_bin_inject.py conf.bin # that long chain of operations I mentioned above
```

The `outconf.bin` file will have a `root` account enabled with the password `root`.

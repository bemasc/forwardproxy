# How to Contribute

We'd love to accept your patches and contributions to this project. There are
just a few small guidelines you need to follow.

## Contributor License Agreement

Contributions to this project must be accompanied by a Contributor License
Agreement. You (or your employer) retain the copyright to your contribution,
this simply gives us permission to use and redistribute your contributions as
part of the project. Head over to <https://cla.developers.google.com/> to see
your current agreements on file or to sign a new one.

You generally only need to submit a CLA once, so if you've already submitted one
(even if it was for a different project), you probably don't need to do it
again.

## Code reviews

All submissions, including submissions by project members, require review. We
use GitHub pull requests for this purpose. Consult
[GitHub Help](https://help.github.com/articles/about-pull-requests/) for more
information on using pull requests.

# Testing on Mac OS

The unit tests for `forwardproxy` require access to some IPv4 loopback addresses,
which are disabled by default on Mac OS.  To enable them run:

```sh
declare -a FORWARDPROXY_TEST_IPS=(
    "127.0.19.84"
    "127.0.69.73"
    "127.0.88.88"
    "127.0.99.99"
    "127.0.64.51"
    "127.0.65.25"
    "127.0.87.76"
    "127.0.66.76"
)

for ip in "${FORWARDPROXY_TEST_IPS[@]}"
do
    sudo ifconfig lo0 alias "${ip}" up
done
```

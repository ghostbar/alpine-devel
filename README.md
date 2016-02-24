Hub for all my alpine-pkg stuff
===============================

WHY?
----
I have several alpine related repos and thought it would be good to centralize
what are they and how to use them.

WHAT?
-----

+ [`resnullius/docker-alpine`](#resnulliusdocker-alpine)
+ [`resnullius/docker-alpine-devel`](#resnulliusdocker-alpine-devel)
+ [`resnullius/alpine-devel-howto`](#resnulliusalpine-devel-howto)
+ [`resnullius/alpine-pkg-orchestrator`](#resnulliusalpine-pkg-orchestrator)
+ [`alpine-pkg-nodejs`](#alpine-pkg-nodejs)
+ [`alpine-pkg-nodejs-lts`](#alpine-pkg-nodejs-lts)
+ [`alpine-pkg-radare2`](#alpine-pkg-radare2)


TIRED OF GETTING UNTRUSTED SIGNATURE
------------------------------------

My key is in this repository, it's called `me@ghostbar.co-56c80129.rsa.pub` and
adding it to your `/etc/apk/keys` will remove the need to add
`--allow-untrusted` while installing the packages built on my repos.

<a href="#resnullius-docker-alpine"></a>
RESNULLIUS/DOCKER-ALPINE
------------------------

I wanted to have nice reproducible alpine images for my `armv7l` devices, and
ended up making so much changes to
[`gliderlabs/alpine`](https://github.com/gliderlabs/alpine) that I made a fork
and published it. The major difference besides `armv7l` support is that is
organized very differently and right now just the builder looks similar to the
original from `gliderlabs/alpine`. The `edge` tags are built daily for `armv7l`
and `x86_64`.

The repositories and docs on how to use it are at
[`resnullius/docker-alpine`](https://github.com/resnullius/docker-alpine)

<a href="#resnullius-docker-alpine-devel"></a>
RESNULLIUS/DOCKER-ALPINE-DEVEL
------------------------------

I love to make packages for alpine, it ends up being the lightest way to get
applications into alpine, so I needed a reliable way to build them for different
versions and quick. So this project: be born 🌄. It spits a ready to be published
repo with signed `APKINDEX.tar.gz` which makes easier the distribution.

It depends on
[`resnullius/docker-alpine`](https://github.com/resnullius/docker-alpine) so
that means it can build packages in `armv7l` and `x86_64`. Ain't that nice? The
`edge` tags are built daily for `armv7l` and `x86_64`.

The repositores and docs on how to use it are at
[`resnullius/docker-alpine-devel`](https://github.com/resnullius/docker-alpine-devel),
but the best way to use it is just in the next title ;-).

<a href="#resnullius-alpine-devel-howto"></a>
RESNULLIUS/ALPINE-DEVEL-HOWTO
-----------------------------

What good makes a tool without an easy way to use it? I wrote a script that you
put in your `~/bin/` and it builds the packages like magic for you. You just
need to change the `APKBUILD` and run it. That's all. It's quite well documented
and I'm improving constantly it since I use it a lot.

The repository is on
[`resnullius/alpine-devel-howto`](https://github.com/resnullius/alpine-devel-howto)
and the `README` works as the main documentation point, tho the script itself
spits lots of info with the `--help`.

With this is that I build the packages on the list below.

<a href="#resnullius-alpine-pkg-orchestrator"></a>
RESNULLIUS/ALPINE-PKG-ORCHESTRATOR
----------------------------------

I wanted to build everything at the same time, so I made this little script in
order to reproduce, easily, what I've made with alpine-pkg-nodjs and
alpine-pkg-nodejs-lts using the `alpine-build-pkg` script from
[`resnullius/alpine-devel-howto`](https://github.com/resnullius/alpine-devel-howto).

The repository is on
[`resnullius/alpine-pkg-orchestrator`](https://github.com/resnullius/alpine-pkg-orchestrator)
and the `README` works as the main documentation point and the `--help` on the
script itself.

<a href="#alpine-pkg-nodejs"></a>
ALPINE-PKG-NODEJS
-----------------

I use nodejs a lot, and you can't get the stable version on the repos for 3.2
and 3.3; so why not build a repo for it? Here it is, it comes with the
corresponding `libuv` package in the version that supports.

The repo is at
[`ghostbar/alpine-pkg-nodejs`](https://github.com/ghostbar/alpine-pkg-nodejs).

<a href="#alpine-pkg-nodejs-lts"></a>
ALPINE-PKG-NODEJS-LTS
---------------------

And getting the correct version of nodejs when you want LTS can be hard,
sometimes. So this repository corrects this fact, delivering the same version
over all the alpine versions available (from 3.2).

The repo is at
[`ghostbar/alpine-pkg-nodejs-lts`](https://github.com/ghostbar/alpine-pkg-nodejs-lts).

ALPINE-PKG-RADARE2
------------------

Get the latest [`radare2`](http://www.radare.org) even if you are not using
`edge`!

The repo is at
[`ghostbar/alpine-pkg-radare2`](https://github.com/ghostbar/alpine-pkg-radare2).

=======
py-ipfs
=======

.. image:: ipfs.png
    :alt: IPFS Logo
    :align: center

.. _shields:

|made-by-shield| |project-shield| |freenode-shield| |readme-shield| |gitter-shield|

  python implementation of ipfs

Python implementation of IPFS, the InterPlanetary File System.
Not even remotely done yet - check out `this discussion <https://github.com/ipfs/py-ipfs/issues/1>`_
to join the project.

.. contents:: Table of Contents

Background
----------
IPFS is a distributed file system that seeks to connect all computing devices
with the same system of files.
In some ways, this is similar to the original aims of the Web, but IPFS is
actually more similar to a single bittorrent swarm exchanging git objects.

IPFS could become a new major subsystem of the internet.
If built right, it could complement or replace HTTP.
It could complement or replace even more.
It sounds crazy.
It *is* crazy.

Organization
------------
This repository contains the Python package ``ipfs``, which contains the
subpackages ``block``, ``merkledag``, ``naming``, and ``routing``, which
function as laid out in the main `IPFS repo <http://github.com/ipfs/ipfs>`_.

The repo roughly looks like this::

    ipfs
    ├─ block
    ├─ merkledag
    ├─ naming
    ├─ network
    └─ routing


Install
~~~~~~~

  **Not ready for prime time yet**

Usage
~~~~~

  **Also not ready for prime time yet**

Roadmap
~~~~~~~

.. note::

  This has been lifted wholesale from js-ipfs_ and only lightly edited.
  As such, it may still contain inconsistencies until further editing.

TODO
^^^^

- Create stubs and checklist items for relevant Python modules.
- Create and link discussion issues at least for each top level.
- Remove JS discussion issues when no longer needed.

This is the roadmap according to the JS implementation.
It has `Peer Routing` inside the `Network` hierarchy.
The above organization has both at the same level.
It also has the `Distributed Record Store` inside `Network`, while our
organization diagram also has it at first level.
TODO: harmonise?



- **Block**
- **MerkleDAG**

  * MerkleDAG Python implementation (needs IPLD).
  * ``py-merkledag-store`` No spec yet.

    - `Go Impl <https://github.com/ipfs/go-ipfs/blob/master/merkledag/merkledag.go>`_
    - `JS Impl <https://github.com/diasdavid/js-merkledag-store>`_

- **Network**

  * The ``libp2p-website`` `is the spec <https://github.com/diasdavid/libp2p-website>`_,
    but for now the place to go is the `roadmap readme <https://github.com/diasdavid/go-libp2p/blob/docs/roadmap/README.md>`_
    in the ``go-libp2p`` docs.
  * `py-libp2p <https://github.com/ipfs/py-ipfs/py-libp2p>`_ *(the entry point)*

  - **Peer Routing**

    * mDNS-routing

      * py-libp2p-kad-routing

        + `JS Impl <https://github.com/diasdavid/js-libp2p-kad-routing>`_
        + `JS discussion issue <https://github.com/ipfs/js-ipfs/issues/18>`_

  - **Discovery**

    Listed separately because they have separate discussion issues in the JS
    repo, which might be relevant.

    * py-libp2p-mdns-discovery

      + `JS Impl <https://github.com/diasdavid/js-libp2p-mdns-discovery>`_
      + `JS discussion issue <https://github.com/ipfs/js-ipfs/issues/19>`_

    * py-libp2p-random-walk

      + `JS Impl <https://github.com/diasdavid/js-libp2p-random-walk>`_
      + `JS discussion issue <https://github.com/ipfs/js-ipfs/issues/20>`_

    * py-libp2p-railing

      + `JS Impl <https://github.com/diasdavid/js-libp2p-railing>`_
      + `JS discussion issue <https://github.com/ipfs/js-ipfs/issues/21>`_

  - **Swarm**

    * Entry point, for now let's call it py-libp2p-swarm

      + `JS Impl <https://github.com/diasdavid/js-libp2p-swarm>`_
      + `JS discussion issue <https://github.com/ipfs/js-ipfs/issues/22>`_

    * libp2p-identify

      + `JS implementation <https://github.com/diasdavid/js-libp2p-swarm/tree/master/src/identify>`_

    * libp2p-ping

      + `JS Impl <https://github.com/diasdavid/js-ipfs-ping>`_

  - **Transports**

    Links to JS impementations probably not needed if we go with Curio,
    but there's always time to delete.

    * libp2p-tcp

      + `JS Impl <https://github.com/diasdavid/js-libp2p-tcp>`_

    * libp2p-udp

      + `JS Impl <https://github.com/diasdavid/js-libp2p-udp>`_

    * libp2p-udt

      + `JS Impl <https://github.com/diasdavid/js-libp2p-udt>`_

    * libp2p-utp

      + `JS Impl <https://github.com/diasdavid/js-libp2p-utp>`_

    * libp2p-webrtc
    * libp2p-cjdns

  - **Upgrades/Crypto Channel**

    * libp2p-tls
    * libp2p-secio

  - **Stream Muxing**

    * py-spdy-stream-muxer

      + `JS Impl <https://github.com/diasdavid/js-spdy-stream-muxer>`_
      + `JS Discussion issue <https://github.com/ipfs/js-ipfs/issues/23>`_

    * libp2p-spdy

      + `JS Impl <https://github.com/diasdavid/js-libp2p-spdy/blob/master/src/index.js>`_

  - **Distributed Record Store**

    * `JS Discussion issue <https://github.com/ipfs/js-ipfs/issues/25>`_
    * py-libp2p-record

      + `JS Impl <https://github.com/diasdavid/js-libp2p-record>`_ *record (needs MerkleDAG node)*

    * py-libp2p-distributed-record-store

      + `JS Impl <https://github.com/diasdavid/js-libp2p-distributed-record-store>`_

    * py-libp2p-kad-record-store

      + `JS Impl <https://github.com/diasdavid/js-libp2p-kad-record-store>`_ *implements abstract record store*.

- **Exchange**

  * py-bitswap

    + `JS Impl <https://github.com/diasdavid/js-bitswap>`_
    + `JS Discussion issue <https://github.com/ipfs/js-ipfs/issues/17>`_

- **Supporting modules**

  * multihash/multihashing

    * Discussion about the `multihash/multihashing distinction <https://github.com/ipfs/py-ipfs/issues/23#issuecomment-158345821>`_
    * `py-multihashing <https://github.com/JulienPalard/multihash>`_ (note: started as multihash, should be multihashing)

      + `JS Impl <https://github.com/jbenet/js-multihashing>`_

    * py-multihash

      + `Spec <https://github.com/jbenet/multihash>`_
      + `Discussion Issue <https://github.com/ipfs/py-ipfs/issues/13>`_
      + `Go Impl <https://github.com/jbenet/go-multihash>`_
      + `JS Impl <https://github.com/jbenet/js-multihash>`_

  * `python-multiaddr <https://github.com/amstocker/python-multiaddr>`_

    + `Spec <https://github.com/jbenet/multiaddr>`_
    + `Go Impl <https://github.com/jbenet/go-multiaddr>`_
    + `JS Impl <https://github.com/jbenet/js-multiaddr>`_

  * py-multistream

    + `Spec <https://github.com/jbenet/multistream>`_
    + `JS Impl <https://github.com/diasdavid/js-multistream>`_ *protocol muxer*
    + `JS Discussion issue <https://github.com/ipfs/js-ipfs/issues/24>`_

  * `py-multicodec <https://github.com/fredthomsen/py-multicodec>`_

    + `Spec <https://github.com/jbenet/multicodec>`_
    + `Go Impl <https://github.com/jbenet/go-multicodec>`_

  * PeerID

    + `JS Impl <https://github.com/diasdavid/js-peer-id>`_

  * PeerInfo

    + `JS Impl <https://github.com/diasdavid/js-peer-info>`_

  * repo
  * `py-ipld <https://github.com/bigchaindb/py-ipld>`_

    + `Spec <https://github.com/ipfs/specs/pull/37>`_
    + `Discussion <https://github.com/ipfs/go-ipld/issues/8>`_
    + `Go Impl <https://github.com/ipfs/go-ipld>`_
    + `JS Impl <https://github.com/diasdavid/js-ipld>`_

- `specs/19 <https://github.com/ipfs/specs/pull/19>`_


Contribute
----------
IPFS implementation in Python is a work in progress. As such, there's a few things you can do right now to help out:

* Go through the modules below and **check out existing issues**.
  This would be especially useful for modules in active development.
  Some knowledge of IPFS may be required, as well as the infrasture
  behind it - for instance, you may need to read up on p2p and more
  complex operations like muxing to be able to help technically.

* Perform code reviews
    More eyes will help, speed the project along, ensure quality &
    reduce possible future bugs.

* Take a look at both go-ipfs_ and js-ipfs_ (which we intend to follow to a
  point), and also at some of the planning repositories or issues: for
  instance, the `libp2p spec`_.
  Contributions here that would be most helpful are **top-level comments**
  about how it should look based on our understanding.
  Again, the more eyes the better.

* Add Tests
    There can never be enough tests.

* Contribute to the `FAQ repository <https://github.com/ipfs/faq/issues>`_
  with any questions you have about IPFS or any of the relevant technology.
  A good example would be asking, "What is a merkledag tree?".
  If you don't know a term, odds are someone else doesn't either.
  Eventually, we should have a good understanding of where we need to improve
  communications and teaching together to make IPFS and IPN better.

.. todo::

  Write our own `CONTRIBUTE.md` similar to
  `IPFS's <https://github.com/ipfs/ipfs/blob/master/CONTRIBUTE.md>`_
  once we know what we're doing and who's doing it.


License
-------

`MIT <LICENSE>`_


.. links:

.. _js-ipfs: https://github.com/ipfs/js-ipfs
.. _go-ipfs: https://github.com/ipfs/go-ipfs
.. _libp2p spec: https://github.com/ipfs/specs/pull/19

.. images:

.. |made-by-shield| image:: https://img.shields.io/badge/made%20by-Protocol%20Labs-blue.svg?style=flat-square
    :target: http://ipn.io

.. |project-shield| image:: https://img.shields.io/badge/project-IPFS-blue.svg?style=flat-square
    :target: http://ipfs.io/

.. |freenode-shield| image:: https://img.shields.io/badge/freenode-%23ipfs-blue.svg?style=flat-square
    :target: http://webchat.freenode.net/?channels=%23ipfs

.. |readme-shield| image:: https://img.shields.io/badge/standard--readme-OK-green.svg?style=flat-square
    :target: https://github.com/RichardLitt/standard-readme
    :alt: standard-readme compliant

.. |gitter-shield| image:: https://badges.gitter.im/Join%20Chat.svg
    :target: https://gitter.im/ipfs/py-ipfs?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge
    :alt: Join the chat at https://gitter.im/ipfs/py-ipfs

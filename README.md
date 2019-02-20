# python-server

Simple Python webserver, forked from [cadence-server](https://github.com/za419/cadence-server)

## Requirements

`python-server` runs on python3. I'm not sure what the minimum required version is (it's no earlier than 3.3), but it's being tested and developed on 3.7.

In order to run ARIA searches, `python-server` requires the `pg8000` module, which can be installed by running `pip install pg8000`.

## Running

The simplest command line is `python server.py <port> <path to directory> [-c [seconds]]`. However, in production, I recommend passing `-OO` to python before `server.py`. This will cause Python to ignore debugging code and remove documentation strings before running the server.

`port` is which port to serve the site on. If it's something privileged like 80, the server will require `sudo`.

The `path to directory` is the path to the root of the site (ie, the front-end folder).

Those two are the only mandatory flags. If you provide `-c` (which I recommend), the server will instruct browsers that they are permitted to cache resources. You can provide an integer after that flag to set the number of seconds browsers are told cache resources are fresh for, or you can leave it to use the default (currently 3600).

Logs are stored next to the server itself, in a folder called "logs" by default (see configuration ini files for more information).

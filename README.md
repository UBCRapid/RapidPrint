RapidPrint
=========

RapidPrint provides a responsive web interface for controlling a 3D printer (RepRap, Ultimaker, ...) with usage tracking. It is Free Software
and released under the [GNU Affero General Public License V3](http://www.gnu.org/licenses/agpl.html).

RapidPrint is a fork of [OctoPrint](https://github.com/foosel/OctoPrint), its website can be found at [octoprint.org](http://octoprint.org).

RapidPrint is being developped by [UBC Rapid](http://www.ubc-rapid.com/).

Reporting bugs
--------------

RapidPrint's issue tracker can be found [on Github](https://github.com/UBCRapid/RapidPrint/issues).

Sending pull requests for non UBC Rapid contributors
----------------------------------------------------

Please create all pull requests against the [devel branch](https://github.com/foosel/OctoPrint/tree/devel) of OctoPrint, as that one is used for developing new 
features and then merged against master when those features are deemed mature enough for general consumption. In case
of bug fixes I'll take care to cherry pick them against master if the bugs they are fixing are critical.

Dependencies
------------

RapidPrint depends on a couple of python modules to do its job. Those are listed in requirements.txt and can be
installed using `pip`:

    pip install -r requirements.txt

You should also do this after pulling from the repository, since the dependencies might have changed.

RapidPrint currently only supports Python 2.7.

Usage
-----

Just start the server via

    ./run

By default it binds to all interfaces on port 5000 (so pointing your browser to `http://127.0.0.1:5000`
will do the trick). If you want to change that, use the additional command line parameters `host` and `port`,
which accept the host ip to bind to and the numeric port number respectively. If for example you want the server
to only listen on the local interface on port 8080, the command line would be

    ./run --host=127.0.0.1 --port=8080

Alternatively, the host and port on which to bind can be defined via the configuration.

If you want to run RapidPrint as a daemon (only supported on Linux), use

    ./run --daemon {start|stop|restart} [--pid PIDFILE]

If you do not supply a custom pidfile location via `--pid PIDFILE`, it will be created at `/tmp/octoprint.pid`.

You can also specify the configfile or the base directory (for basing off the `uploads`, `timelapse` and `logs` folders),
e.g.:

    ./run --config /path/to/another/config.yaml --basedir /path/to/my/basedir

See `run --help` for further information.

Configuration
-------------

If not specified via the commandline, the configfile `config.yaml` for OctoPrint is expected in the settings folder,
which is located at `~/.octoprint` on Linux, at `%APPDATA%/OctoPrint` on Windows and
at `~/Library/Application Support/OctoPrint` on MacOS.

A comprehensive overview of all available configuration settings can be found
[on the OctoPrint wiki](https://github.com/foosel/OctoPrint/wiki/Configuration).

Setup on a Raspberry Pi running Raspbian
----------------------------------------

A comprehensive setup guide can be found [on the wiki](https://github.com/foosel/OctoPrint/wiki/Setup-on-a-Raspberry-Pi-running-Raspbian).

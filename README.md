# Slowloris HTTP DoS attack in Python

Read more about Slowloris [here](https://en.wikipedia.org/wiki/Slowloris_(computer_security)).

We essentially open lots of sockets and make lots of HTTP requests while sending headers every 15 seconds to keep the sockets open. If the server closes a socket, we open a new one. This will use up the web server's thread pool so other people can't connect to it.

## Run

Try it yourself (at your own risk) on web servers running Apache 1.x/2.x (hopefully unpatched?) and dhttpd.

* `git clone https://github.com/adrianchifor/pyslowloris.git`
* `cd pyslowloris`
* `python slowloris.py example.com`

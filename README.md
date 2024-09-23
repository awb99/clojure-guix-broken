# clojure-guix-broken


## what is the issue

 dependencies that contain CLASS files are no longer loaded properly by clojure

## a little test app 

run from this repo:

clojure -X:curl

- this loads aleph library, does a http get request and prints the result.

ON TODAYS GUIX SNAPSHOT IT DOES NOT WORK
you get the following error message:

Execution error (ClassNotFoundException) at java.net.URLClassLoader/findClass (REPL:-1).
io.netty.channel.epoll.Epoll

# in the past it worked

first do this:

guix time-machine --commit=98e4bfe96f2c99daa0b66b65c1d379bb385301a8 -- shell --pure --development --check clojure-tools openjdk coreutils

then 

clojure -X:curl








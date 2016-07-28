tor-proxy
=========

Provides an anonymous proxy over the tor network by exposing privoxy from inside
a container.

## HTTP

```sh
$ docker run -d -p 8181:8181 justinwr/tor-proxy
$ curl --proxy localhost:8181 https://www.duckduckgo.com
```

### macOS

Configure your web proxy on the command-line for your "Wi-Fi" network
connection.

```sh
$ networksetup -setwebproxy "Wi-Fi" localhost 8181
```

Turn off SOCKS proxy on your "Wi-Fi" network connection.

```sh
$ networksetup -setwebproxy "Wi-Fi" off
```

## SOCKS

You can also utilize tor as a regular SOCKS proxy by exposing container port
`9050`.

```sh
$ docker run -d -p 9050:9050 justinwr/tor-proxy
```

### macOS

Configure your SOCKS proxy on the command-line for your "Wi-Fi" network
connection.

```sh
$ networksetup -setsocksfirewallproxy "Wi-Fi" localhost 9050
```

Turn off SOCKS proxy on your "Wi-Fi" network connection.

```sh
$ networksetup -setsocksfirewallproxystate "Wi-Fi" off
```

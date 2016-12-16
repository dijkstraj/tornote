# Tornote 

Based on the implementation by [Vladimir Osintsev](https://github.com/osminogin).

Anonymous self-destructing notes written in Go and with help Stanford Javascript Crypto Library ([SJCL](https://crypto.stanford.edu/sjcl/)) on client-side.

Server stores only encrypted data. JavaScript must be enabled, because notes are decrypted in the browser with the key contained in the secret link. After reading the encrypted note is immediately removed from the database.    

Latest stable version available on https://notes.medworq.nl

## Security

How safe is Tornote compared with other similar services? More than:

- All private data in the clear text is not leaving the client-side (without encryption).

- Server stores only anonymous encrypted data (without any reference to author or reader).

- Note decryption executed on the client-side via the SJCL. On reading the encrypted data is removed from the server.

If you have ideas to improve the safety/security so far as possible please post the issue.

## Getting started

```bash
$ go get -u github.com/dijkstraj/tornote
$ cd $GOPATH/src/github.com/dijkstraj/tornote
$ bower install
$ make install
$ tornote &
```

## Running with Docker

```bash
$ docker build -t tornote-app .
$ docker run -p 80:8080 --name tornote tornote-app
```

## License

AGPLv3 or later

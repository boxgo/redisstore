[doc-img]: https://godoc.org/github.com/boxgo/redisstore?status.svg
[doc-url]: https://godoc.org/github.com/boxgo/redisstore
[travis-img]: https://travis-ci.com/boxgo/redisstore.svg?branch=master
[travis-url]: https://travis-ci.com/boxgo/redisstore?branch=master
[coverage-img]: https://coveralls.io/repos/github/boxgo/redisstore/badge.svg?branch=master
[coverage-url]: https://coveralls.io/github/boxgo/redisstore?branch=master
[report-img]: https://goreportcard.com/badge/github.com/boxgo/redisstore
[report-url]: https://goreportcard.com/report/github.com/boxgo/redisstore

# redistore

[![GoDoc][doc-img]][doc-url]
[![Build Status][travis-img]][travis-url]
[![Coverage Status][coverage-img]][coverage-url]
[![Go Report Card][report-img]][report-url]

A session store backend for [gorilla/sessions](http://www.gorillatoolkit.org/pkg/sessions) - [src](https://github.com/gorilla/sessions).

## Requirements

Depends on the [go-redis/redis](https://github.com/go-redis/redis) Redis library.

## Installation
```sh
    go get github.com/boxgo/redistore
```

### Example
``` go
client := redis.NewUniversalClient(&redis.UniversalOptions{
    Addrs: []string{"localhost:6379"},
    DB:    0,
})

store, err := NewStoreWithUniversalClient(client,
    WithKeyPairs([]byte("test")),
    WithKeyPrefix("session_"),
    WithSerializer(&serializer.JSONSerializer{}),
)
```
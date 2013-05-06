# base64-clj

Convert Data to [Base64](http://en.wikipedia.org/wiki/Base64) and back in a reasonable amount of time. 

This is much slower than the [Apache Commons Base64 Codec](http://commons.apache.org/proper/commons-codec/apidocs/org/apache/commons/codec/binary/Base64.html). Seriously, use that one, especially since using it is really, really simple (see [here](https://github.com/xsc/base64-clj/blob/master/benchmark/base64_clj_benchmark/apache_commons_base64.clj)). I just wanted to see how fast I could make a Clojure implementation.

## Usage

__REPL__

```clojure
(require '[base64-clj.core :as base64])

(base64/encode "Hello, World!")
;; => "SGVsbG8sIFdvcmxkIQ=="

(base64/decode "SGVsbG8sIFdvcmxkIQ==")
;; => "Hello, World!"

```

### Benchmarks

You can run [Criterium](https://github.com/hugoduncan/criterium) benchmarks on different Base64 codecs with the following
Leiningen command:

```
lein benchmark base64-clj-benchmark.<ID> [--quick]
```

__ID__ is one of:

- `base64-clj` : evaluate this project
- `base64-naive` : evaluate a naive and intuitive implementation
- `apache-commons-base64` : evaluate the Apache Commons Codec

## License

Copyright &copy; Yannick Scherer

Distributed under the Eclipse Public License, the same as Clojure.
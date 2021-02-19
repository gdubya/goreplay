### Overview
Gor architecture tries to follow UNIX philosophy: everything made of pipes, various inputs multiplexing data to outputs.

You can [rate limit](/rate-limiting.md), [filter](request-filtering.md), [rewrite](request-rewriting.md) requests or even use your own [middleware](middleware.md) to implement custom logic. Also, it is possible to replay requests at the higher rate for [load testing](saving-and-replaying-from-file.md).

### Available inputs

* `--input-raw` - used to capture HTTP traffic, you should specify IP address or interface and application port. More about [[Capturing and replaying traffic]].
* `--input-file` - accepts file which previously was recorded using ` --output-file`. More about [[Saving and Replaying from file]]
* `--input-tcp` - used by a Gor aggregator for accepting forwarded traffic from other Gor instances. Read about using Aggregator-forwarder setup in [[Distributed configuration]].

### Available outputs

* `--output-http` - replay HTTP traffic to given endpoint, accepts base url. Read [more about it](Replaying HTTP traffic)
* `--output-file` - records incoming traffic to the file. More about [[Saving and Replaying from file]]
* `--output-tcp` - forward incoming data to another Gor instance, used in conjunction with `--input-tcp`. Read about using Aggregator-forwarder setup in [[Distributed configuration]].
* `--output-stdout` - used for debugging, outputs all data to stdout.
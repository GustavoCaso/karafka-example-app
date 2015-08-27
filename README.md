# Karafka example application

[![Build Status](https://travis-ci.org/karafka/karafka-example-app.png)](https://travis-ci.org/karafka/karafka-example-app)
[![Code Climate](https://codeclimate.com/github/karafka/karafka-example-app/badges/gpa.svg)](https://codeclimate.com/github/karafka/karafka-example-app)

This is an example application which uses [Karafka framework](https://github.com/karafka/karafka
) to receive messages from [Apache Kafka](http://kafka.apache.org/) server and [WaterDrop gem](https://github.com/karafka/waterdrop) to send messages to Kafka server.

To run this application locally you should run Apache Kafka and Apache ZooKeeper servers on those hosts and ports which
are set in *app.rb* and */config/initializers/water_drop.rb* files.

## Usage

Following available. You should run them in the console.

#### Run sidekiq worker to manage perform methods of controllers
```
  bundle exec rake karafka:sidekiq
```
#### Run Kafka consumer. It will receive messages and send them to needed controller based on it's topic name
```
  bundle exec rake karafka:run
```

#### Generate messages to Kafka server in two ways: by applying aspects to methods, and by sending message directly.

```
  bundle exec rake waterdrop:send
```

## References

* [Karafka framework](https://github.com/karafka/karafka)
* [WaterDrop gem](https://github.com/karafka/waterdrop)
* [Apache Kafka](http://kafka.apache.org/)
* [Apache ZooKeeper](https://zookeeper.apache.org/)

## Note on Patches/Pull Requests

Fork the project.
Make your feature addition or bug fix.
Add tests for it. This is important so I don't break it in a future version unintentionally.
Commit, do not mess with Rakefile, version, or history. (if you want to have your own version, that is fine but bump version in a commit by itself I can ignore when I pull). Send me a pull request. Bonus points for topic branches.

Each pull request must pass our quality requirements. To check if everything is as it should be, we use [PolishGeeks Dev Tools](https://github.com/polishgeeks/polishgeeks-dev-tools) that combine multiple linters and code analyzers. Please run:

```bash
bundle exec rake
```

to check if everything is in order. After that you can submit a pull request.
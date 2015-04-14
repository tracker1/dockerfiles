# docker-travis-ci-cli

Based on [andredumas/docker-travis-ci-cli](https://github.com/andredumas/docker-travis-ci-cli)

Docker container for [travis ci client](http://blog.travis-ci.com/2013-01-14-new-client/) following 
[installation instructions](https://github.com/travis-ci/travis.rb#installation), using Ruby 1.9.3.

I primarily used this to `travis setup releases`.

```
docker pull tracker1/travis-ci-cli
```

## Usage

```
docker run --rm -v $PWD:/repo -v ~/.travis:/travis tracker1/travis-ci-cli [command]
```


### Detailed Example

```
$ alias travis='docker run --rm -v $PWD:/repo -v ~/.travis:/travis tracker1/travis-ci-cli'
$ travis whoami
not logged in, please run travis login
$ travis login --github-token <public_repo personal access token>
$ travis whoami
andredumas
$ travis setup releases
# Follow on screen instructions
```

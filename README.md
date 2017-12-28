# Scout APM Slowness POC

This is a proof-of-concept of the slowness of loading the `scout_apm` gem.

It's a plain Ruby 2.3.5 / Rails 4.2.10 app with `bumbler`

Prior to scout_apm boot time is:

```
$ time be bumbler

Slow requires:
    166.95  sass-rails
    319.91  rails
bundle exec bumbler  1.46s user 0.82s system 87% cpu 2.595 total
```

After adding `scout_apm` gem:

```
$ time be bumbler
Slow requires:
    197.71  sass-rails
    233.56  rails
   5298.24  scout_apm
bundle exec bumbler  1.62s user 0.86s system 31% cpu 7.773 total
```

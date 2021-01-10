# Jekyll on Heroku
  * For more information, please visit https://blog.heroku.com/jekyll-on-heroku

### Gemfile
  * ruby (2.7.2)
  * bunlder (2.1.4)
  * jekyll (4.2.0)
  * rake (13.0.3)
  * rack (1.6.13)
  * rack-jekyll (0.5.0)
  * minima (2.5.1)

```console
bundle config set --local path 'vendor/bundle'
```

```console
bundle install
```

```console
bundle exec jekyll serve
```

```console
git add .
```

```console
git commit -m "Cleanup"
```

```console
git push heroku master
```

### Install 
```console
git clone https://github.com/lootpiz/jekyll-on-heroku.git
```

```console
cd jekyll-on-heroku
```

```console
heroku apps:create
```

```console
heroku buildpacks:add heroku/ruby
```

```console
heroku buildpacks:add https://github.com/heroku/heroku-buildpack-static
```

```console
bundle config set --local path 'vendor/bundle'
```

```console
bundle install
```

```console
git add .
```

```console
git commit -m "Updated"
```

```console
$ git push heroku master
```

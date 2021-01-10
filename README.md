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

### Setup
```console
jekyll new jekyll-on-heroku
```

```console
cd jekyll-on-heroku
```

```console
git init
```

```console
vi .gitignore
```
> .bundle

```console
git add .
```

```console
git commit -m "Initial commit"
```

```console
heroku apps:create my-new-app-folder
```

```console
heroku buildpacks:add heroku/ruby
```

```console
heroku buildpacks:add https://github.com/heroku/heroku-buildpack-static
```

```console
vi Gemfile
```
> source "https://rubygems.org"
> ruby "2.7.2"
> gem "jekyll"
> gem "minima"
> gem "bundler"
> gem "rack"
> gem "rack-jekyll"
> gem "rake"

```console
vi Procfile
```
> ---
> addons: []
> config_vars:
>   LANG: en_US.UTF-8
>   RACK_ENV: production
> default_process_types:
>   rake: bundle exec rake
>   console: bundle exec irb
>   web: bundle exec rackup config.ru -p $PORT

```console
vi Rakefile
```
> task "assets:precompile" do
>   exec("jekyll build")
> end

```console
vi config.ru
```
> require 'yaml'
> require 'rack/jekyll'
> run Rack::Jekyll.new

```console
vi static.json
```
> {
>  "clean_urls": true,
>  "https_only": true,
>  "root": "_site/"
> }

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
$ git clone https://github.com/lootpiz/jekyll-on-heroku.git
```

```console
$ heroku apps:create
```

```console
$ heroku buildpacks:add heroku/ruby
```

```console
$ heroku buildpacks:add https://github.com/heroku/heroku-buildpack-static
```

```console
$ bundle config set --local path 'vendor/bundle'
```

```console
$ bundle install
```

```console
$ git add .
```

```console
$ git commit -m "Updated"
```

```console
$ git push heroku master
```
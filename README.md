Fig/Docker/Rails example app/bootstrapper
=========================================

See the [blog post](https://orchardup.com/blog/use-fig-to-run-a-rails-app) for full details.


*******

## Step 1 - Update ruby  and rails versions


### Dockerfile

```
-FROM binaryphile/ruby:2.0.0-p247
+FROM binaryphile/ruby:2.1.2
 ```

### Gemfile

```
-gem 'rails', '4.0.2'
+gem 'rails', '4.2.0'
```


## Step 2 - install rails

```
$ fig run web rails new . --force --database=postgresql \
    --skip-turbolinks --skip-test-unit \
    --skip-spring --skip-bundle
```

## Step 3 - update Gemfile

The usual stuff I like.

## Step 4 - build container

    $ fig build

Seems to have built things, but:

    $ fig up

*Rebuilds* things, and appears that bundler never got run. It fails
with:

```
    web_1 | /usr/local/lib/ruby/gems/2.1.0/gems/bundler-1.6.2/lib/bundler/source/git/git_proxy.rb:151:in `allowed_in_path': The git source git://github.com/tamouse/twitter_bootstrap_form_for.git is not yet checked out. Please run `bundle install` before trying to start your application (Bundler::GitError)
```

Dropping this line of inquiry.

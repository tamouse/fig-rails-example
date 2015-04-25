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

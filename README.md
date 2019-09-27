# Northbricks Developer Portal
This is [Northbricks Developer Portal](https://www.northbricks.io).

The website is a static website that is built with [Jekyll](https://jekyllrb.com) and hosted with *HitHub Pages* from this repo. The API specification is displayed by the [RapiDoc](https://mrin9.github.io/RapiDoc/) Component using the OpenApi specification files in `/assest/api-spec`

## Run local server

Start local server.
```sh
bundle exec jekyll serve
```

## Deploy

Just check in the code to the master branch.

## Prerequisites Ubuntu

These dependencies need to be installed to build and run on Ubuntu.

```sh
sudo apt-get install ruby-full build-essential zlib1g-dev

echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

gem install jekyll bundler
```
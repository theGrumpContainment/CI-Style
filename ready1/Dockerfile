from ruby

env \
  DEBIAN_FRONTEND=noninteractive \
  NODE_VERSION=16.14.0

run \
  sed -i "/deb-src/d" /etc/apt/sources.list && \
  apt update && apt install -y build-essential cmake && \
  wget -O- -q "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz" | tar xfJ - -C /usr/local --strip-components=1 && \
  npm install -g \
    cypress --unsafe-perm --silent \
    eslint@7.32.0 \
    eslint-plugin-html \
    babel-eslint \
    eslint-config-standard \
    eslint-plugin-prettier \
    eslint-plugin-import@latest \
    eslint-plugin-node@latest \
    eslint-plugin-promise@latest \
    eslint-plugin-standard@latest && \
  npm install -g \
    @babel/core@7.18.6 \
    @babel/eslint-parser@7.12.16 \
    eslint-config-prettier@8.3.0 \
    prettier-plugin-multiline-arrays@1.1.0 \
    eslint@7.32.0 \
    prettier@2.4.1 && \
  gem install --no-document parser pronto pronto-rubocop pronto-flay \
    rubocop-rspec rubocop-performance pronto-eslint_npm pronto-reek reek \
    pronto-fasterer rubocop faraday-retry && \
  rm -rf /var/lib/apt/lists/*

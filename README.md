# Standalone-php-exec

## Build

Prepare build

```bash
mkdir build/my-prepared-app
git archive HEAD | tar -x -C build/my-prepared-app
cd build/my-prepared-app
echo APP_ENV=prod > .env.local
echo APP_DEBUG=0 >> .env.local
composer install --ignore-platform-reqs --no-dev -a
cd ../..
```

Install build tool

```bash
git clone https://github.com/php/frankenphp
```

Build executable

```bash
cd frankenphp

PHP_EXTENSIONS="filter,iconv,tokenizer" \
EMBED=../build/my-prepared-app \
./build-static.sh
```

## Run

```bash
dist/frankenphp-linux-x86_64 php-server -l localhost:8000 -r .
```

# Standalone-php-exec

## Build

```bash
mkdir build/my-prepared-app
git archive HEAD | tar -x -C build/my-prepared-app
cd build/my-prepared-app
echo APP_ENV=prod > .env.local
echo APP_DEBUG=0 >> .env.local
composer install --ignore-platform-reqs --no-dev -a
cd ../..
```

```bash
git clone https://github.com/php/frankenphp
```

```bash
cd frankenphp
```

```bash
PHP_EXTENSIONS="filter,iconv,tokenizer" \
EMBED=/home/mantas/Projects/Playground/standalone-php-exec/build/my-prepared-app \
./build-static.sh
```

## Run

```bash
dist/frankenphp-linux-x86_64 php-server -l localhost:8000 -r .
```

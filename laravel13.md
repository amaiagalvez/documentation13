# Install aplikazio berri bat

>> `docker-compose.yml` PHP 8.4 martxan jarri

```
composer global require laravel/installer
```
```
laravel new demo13
```
- Livewire
- Laravel's built-in authentication
- Use single-file Livewire components Yes
- Teams support No
- Pest
- Laravel Boost Yes

>> npm akatsa emango du

>> itzali laravel13 makina

# Martxan jarri aplikazio berria

>> `docker-compose.yml` basics13-tik hartu eta martxan jarri

```
cp ../packages/basics13/tooling/docker-compose.yml .
```

- basics13-n bizi da; hura behar da edukiontziak martxan jartzeko. Gero `vendor:publish --tag=basics13-tooling` berdinak usten du
- `docker/` azpiko script-ak ere basics13-n bizi dira (mysql init, phpunit coverage, link-opencode): compose-ak `/packages/basics13/tooling/...` erabiltzen du, beraz ez dago kopiarik aplikazioan

>> .gitignore => dc-data

```
sudo chown amaia:amaia dc-data/
sudo chown amaia:amaia dc-data/mysqldumps/
```

```
git init
git add .
git commit -am "Laravel 13 instalation"
```

- Zuzendu composer.json dockerrekin ez emateko errorerik
>> Containers: Composer up - Select Services
- composer
- npm-all
- migration-all
- reformat

>> .env.example aldatu eta .env egokitu

- 
```
git add .
git commit -am "application running"
```

>> basics13 paketea + tooling config

```
composer config repositories.basics13 '{"type": "path", "url": "../packages/basics13", "options": {"symlink": true}}'
composer require amaia/basics13
```
```
php artisan vendor:publish --tag=basics13-tooling
```

- Honek basics13-tik argitaratzen ditu aplikazioan (kopia bakarra basics13-n, ez eskuzeko kopia bat aplikazio bakoitzean): `pint.json`, `phpstan.neon`, `phpunit.xml`, `phpunit.dusk.xml`, `boost.json`, `docker-compose.yml` eta `Dockerfile.dusk`
- basics13-eko config-a aldatzen denean, aplikazioan eguneratzeko:
```
php artisan vendor:publish --tag=basics13-tooling --force
```

>> Dusk test
```
composer require --dev laravel/dusk
php artisan dusk:install
```

>>  install laraveel boots + skills

```
composer require laravel/boost --dev
php artisan boost:install
```

>> Hizkuntzak
 composer require laravel-lang/common --no-interaction
php artisan lang:add es fr eu --no-interaction

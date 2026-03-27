# 🐘 Symfony Docker Template

![PHP](https://img.shields.io/badge/PHP-8.5-777BB4?logo=php&logoColor=white)
![Symfony](https://img.shields.io/badge/Symfony-8-000000?logo=symfony&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-ready-2496ED?logo=docker&logoColor=white)
![FrankenPHP](https://img.shields.io/badge/FrankenPHP-1-9B59B6?logo=php&logoColor=white)
![PHPStan](https://img.shields.io/badge/PHPStan-level%206-8892BF)
![License](https://img.shields.io/badge/license-MIT-green)

## Stack

- **PHP 8.5** / **Symfony 8**
- **FrankenPHP** (modern PHP server, replaces Nginx + PHP-FPM)
- **PostgreSQL 16**
- **Docker** / Docker Compose
- **PHP CS Fixer** (automatic PSR-12 code formatting)
- **PHPStan** (static analysis, level 6)
- **GrumPHP** (automatic git hooks)

## Requirements

- [Docker](https://docs.docker.com/get-docker/) + Docker Compose
- [Git](https://git-scm.com/)
- Make

## Start a new project

```bash
# 1. Use this template from GitHub ("Use this template" button)
# 2. Clone your new repo
git clone git@github.com:YOUR_USERNAME/my-project.git
cd my-project

# 3. Start Docker
make start
```

The app is available at **https://localhost** 🎉

## Available commands

| Command | Description |
|---|---|
| `make start` | Start Docker containers |
| `make stop` | Stop containers |
| `make bash` | Open a terminal inside the PHP container |
| `make db-create` | Create the database |
| `make migration` | Generate a Doctrine migration |
| `make migrate` | Run migrations |
| `make cs-fix` | Format code (PHP CS Fixer) |
| `make phpstan` | Run static analysis |
| `make fix-perms` | Fix file permissions |

## Environment variables

Default values are defined in `compose.yaml`. To override them locally, create a `.env.local` file at the root:

```env
POSTGRES_USER=my_user
POSTGRES_PASSWORD=my_password
POSTGRES_DB=my_database
```

> ⚠️ The `.env.local` file is listed in `.gitignore`

## Code quality

```bash
# Automatically format code
make cs-fix

# Run static analysis
make phpstan
```

## Project structure

```
├── compose.yaml            # Docker configuration
├── compose.override.yaml   # Docker overrides (dev)
├── Dockerfile              # PHP/FrankenPHP image
├── Makefile                # Daily commands
├── .php-cs-fixer.dist.php
├── phpstan.dist.neon
└── src/                    # Symfony source code
```

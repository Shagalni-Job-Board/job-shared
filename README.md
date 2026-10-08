# job-shared

This repository is the shared Laravel package for the Shagalni platform. It contains the common model classes and notification definitions used by both the public job app and the backoffice application.

## Purpose

The main purpose of this package is to keep the platform domain consistent across repositories. Instead of duplicating the same Eloquent models in multiple apps, the shared package provides the common model layer that both projects consume through Composer.

## Main technologies

- PHP 8.2
- Laravel 12
- Composer package architecture

## What is included

The package currently provides shared domain models and a notification class, including:

- App\Models\User
- App\Models\company
- App\Models\job_category
- App\Models\job_vacancy
- App\Models\resume
- App\Models\job_application
- App\Notifications\newJobApply

## Project structure

- src/Models: shared Eloquent models
- src/Notifications: shared notification classes
- composer.json: package definition and autoload configuration

## Installation

Add the package repository and require it from a Laravel app:

```json
"repositories": [
  {
    "type": "vcs",
    "url": "https://github.com/YoussefSayed-cs/job-shared.git"
  }
],
"require": {
  "job/shared": "*"
}
```

Then run:

```bash
composer install
```

## Database and migrations

This package does not contain its own application migrations. The shared schema is created in the job-backoffice repository, and both applications use the same database connection and tables.

## Requirements

- PHP ^8.2
- Laravel ^12.0
- Composer

## Related repositories

- job-app: seeker-facing application
- job-backoffice: admin and company management application

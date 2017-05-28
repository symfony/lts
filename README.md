Enforcing Long Term Supported Versions of the Symfony Components
================================================================

Using `symfony/symfony` makes Composer install all Symfony Components, all in
the same version. But when using the standalone packages, Composer might
install dependencies in a different major version (`symfony/http-kernel` v2.8
is compatible with `symfony/event-dispatcher` v3.0 for instance).

This is fine if you don't want to stick to Symfony LTS versions and if your
code does not use these transitive dependencies.

This Composer package allows you to enforce a consistent major version on all
Symfony Components, whether they are explicitly listed as a project's
dependency or installed transitively.

Note that this package is meant to be used by projects. Library authors SHOULD
NOT use it, except maybe in the `"require-dev"` Composer section.

Usage
-----

Use the Composer command line:

```bash
composer require symfony/lts v3
```

Versioning Policy
------------------

There is only one version of the `symfony/lts` package per major Symfony
version. Each version is tagged at the same time as the *last* minor version of
each major release (`v3` when Symfony `v3.4.0` is out.)

At the same time also, the Composer `branch-alias` is increased to the next
major version number.

If one wants to use the next *unreleased* major version of Symfony, one should
not use this package at all.

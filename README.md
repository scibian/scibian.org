This repo contains source files for https://scibian.org.

The website is static and the pages are generated using the Hyde templating engine.

The following commands must be used to update the pre-production website https://scibian.org/preprod-site/:

```
cd /local00/git/scibian.org
git pull github
. env/bin/activate
hyde gen -c preprod.yml
```

For the production site at https://scibian.org run hyde with `prod.yml`.

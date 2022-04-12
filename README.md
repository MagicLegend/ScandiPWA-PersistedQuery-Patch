# ScandiPWA-PersistedQuery-Patch
Repo providing a tiny patch for the ScandiPWA/PersistedQuery composer module to ensure compatability with Magento Cloud's Varnish. This fixes the following issue:

```
Error flushing Varnish server. Host: "varnish". PURGE response code: 400 message: X-Magento-Tags-Pattern header required
```

# Usage

First, you need the package that allows composer patches.

```
composer require cweagans/composer-patches
```

Then, you can add this section to your `composer.json`:

```
"patches": {
    "scandipwa/persisted-query": {
        "https://github.com/scandipwa/scandipwa/issues/2762 | scandipwa/persisted-query fix for Varnish in Magento Cloud setups": "https://raw.githubusercontent.com/MagicLegend/ScandiPWA-PersistedQuery-Patch/main/magento_cloud_varnish_persisted_query.patch"
    }
}
```

When running `composer install` it should automatically install this patch.

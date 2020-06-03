# one-signal-api-bundle

Use the OneSignal PHP API [made by Norkunas](https://github.com/gulaandrij/onesignal-php-api).

### Download the Bundle

```console
$ composer require gulaandrij/one-signal-api-bundle
```

### Enable the Bundle

Registered bundles in the `app/AppKernel.php` file of your project:

```php
<?php
class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = array(
            // ...
            new GulaAndrij\OneSignalApiBundle\GulaAndrijOneSignalApiBundle(),
        );
        // ...
    }
    // ...
}
```

### Config
Add this to config.yml:

```yaml
one_signal_api:
    app_id:         "{ONE_SIGNAL_API_APP_ID}"
    app_auth_key:   "{ONE_SIGNAL_API_APP_AUTH_KEY}"
    user_auth_key:  "{ONE_SIGNAL_API_USER_AUTH_KEY}"
```

### Basic Use
Gets all apps:

- services.yaml:
```yaml
    App\Controller\Admin\DashboardController:
        arguments: ['@one_signal_api.service']
```
- DashboardController.php
```php
$service = $this->get('one_signal_api.service');

$myApps = $service->apps->getAll();
```

# TemplateBundle


### Step 1: Download de bundle
``` json
"foxsiscom/templatebundle" : "dev-master"
```

### Step 2: Enable the bundle
``` php
// app/AppKernel.php
public function registerBundles()
{
    return array(
        // ...
        new Foxsiscom\TemplateBundle\FoxsiscomTemplateBundle(),
    );
}
```

### Step 3: Register the bundle in your assetic.bundle config
``` yaml
#app/config/config.yml
assetic:
    debug:          "%kernel.debug%"
    use_controller: false
    bundles:        [FoxsiscomTemplateBundle]
```

### Step 4: Publish assets
```sh
php app/console assetic:dump
```

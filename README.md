[![SensioLabsInsight](https://insight.sensiolabs.com/projects/a16747e6-5909-412a-ac90-f1e0d8b7f141/big.png)](https://insight.sensiolabs.com/projects/a16747e6-5909-412a-ac90-f1e0d8b7f141)

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
        new FOS\JsRoutingBundle\FOSJsRoutingBundle(),
    );
}
```

### Step 3: Register the routing definition

```yaml
# app/config/routing.yml
fos_js_routing:
    resource: "@FOSJsRoutingBundle/Resources/config/routing/routing.xml"
```

### Step 4: Register the bundle in your assetic.bundle config
``` yaml
#app/config/config.yml
assetic:
    bundles:        [FoxsiscomTemplateBundle]
```

### Step 5: Publish assets
```sh
$ php app/console assets:install --symlink web
```

### Step 6: Publish assets
```sh
$ php app/console assetic:dump
```

### Step 7: Add these two lines in your layout:
```jinja
<script src="{{ asset('bundles/fosjsrouting/js/router.js') }}"></script>
<script src="{{ path('fos_js_routing_js', {'callback': 'fos.Router.setData'}) }}"></script>
```

Usage
-----

Extends the template in your views or in you template base
``` twig
{% extends 'FoxsiscomTemplateBundle:MaterialAdmin:index.html.twig' %}
```

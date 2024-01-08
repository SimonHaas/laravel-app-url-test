./vendor/laravel/framework/src/Illuminate/Routing/UrlGenerator.php
``` php
    public function asset($path, $secure = null)
    {
        if ($this->isValidUrl($path)) {
            return $path;
        }

        // Once we get the root URL, we will check to see if it contains an index.php
        // file in the paths. If it does, we will remove it since it is not needed
        // for asset paths, but only for routes to endpoints in the application.
        $root = $this->formatRoot($this->formatScheme($secure));

        return $path;
        #return $this->removeIndex($root).'/'.trim($path, '/');
    }

    protected function toRoute($route, $parameters, $absolute)
    {
        return $this->routeUrl()->to(
            $route
        );
        #return $this->routeUrl()->to(
        #    $route, $this->formatParameters($parameters), $absolute
        #);
    }
```
```bash
    composer install --no-dev --no-scripts
    chmod +x test*
    ./test-7.2.19
    # works
    
    ./test-7.2.20
    # fails with:
    # Fatal error: During class fetch: Uncaught ReflectionException: Class Doctrine\Bundle\FixturesBundle\Fixture not found in /var/www/html/src/DataFixtures/AppFixtures.php:8
    # Stack trace:
    #0 /var/www/html/vendor/composer/ClassLoader.php(444): include('/var/www/html/s...')
    #1 /var/www/html/vendor/composer/ClassLoader.php(322): Composer\Autoload\includeFile('/var/www/html/v...')
    #2 [internal function]: Composer\Autoload\ClassLoader->loadClass('App\\DataFixture...')
    #3 [internal function]: spl_autoload_call('App\\DataFixture...')
    #4 /var/www/html/vendor/symfony/config/Resource/ClassExistenceResource.php(78): class_exists('App\\DataFixture...')
    #5 /var/www/html/vendor/symfony/dependency-injection/ContainerBuilder.php(353): Symfony\Component\Config\Resource\ClassExistenceResource->isFresh(0)
    #6 /var/www/html/vendor/symfony/dependency-injection/Loader/FileLoader.php(151): Symfony\Component\DependencyInjection\ContainerBuilder->getReflectionClass('App\\DataFixture...')
    #7 /var/www/html/vendor/symfony/dependency-injection/Loader/FileL in /var/www/html/src/DataFixtures/AppFixtures.php on line 8

```


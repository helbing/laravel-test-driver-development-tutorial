## 安装环境

```shell
brew cask install visual-studio-code-insiders
brew install php composer
composer global require
composer global require phpunit/phpunit 
composer global require squizlabs/php_codesniffer 
composer global require friendsofphp/php-cs-fixer 
```

## Visual Studio Code 插件

php 开发推荐使用下面这些插件

- [PHP Intelephense](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client)
- [PHPUnit](https://marketplace.visualstudio.com/items?itemName=emallin.phpunit)
- [php cs fixer](https://marketplace.visualstudio.com/items?itemName=junstyle.php-cs-fixer)
- [PHP DocBlocker](https://marketplace.visualstudio.com/items?itemName=neilbrayfield.php-docblocker)
- [phpcs](https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs)

## 插件配置

```
"php.suggest.basic": false,
"php-cs-fixer.onsave": true,
"php-cs-fixer.rules": "@PSR2",
"phpcs.enable": true,
"phpcs.standard": "PSR2",
"phpcs.showSources": true,
"phpcs.trace.server": "verbose",
"phpcs.ignorePatterns": ["*/vendor/*"],
"phpcs.autoConfigSearch": true,
"intelephense.licenceKey": "",
"[php]": {
  "editor.defaultFormatter": "junstyle.php-cs-fixer"
},
```

我使用的 intelephense 插件推出了 Pro 服务，推荐购买，[https://intelephense.com/](https://intelephense.com/)

## 其他

你可以会奇怪我怎么没安装 xdebug 插件，理由很简单，因为每次打断点跑但单元测试的时候，总是会报 PHP ReflectionException: Method suite does not exist，上网查了解决方法，按照说的将 xdebug.show_exception_trace 设置为0，也依旧无法解决，所以干脆不用 xdebug 了，反正调试这块打 var_dump 也是能解决的，没必要非要使用 xdebug

还有就是为什么没使用 phpstan，phpmd 这类的静态检查工具，主要是毕竟 php 不是静态类型语言，而这类检查工具总是会提示各种各样的错误，太烦人了。只要好好遵守 PSR 规范，还是能写出安全的代码的，所以干脆不用了，看到错误就糟心

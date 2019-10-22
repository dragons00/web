## npmrc
The four relevant files are:
* per-project configuration file (/path/to/my/project/.npmrc)
* per-user configuration file (defaults to $HOME/.npmrc; configurable via CLI option --userconfig or environment variable $NPM_CONFIG_USERCONFIG)
* global configuration file (defaults to $PREFIX/etc/npmrc; configurable via CLI option --globalconfig or environment variable $NPM_CONFIG_GLOBALCONFIG)
* npm’s built-in configuration file (/path/to/npm/npmrc)
| 这四个相关文件是：
每个项目的配置文件（/path/to/my/project/.npmrc）
每用户配置文件（默认为$HOME/.npmrc;可通过CLI选项--userconfig或环境变量配置$NPM_CONFIG_USERCONFIG）
全局配置文件（默认为$PREFIX/etc/npmrc;可通过CLI选项--globalconfig或环境变量配置$NPM_CONFIG_GLOBALCONFIG）
npm 的内置配置文件（/path/to/npm/npmrc）
有关详细信息，请参阅 npmrc

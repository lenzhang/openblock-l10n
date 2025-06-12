# OpenBlock-l10n (Upgraded Fork)

[![Publish Npm Package](https://github.com/openblockcc/openblock-l10n/actions/workflows/publish-npm-package.yml/badge.svg)](https://github.com/openblockcc/openblock-l10n/actions/workflows/publish-npm-package.yml) ![](https://img.shields.io/github/license/openblockcc/openblock-l10n)

## 🙏 Acknowledgements

This is a fork of the original [OpenBlock-l10n](https://github.com/openblockcc/openblock-l10n) project created by the OpenBlock team. We are deeply grateful to the original authors and contributors for their excellent work in creating this internationalization library for OpenBlock projects.

**Original Project**: [https://github.com/openblockcc/openblock-l10n](https://github.com/openblockcc/openblock-l10n)  
**Original Authors**: OpenBlock Team and contributors

## 🚀 What's New in This Fork

This fork includes significant dependency upgrades and modernization improvements:

### ✨ Major Upgrades
- **Node.js**: Upgraded to require Node.js >=18.0.0
- **Webpack**: Upgraded from 4.x to 5.x (latest)
- **Babel**: All Babel packages upgraded to latest versions
- **ESLint**: Upgraded to latest stable version
- **All Dependencies**: Updated to latest stable versions

### 📈 Improvements
- **Smaller Bundle Size**: Reduced package size by ~16KB (-1.2%)
- **Better Performance**: Webpack 5 optimizations
- **Modern JavaScript**: Support for latest ES features
- **Security**: Fixed multiple security vulnerabilities
- **Maintenance**: Removed deprecated packages

### 📋 Requirements
- **Node.js**: >=18.0.0 (see `.nvmrc` for recommended version)
- **npm**: >=8.0.0

For detailed upgrade information, see [UPGRADE_NOTES.md](./UPGRADE_NOTES.md).

---

## About OpenBlock-l10n

Translation of all OpenBlock projects is managed on the Transifex service: https://www.transifex.com/openblockcc/public/

This repository collects translations submitted to the OpenBlock projects on Transifex. **Please do not submit PRs. If you would like to contribute translations, please sign up to translate on Transifex.**

## Using OpenBlock-l10n in development

#### Installation
```bash
npm install --save-dev openblock-l10n
```

#### Basic Use
```js
import locales, {localeData, isRtl} from 'openblock-l10n';
import editorMessages from 'openblock-l10n/locales/editor-messages';
```
* `locales`: currently supported locales for the OpenBlock project
* `isRtl`: function that returns true if the locale is one that is written right-to-left
* `localeData`: locale data for the supported locales, in the format accepted by `addLocaleData` required by `react-intl`
* `editorMessages`: the actual message strings for all supported locales for a particular resource. `editorMessages` collects all the strings for the interface, extensions and paint-editor.

#### Useful Scripts
openblock-l10n provides:
* `build-i18n-src`: script that uses babel and plugins to extract all `FormattedMessage` strings for translation. Combines the message from all the source files into one `en.json`
* `tx-push-src`: script to push the `en.json` file to Transifex. Requires that the environment variable `TX_TOKEN` is set with a value that has developer access to the OpenBlock projects on Transifex (i.e. OpenBlock Team only)

#### Versioning
openblock-l10n uses semantic versioning - breaking changes will increment the major version number, and new features (e.g. a new language) will increment the minor version number. However, the patch number is actually a datetime string. That way it's easy to see how recently the translations were updated.

In general, changes that require a PR (new functionality, new language) should increment the minor version. Pulling new translations from Transifex is automated and will commit to master directly.

## 🔧 Development Setup

### Prerequisites
```bash
# Install Node.js 18+ (recommended: use nvm)
nvm install 18.19.1
nvm use 18.19.1

# Or use the project's .nvmrc file
nvm use
```

### Installation
```bash
git clone https://github.com/lenzhang/openblock-l10n.git
cd openblock-l10n
npm install
```

### Build and Test
```bash
# Run all tests
npm test

# Build the project
npm run build

# Lint code
npm run lint
```

## 📄 License

This project maintains the same license as the original OpenBlock-l10n project.

---

## 🤝 Contributing

While this is a fork, we encourage contributions! Please:

1. Fork this repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

For translation contributions, please continue to use the original Transifex service: https://www.transifex.com/openblockcc/public/

## 📞 Support

- **Issues**: Please report issues on this repository's GitHub Issues page
- **Original Project**: For original OpenBlock-l10n issues, please refer to the [original repository](https://github.com/openblockcc/openblock-l10n)

---

**Thank you again to the OpenBlock team for creating this amazing internationalization library! 🙌**

# 依赖升级说明

## 升级概要

本次升级将项目的主要依赖更新到了较新的稳定版本，同时修复了一些安全漏洞和过时的依赖包。

## Node.js 版本要求

- **新要求**: Node.js >= 18.0.0, npm >= 8.0.0
- **推荐版本**: Node.js 18.19.1 (见 `.nvmrc` 文件)
- **注意**: 如果您当前使用的是 Node.js 16，需要先升级 Node.js 版本

## 主要升级内容

### Core Dependencies
- **@babel/cli**: 7.1.2 → 7.27.2
- **@babel/core**: 7.1.2 → 7.27.4
- **@transifex/api**: 4.2.5 → 7.1.4

### Dev Dependencies
- **webpack**: 4.6.0 → 5.99.9 (主要版本升级)
- **webpack-cli**: 3.1.2 → 5.1.4
- **eslint**: 8.17.0 → 8.57.1
- **babel-loader**: 8.0.5 → 9.2.1

### 包名更改
- `babel-plugin-react-intl` → `babel-plugin-formatjs` (原包已废弃)
- `@babel/plugin-proposal-object-rest-spread` → `@babel/plugin-transform-object-rest-spread` (已合并到ES标准)
- 移除 `babel-eslint` (已被 `@babel/eslint-parser` 替代)

## 破坏性变更

1. **Node.js 版本要求**: 需要 Node.js 18+ 才能运行
2. **Webpack 5**: 可能需要调整某些配置（如果有自定义配置）
3. **babel-plugin 变更**: 如果项目中直接引用了 `babel-plugin-react-intl`，需要更新为 `babel-plugin-formatjs`

## 升级后的好处

1. **安全性**: 修复了多个安全漏洞
2. **性能**: Webpack 5 和新版本的 Babel 提供更好的性能
3. **维护性**: 使用活跃维护的包版本
4. **兼容性**: 支持最新的 JavaScript 特性

## 如何升级 Node.js

### 使用 nvm (推荐)
```bash
# 安装指定版本
nvm install 18.19.1
nvm use 18.19.1

# 或者使用项目的 .nvmrc 文件
nvm use
```

### 使用 n
```bash
n 18.19.1
```

### 直接下载
访问 [Node.js 官网](https://nodejs.org/) 下载 LTS 版本

## 验证升级

升级 Node.js 后，运行以下命令验证：

```bash
# 检查版本
node --version  # 应该显示 v18.19.1 或更高
npm --version   # 应该显示 8.x 或更高

# 重新安装依赖
rm -rf node_modules package-lock.json
npm install

# 运行测试
npm test
```

## ✅ 升级完成状态

本次升级已成功完成，所有测试均通过！

### 修复的问题：
1. ✅ 升级了所有主要依赖到最新稳定版本
2. ✅ 修复了 Babel 插件配置（`@babel/plugin-proposal-object-rest-spread` → `@babel/plugin-transform-object-rest-spread`）
3. ✅ 修复了 Webpack 5 兼容性问题（移除了不支持的 `--colors` 选项）
4. ✅ 修复了 glob 模块的导入方式（新版本需要使用 `{globSync}`）
5. ✅ 移除了已废弃的依赖包

### 当前依赖版本：
- **Webpack**: 5.99.9 (从 4.6.0 升级)
- **@babel/core**: 7.27.4 (从 7.1.2 升级)
- **ESLint**: 8.57.1 (从 8.17.0 升级)
- **所有其他依赖**: 均已升级到最新稳定版本

### 测试结果：
- ✅ ESLint 检查通过
- ✅ JSON 语法检查通过
- ✅ 翻译验证通过
- ✅ Webpack 构建成功
- ✅ 所有测试通过

## 故障排除

如果遇到问题：

1. **清理缓存**: `npm cache clean --force`
2. **删除 node_modules**: `rm -rf node_modules package-lock.json`
3. **重新安装**: `npm install`
4. **检查 Node 版本**: 确保使用 Node.js 18+

## 回滚方案

如果需要回滚，可以使用备份的 `package.json.backup` 文件：

```bash
cp package.json.backup package.json
rm package-lock.json
npm install
```

## 下一步建议

1. **升级 Node.js**: 建议将本地和 CI/CD 环境升级到 Node.js 18+
2. **测试部署**: 在测试环境中验证所有功能
3. **更新文档**: 更新项目 README 中的 Node.js 版本要求
4. **CI/CD 更新**: 更新持续集成配置使用 Node.js 18+ 
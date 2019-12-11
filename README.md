# lerna-learn

## 命令

### 一、初始化

- 初始化：`lerna init`

- 添加模块：`lerna create @project/someModule`

### 二、添加依赖

- 所有模块添加依赖：`lerna add package | @project/someModule` // 也可以安装本地模块

- 指定模块添加依赖：`lerna add package --scope @project/someModule -D | -S --registry https://someRegistry.com`

- 模块之间添加依赖：`lerna add @project/module2 --scope @project/module1` // module2 添加到 module1 中

- 所有模块安装依赖：`lerna bootstrap`

### 三、卸载

- 所有模块卸载依赖：`lerna exec -- npm uninstall package`

- 指定模块卸载：`lerna exec -- npm uninstall package --scope @project/someModule`

- 所有模块清理依赖：`lerna clean`

### 四、迭代与发布

- 按指定版本迭代：`lerna version 0.0.2`

- 交互式流程迭代：`lerna version` // 包括 push，tag，release

- 自动 changelog：`lerna version --conventional-commits` // lerna.json 配置 command 同理

- 阻止默认推送：`lerna version --no-push`

- 发布：`lerna publish` // 包括 push，tag，release，publish

- 先通过 `version` 提交了，再发布：`lerna publish from-git`

# GitHub Action Demo

本仓库包含 GitHub Action 的示例工作流，用于学习和参考。

## 工作流说明

### 1. CI 工作流 (`ci.yml`)

- **触发条件**：推送到 `main` 分支或创建/更新针对 `main` 分支的 Pull Request
- **功能**：
  - 在 Ubuntu 环境上运行
  - 测试多个 Node.js 版本（14.x, 16.x, 18.x）
  - 执行 `npm ci` 安装依赖
  - 执行 `npm run build`（如果存在）
  - 执行 `npm test` 运行测试

### 2. GitHub Pages 部署工作流 (`pages.yml`)

- **触发条件**：推送到 `main` 分支
- **功能**：
  - 在 Ubuntu 环境上运行
  - 使用 Node.js 18
  - 执行 `npm ci` 安装依赖
  - 执行 `npm run build` 构建项目
  - 将 `./dist` 目录部署到 GitHub Pages

## 如何使用

1. **克隆仓库**：
   ```bash
   git clone https://github.com/your-username/workflow_demo.git
   cd workflow_demo
   ```

2. **添加项目代码**：
   - 确保项目包含 `package.json` 文件
   - 配置相应的 `build` 和 `test` 脚本

3. **推送代码**：
   ```bash
   git add .
   git commit -m "Add project files"
   git push origin main
   ```

4. **查看工作流执行**：
   - 进入 GitHub 仓库页面
   - 点击 "Actions" 标签
   - 查看工作流的执行状态和日志

## 配置说明

### CI 工作流配置
- 可在 `strategy.matrix.node-version` 中添加或修改 Node.js 版本
- 可根据项目需要调整构建和测试命令

### GitHub Pages 部署配置
- 确保项目构建后生成的文件位于 `./dist` 目录
- 如果构建输出目录不同，需修改 `publish_dir` 配置

## 版本变更

详细的版本变更记录请查看 [CHANGELOG.md](CHANGELOG.md)。
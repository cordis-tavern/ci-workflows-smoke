# ci-workflows-smoke

`ci-workflows` 的金丝雀仓库：**只跑 `dry-run`，不会真的发布到 npm**。

用途：改完 `cordis-tavern/ci-workflows` 的 `publish-npm.yml` 后，在这里推一个新 tag，
就能确认「调用方 → 可复用工作流 → 打包」整条链路还活着，而不必拿真包试错。

```bash
git tag v0.0.2 && git push origin v0.0.2
```

绿色 = 链路可用；红色 = 看 run 里哪一步断了（tag 解析 / Node·npm 版本 / 安装 / 构建 / 打包）。

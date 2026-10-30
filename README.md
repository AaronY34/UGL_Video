# UGL Social Video Workflow

用 ChatCut Desktop 从 UGL 上课、比赛和高尔夫原片中选段、标注并粗剪，再用 HyperFrames 做特效，加入固定片头片尾，导出竖屏社媒视频。

## 在另一台电脑安装

先确认 Codex 已连接 ChatCut Desktop 和 HyperFrames。然后把以下内容直接发给 Codex：

```text
Use $skill-installer to install https://github.com/AaronY34/UGL_Video/tree/main/skills/ugl-social-video-workflow
```

安装后重启 Codex。第一次运行时提供已有的固定片头、片尾文件路径。仓库不包含学员原片或品牌视频素材。

也可以下载 [ZIP 压缩包](dist/ugl-social-video-workflow.zip) 手动安装；步骤见 [INSTALL.md](skills/ugl-social-video-workflow/INSTALL.md)。

## 使用

```text
Use $ugl-social-video-workflow to make a UGL social video from the footage in this folder.
```

默认输出为英文为主、9:16、总长 15–30 秒。Codex 会先让你从三个故事线中选择，再从三个 3–5 秒的真实 HyperFrames 特效预览中选择。

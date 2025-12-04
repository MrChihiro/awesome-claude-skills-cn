---
name: video-downloader
description: 从 YouTube 和其他平台下载视频以供离线观看、编辑或归档。处理各种格式和质量选项。
---

# 视频下载器 (Video Downloader)

此技能将视频从 YouTube 和其他平台直接下载到你的计算机。

## 何时使用此技能

- 下载 YouTube 视频以供离线观看
- 保存教育内容以供参考
- 归档重要视频
- 获取视频文件以进行编辑或重新利用
- 从平台下载你自己的内容
- 保存会议演讲或网络研讨会

## 此技能做什么

1. **下载视频**：从 YouTube 和其他平台获取视频
2. **质量选择**：让你选择分辨率 (480p, 720p, 1080p, 4K)
3. **格式选项**：以各种格式下载 (MP4, WebM, 仅音频)
4. **批量下载**：可以下载多个视频或播放列表
5. **元数据保留**：保存标题、描述和缩略图

## 如何使用

### 基本下载

```
Download this YouTube video: https://youtube.com/watch?v=...
(下载此 YouTube 视频：...)
```

```
Download this video in 1080p quality
(以 1080p 质量下载此视频)
```

### 仅音频

```
Download the audio from this YouTube video as MP3
(将此 YouTube 视频的音频下载为 MP3)
```

### 播放列表下载

```
Download all videos from this YouTube playlist: [URL]
(下载此 YouTube 播放列表中的所有视频：[URL])
```

### 批量下载

```
Download these 5 YouTube videos:
1. [URL]
2. [URL]
...
(下载这 5 个 YouTube 视频：...)
```

## 示例

**用户**: "Download this YouTube video: https://youtube.com/watch?v=abc123" (下载此 YouTube 视频：...)

**输出**:
```
Downloading from YouTube...

Video: "How to Build Products Users Love"
Channel: Lenny's Podcast
Duration: 45:32
Quality: 1080p

Progress: ████████████████████ 100%

✓ Downloaded: how-to-build-products-users-love.mp4
✓ Saved thumbnail: how-to-build-products-users-love.jpg
✓ Size: 342 MB

Saved to: ~/Downloads/
```

**灵感来源：** Lenny 在他的时事通讯中的工作流

## 重要说明

⚠️ **版权与合理使用**
- 仅下载你有权下载的视频
- 遵守版权法和平台服务条款
- 用于个人、教育或合理使用目的
- 不要重新分发受版权保护的内容

## 提示

- 如果你需要较小的文件大小，请指定质量 (720p vs 1080p)
- 对播客或音乐使用仅音频以节省空间
- 下载到专用文件夹以保持有序
- 在慢速连接上下载前检查文件大小

## 常见用例

- **教育**：保存教程和课程以供离线学习
- **研究**：归档视频以供参考
- **内容创作**：从平台下载你自己的内容
- **备份**：在重要视频被删除之前保存它们
- **离线观看**：在没有互联网访问的情况下观看视频

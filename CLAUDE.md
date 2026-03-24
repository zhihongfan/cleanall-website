# CleanAll Website — 项目说明

## 项目概述
CleanAll 官网，单文件静态网站，支持中英文双语切换。

## 文件结构
```
CleanAll_website/
└── index.html   # 全部 CSS / HTML / JS 内联，无外部依赖
```

## GitHub 仓库
| 仓库 | 用途 | 地址 |
|---|---|---|
| `cleanall-website` | 官网独立仓库 + GitHub Pages | https://github.com/zhihongfan/cleanall-website |
| `cleanall_pro` | 主项目仓库，网站放在 `website/` 子目录 | https://github.com/zhihongfan/cleanall_pro |

## 部署
**官网（GitHub Pages）：**
```bash
git add index.html
git commit -m "描述"
git push origin main
```
访问地址：https://zhihongfan.github.io/cleanall-website/

**同步到 cleanall_pro/website/：**
```bash
cp index.html /tmp/cleanall_pro_tmp/website/
cd /tmp/cleanall_pro_tmp
git add website/index.html && git commit -m "描述" && git push origin main
```
> 注意：cleanall_pro 是独立仓库，每次需要先确认 `/tmp/cleanall_pro_tmp` 是否存在，不存在则重新 clone：
> `git clone https://github.com/zhihongfan/cleanall_pro.git /tmp/cleanall_pro_tmp`

## GitHub 认证
使用 GitHub CLI (`gh`)，已登录账号 `zhihongfan`。
推送前若报认证错误，执行：`gh auth setup-git`

## 中英文国际化（i18n）
- 语言检测：`localStorage` 记忆 > `navigator.language` 浏览器语言 > 默认英文
- 切换方式：导航栏 `中文 / EN` 按钮；移动端汉堡菜单内底部按钮
- 翻译数据：`index.html` 底部 `<script>` 内的 `i18n` 对象，`en` / `zh` 两套
- 文本绑定：纯文本用 `data-i18n="key"`，含 HTML 标签用 `data-i18n-html="key"`

## 中文文案风格
苹果发布会风格：极简、短句、有节奏感、有力度。
- 避免直译，追求意译
- 多用句号断句，制造停顿感
- 示例：「音乐、播客、视频——世界，安静了。」

## 产品信息
- 支持平台：macOS 13+、Windows 10+
- 安装包大小：~6.2 MB
- 定价：免费试用，买断解锁
- 核心功能：一键隐藏所有窗口 + 静音 + 打开掩护应用
- 特色功能：Guard Mode（守卫模式）——常驻菜单栏，激活后监测任意按键自动触发

# 开发者工具箱

> 18 个高频开发小工具装进一个 HTML 文件。零依赖、离线可用，所有计算都在你的浏览器里完成，**不上传任何数据**。

[English](README.md) | **简体中文**

## 里面有什么

| # | 工具 | 说明 |
|---|---|---|
| 1 | JSON 格式化 / 校验 | 格式化、压缩、转义 / 反转义；报错带行列定位 |
| 2 | Base64 编解码 | UTF-8 安全（中文不乱码），支持 URL 安全变体 |
| 3 | URL 编解码 | `encodeURIComponent` / `decodeURIComponent` / `encodeURI` |
| 4 | JWT 解码 | 解出 Header / Payload，标出过期状态（不校验签名） |
| 5 | 时间戳 ↔ 日期 | 秒 / 毫秒自动识别，给出本地时间、ISO、UTC |
| 6 | UUID 生成 | v4，一次最多 200 个 |
| 7 | 密码生成 | 自己选长度和字符集，走 crypto 随机源 |
| 8 | MD5 | 纯 JS 实现，同步返回 |
| 9 | SHA-1 / 256 / 512 | 走 Web Crypto（需要 https 或 localhost） |
| 10 | 正则测试 | 列出匹配和捕获组 |
| 11 | 文本对比（逐行） | LCS 逐行 diff，输出 `+` / `-` |
| 12 | 进制转换 | 2~36 进制互转，大数用字符串运算 |
| 13 | 命名风格转换 | camel / Pascal / snake / kebab / CONSTANT 一次给全 |
| 14 | HTML / JSON 转义 | 正反两个方向 |
| 15 | 颜色转换 | HEX / RGB / HSL 互转 + 相对亮度 |
| 16 | Crontab 解释 | 翻译成人话，并列出接下来 5 次执行时间 |
| 17 | chmod 权限计算 | 数字 ↔ `rwxr-xr-x` 互转 |
| 18 | 文本统计 | 字符 / 去空格 / 中文字数 / 词数 / 行数 / 段落 / UTF-8 字节 |

左边列表可以直接搜索过滤，所有工具都是同一套「输入 → 输出 → 复制」的操作方式。

## 怎么用

下载 `index.html` 双击打开就行。不用安装、不用构建、不用联网。

想用本地服务也可以：

```bash
python -m http.server 8000
# 打开 http://localhost:8000
```

> SHA 系列依赖 `crypto.subtle`，少数浏览器在 `file://` 下会禁用它。如果提示不支持，用上面的本地服务方式打开就好。

## 实现要点

- **零依赖**：所有算法都内联在文件里，包括 MD5、LCS 逐行 diff、Cron 解析、进制大数转换、redmean 颜色距离
- **确定性**：密码 / UUID 用 `crypto` 的随机源；MD5、diff 是纯函数，可以单独抽出来复用
- **不上传**：整个文件没有任何网络请求，连 `fetch` 都没用到

## 许可

MIT — 见 [LICENSE](LICENSE)。

# My blog base on ShokaX Can
## prerequisites
```bash
git
nodejs >= 22
pnpm >= 8
```
## 开始
ShokaX 即食罐头，使用 pnpm 加热即可食用，执行下列命令：
```bash
git clone https://github.com/qjm100/qjm100.github.io --depth=1
cd shokax-can
pnpm install
hexo s # 如果报错更换为 pnpm dlx hexo s
```

当前内容物版本：ShokaX v0.5.4 含 lightning-minify

## 创建链接
```bash
mklink /J .\themes\shokax .\node_modules\hexo-theme-shokax # windows CMD
# 或
cd ../themes && ln -s ../node_modules/hexo-theme-shokax shokax # Linux Bash
```
随后可以通过`themes/shokax`访问主题文件

修改了CI工作流，在.github/workflows/pages.yml
只需要提交代码到username.github.io仓库的main分支即可自动部署

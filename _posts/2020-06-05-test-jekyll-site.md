---
layout: post
---
# 日常更新操作流程

1. 进入文件夹  ~/nanoorchis.github.io/_posts 新建或者编辑文章。
2. 在 ~/nanoorchis.github.io/ 下运行 jekyll server，然后按提示的地址在浏览器中查看效果。
3. 修改完成后在文件夹 ~/mysite/nanoorchis.github.io下运行``cd ~/nanoorchis.github.io````git add --all``git commit -m "some commit"``git push -u origin master`
4. 等待几分钟。

# 初始化操作流程

1. 将仓库克隆到本地 Git clone 
2. 修改 Gemfile。注释掉全部Gem打头的语句。
3. Create a new Jekyll site 。执行jekyll new .
4. 启动预览，bundle exec jekyll serve。打开浏览器查看。

# .gitignore规则不生效的解决办法

把某些目录或文件加入忽略规则，按照上述方法定义后发现并未生效，原因是.gitignore只能忽略那些原来没有被追踪的文件，如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的。那么解决方法就是先把本地缓存删除（改变成未被追踪状态），然后再提交：

git rm -r --cached .
git add .
git commit -m 'update .gitignore'


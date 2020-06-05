---
layout: post
---
日常更新操作流程

进入文件夹  ~/mysite/nanoorchis.github.io/_posts

新建或者编辑文章。

在 ~/mysite/nanoorchis.github.io/ 下运行 jekyll server

然后按提示的地址在浏览器中查看效果。

修改完成后在文件夹 ~/mysite/nanoorchis.github.io下运行

cd ~/mysite/nanoorchis.github.io

git add --all

git commit -m "some commit"

git push -u origin master



重新来一遍

将仓库克隆到本地

Git clone 

Create a new Jekyll site 

jekyll new .

报错 Could not find gem 'minima (~> 2.5)' in any of the gem sources listed in your Gemfile.

尝试安装缺失的包 sudo gem install minima

依旧报错。clone minima包后一个个复制文件，执行new，看看需要哪个文件。

查看 Gemfile，有说明 remove the "gem "jekyll"" above and uncomment the line below. To upgrade, run `bundle update github-pages`.

报错缺的包都不是必须的。

bundle exec jekyll serve

打开流星器查看


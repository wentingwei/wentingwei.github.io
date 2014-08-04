#Sublime Text And Markdown

##1.安装MarkdownBuild和MarkdownPreview

 - Command+Shift+P 输入Install 然后看到Package Control：Install Package，输入MarkdownBuild和MarkdownPreview
 - 如果没有，请先安装Package Control,Command+~ 输入下面代码

> import urllib2,os; pf='Package Control.sublime-package';
> ipp=sublime.installed_packages_path(); os.makedirs(ipp) if not
> os.path.exists(ipp) else None;
> urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler()));
> open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace('
> ','%20')).read()); print 'Please restart Sublime Text to finish
> installation'

##2.在sublime中写Markdown的文本

 - Command+Shift+P选择Markdown Preview : Preview in Browser
 - 选择github，然后浏览器会显示出你的文本
# dotfiles
my dotfiles manager

## Windows
使用 `mklink` 链接自己的dotfile文件到指定目录统一管理，以后切换电脑后可以下载配置文件后替换
管理员模式下执行
```shell
mklink 目标目录  源目录
```
先将home目录的配置移动到指定的保存目录下,，然后执行，这样在配置文件中的文件就是软链接，而真实文件放在自己的dotfile管理目录里
```shell
mklink C:\Users\iPhase2\.zshrc D:\workspace\dotfiles\myconfig\zsh\.zshrc 
```
## bat脚本
脚本为测试用例，方便批量软连接配置文件
```shell
@echo off

echo prepare ...
Pause

set folder=D:\workspace\dotfiles\logs
REM 判断 D:\workspace\dotfiles\logs 目录是否存在，如果不存在则创建该目录  
if exist %folder% (  
  echo it shi cunzaide  
  if exist %folder%\info.log (  
    echo file is exist then delete it;  
    del %folder%\info.log  
  )  
) else (  
  mkdir %folder%  
)

REM 创建链接文件  
mklink %folder%\info.log  D:\home\logs\info.log 

REM 输出创建目录和链接文件的成功与否  
echo success... : %folder%
Pause  
```
## idea action
将action映射到vim快捷键
显示所有idea的action
```shell
actionlist 
```
匹配method相关的action
```shell
actionlist method
```
# Vim 键位图
![image](https://github.com/Contentsearch/dotfiles/assets/51782090/c66a8ab0-d353-4de2-b791-a877bf5b84a8)

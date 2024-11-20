# Delphi Docker Build Environment
![License](https://img.shields.io/github/license/delphilite/DockerFile)
![stars](https://img.shields.io/github/stars/delphilite/DockerFile.svg)

[English](./README.md) | [Chinese](./README.zh-CN.md)

## 项目由来

之前有网友问过 Delphi Lite 能否提供 Docker 封装，简化 Windows 下环境的构造，当时给推荐了这个：

https://hub.docker.com/r/magicxor/radstudio/tags

这个项目的作者生猛，基本上是基于官方原版 iso 直接硬解、命令拷贝、环境设置，差不多 99% 的手工还原了原始安装，领悟等实在是佩服佩服！

不过遗憾因为某些原因，10.x 之后不见更新，原始网站也找不到了。以下是网上能找到的一些镜像：

https://github.com/pa-0/docker-RADstudio
https://gitflic.ru/project/binarynomad/radstudio-docker

于是，趁十一空闲，断断续续的也手搓一个，兴许实用说不上，更多只是兴趣？

当前 Dockerfile 还是 for Delphi XE2 和 Delphi 12，不过有这两个打样，其他版本、Windows 2016/19/22 应该都可以依葫芦画瓢

## 其他信息

1. 基于 Delphi Lite 的 Inno setup 安装制作 Docker Image 还是很容易
2. 基于 Windows Server 的 Docker 功能上确实和 Linux 的还是有差距，譬如 为了最小化容器、尽量合并 Layer 用了些 Magic
3. 不过 Windows 下，港真也没觉得封装一个 Docker Builder 有多大便利性，固定服务器 + FinalBuilder、Jenkins 他不香么
4. 初步 Delphi XE2-12 一切正常，大家有问题及时反馈，欢迎 PR
5. 关于 DockerHub 国内被限制，网上自己搜加速吧；也是这个原因，D12 完整版大小 29.7G，实在是 ...

## 特别说明

1. 这个版本的来源于官方 Beta/RTM 正式试用版，版权归 Embarcadero 所有，请在下载后 24 小时内删除。
2. 重新打包纯粹个人兴趣所致，希望能方便网友测试、交流。作为 Delphi 多年的 Fans，我们都希望 Delphi 能做得更好！
3. 如果您觉得 Delphi 不错，请购买正版，更好的支持 Embarcadero 的发展！

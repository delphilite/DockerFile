# Delphi Docker Build Environment
![License](https://img.shields.io/github/license/delphilite/DockerFile)
![stars](https://img.shields.io/github/stars/delphilite/DockerFile.svg)

[English](./README.md) | [Chinese](./README.zh-CN.md)

## 项目由来

之前有网友问过，当时给推荐了这个：

https://hub.docker.com/r/magicxor/radstudio/tags

作者生猛，基本上基于官方原版 iso 直接硬解、安装，实在佩服佩服！

不过遗憾 10.x 之后不见更新，原始网站也找不到了，以下是网上能找到的一些镜像：

https://github.com/pa-0/docker-RADstudio
https://gitflic.ru/project/binarynomad/radstudio-docker

趁十一空闲，断断续续的也手搓一个，当前 for Delphi XE2 和 Delphi 12，不过有这两个打样，其他版本、Windows 2016/19/22 应该可以依葫芦画瓢

## 其他信息

话说 1，基于 Delphi Lite 的 Inno setup 安装制作 Docker Image 还是很容易
话说 2，基于 Windows Server 的 Docker 功能上确实和 Linux 的还是有差距，譬如 为了最小化容器、尽量合并 Layer 用了些 magic
话说 3，不过 Windows 下，港真也没觉得封装一个 Docker Builder 有多大便利性，固定服务器 + FinalBuilder、Jenkins 他不香么

初步 Delphi XE2-12 一切正常，大家有问题及时反馈 ！？

## 特别说明

1、这个版本的来源于官方 Beta/RTM 正式试用版，版权归 Embarcadero 所有，请在下载后 24 小时内删除。
2、重新打包纯粹个人兴趣所致，希望能方便网友测试、交流。作为 Delphi 多年的 Fans，我们都希望 Delphi 能做得更好！
3、如果您觉得 Delphi 不错，请购买正版，更好的支持 Embarcadero 的发展！

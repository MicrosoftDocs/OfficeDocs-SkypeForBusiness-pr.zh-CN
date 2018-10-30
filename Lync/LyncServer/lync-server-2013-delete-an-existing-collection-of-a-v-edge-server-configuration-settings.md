---
title: 删除 A/V 边缘服务器配置设置的现有集合
TOCTitle: 删除 A/V 边缘服务器配置设置的现有集合
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49888444
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除 A/V 边缘服务器配置设置的现有集合

 

_**上一次修改主题：** 2012-11-01_

利用 A/V 边缘服务，内部用户（已登录到组织网络的用户）可与外部用户（未登录到组织网络的用户）共享音频和视频。A/V 边缘服务主要是通过使用 A/V 边缘配置设置来管理的，可以在站点作用域或服务作用域配置此设置（即，可为单个 A/V 边缘服务器配置此设置）。

在安装 Lync Server 时，将为您创建一个 A/V 边缘配置设置全局集合。无法删除此全局集合。但是，您可使用 Lync Server 命令行管理程序和 Remove-CsAVEdgeConfiguration cmdlet“重置”此全局集合；这明显意味着全局集合中的所有属性值将重置为其默认值。例如，如果您将 MaxTokenLifetime 属性设置为 16 小时，则该属性将重置为其 8 小时的默认值。

但是，可使用 Remove-CsAVEdgeConfiguration cmdlet 删除在站点作用域或服务作用域创建的自定义设置集合。如果您删除站点设置，则相应站点内的 A/V 边缘服务器将由全局设置进行管理。如果您删除服务作用域设置，则相应服务器之后将由其站点设置（如果存在）或由全局设置进行管理（如果没有可用的站点设置）。

有关详细信息，请参阅 [Remove-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAVEdgeConfiguration) cmdlet 的帮助主题。

## 重置全局集合

  - 以下命令重置 A/V 边缘配置设置的全局集合：
    
        Remove-CsAVEdgeConfiguration -Identity "global"

## 删除站点作用域中的集合

  - 此命令删除应用于 Redmond 站点的 A/V 边缘配置设置：
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

## 删除服务作用域中的集合

  - 此命令删除应用于 A/V 边缘服务器 atl-edge-001.litwareinc.com 的设置：
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

## 另请参阅

#### 任务

[返回 A/V 边缘服务器配置信息](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[创建或修改 A/V 边缘服务器配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  

#### 其他资源

[Lync Server 2013 中的音频/视频 (A/V) 边缘服务器](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAVEdgeConfiguration)


---
title: 创建或修改 A/V 边缘服务器配置设置的集合
TOCTitle: 创建或修改 A/V 边缘服务器配置设置的集合
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49888396
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改 A/V 边缘服务器配置设置的集合

 

_**上一次修改主题：** 2012-11-01_

利用 A/V 边缘服务，内部用户（已登录到组织网络的用户）可与外部用户（未登录到组织网络的用户）共享音频和视频。A/V 边缘服务主要是通过使用 A/V 边缘配置设置来管理的，可以在站点作用域或服务作用域配置此设置（即，可为单个 A/V 边缘服务器配置此设置）。

在安装 Lync Server 时，将为您创建一个 A/V 边缘配置设置全局集合。除此之外，可使用 Lync Server 命令行管理程序和 New-CsAVEdgeConfiguration cmdlet 在站点作用域或服务作用域创建新的设置（即，为单个 A/V 边缘服务器创建新的设置）。如果您创建新的设置，请记住：

  - 在服务作用域（即在单个服务器上）配置的设置优先于所有其他设置。

  - 在站点作用域配置的设置优先于在全局作用域配置的设置。但是，服务作用域设置还将替代站点作用域设置。

  - 全局作用域的设置仅当未在单个服务器上配置服务设置和服务器所在的网站没有网站设置的情况下使用。

随后，可使用 Set-CsAVEdgeConfiguration cmdlet 修改任何设置。有关详细信息，请参阅 [New-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAVEdgeConfiguration) 和 [Set-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAVEdgeConfiguration) cmdlet 的帮助主题。

## 在站点作用域创建新的 A/V 边缘配置设置

  - 以下命令为 Redmond 站点创建新的 A/V 边缘配置设置集合：
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

## 在站点作用域创建自定义 A/V 边缘配置设置

  - 由于未包含其他参数，因此这些新设置将使用 A/V 边缘服务的默认值。或者，您可以添加其他参数和参数值来创建自定义集合。例如，此命令将 MaxTokenLifetime 属性设置为 4 小时（04 小时:00 分钟:00 秒）：
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

## 在服务作用域创建自定义 A/V 边缘配置设置

  - 此命令将创建一个适用于 A/V 边缘服务器 atl-edge-001.litwareinc.com 的相似集合：
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

## 修改现有 A/V 边缘配置设置

  - 在此示例中，Set-CsAVEdgeConfiguration cmdlet 用于将 Redmond 站点的最大令牌生存期更改为 12 小时：
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

## 另请参阅

#### 任务

[返回 A/V 边缘服务器配置信息](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[删除 A/V 边缘服务器配置设置的现有集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  

#### 其他资源

[Lync Server 2013 中的音频/视频 (A/V) 边缘服务器](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAVEdgeConfiguration)  
[Set-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAVEdgeConfiguration)


---
title: 返回 A/V 边缘服务器配置信息
TOCTitle: 返回 A/V 边缘服务器配置信息
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49888563
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 返回 A/V 边缘服务器配置信息

 

_**上一次修改主题：** 2012-11-01_

A/V 边缘服务为您的内部用户（已登录到您的组织网络的用户）提供一种与外部用户（未登录到您的组织网络的用户）共享音频和视频的方法。A/V 边缘服务主要通过使用 A/V 边缘配置设置进行管理，即可在站点范围或服务范围进行配置（也就是，可以针对个别 A/V 边缘服务器进行配置）的设置。

要返回有关您的组织中使用的 A/V 边缘配置设置的信息，必须使用 Lync Server 命令行管理程序和 Get-CsAVEdgeConfiguration cmdlet。有关详细信息，请参阅 [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet 的帮助主题。

从 Get-CsAVEdgeConfiguration cmdlet 返回的信息将看起来与以下类似：

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

## 返回所有 A/V 边缘配置设置的信息

  - 以下命令会返回有关您的组织中使用的所有 A/V 边缘配置设置的信息：
    
        Get-CsAVEdgeConfiguration

## 返回站点作用域 A/V 边缘配置设置的信息

  - 要返回有关特定的 A/V 边缘配置设置集合的信息，请在运行 Get-CsAVEdgeConfiguration cmdlet 时指定该集合的 Identity。例如，以下命令仅返回应用到 Redmond 站点的设置的信息：
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

## 返回服务作用域 A/V 边缘配置设置的信息

  - 以下命令仅返回应用到特定 A/V 边缘服务器的设置的信息：
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

## 另请参阅

#### 任务

[创建或修改 A/V 边缘服务器配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[删除 A/V 边缘服务器配置设置的现有集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  

#### 其他资源

[Lync Server 2013 中的音频/视频 (A/V) 边缘服务器](lync-server-2013-audio-video-a-v-edge-servers.md)


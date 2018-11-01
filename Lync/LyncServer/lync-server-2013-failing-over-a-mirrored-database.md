---
title: Lync Server 2013：对镜像数据库进行故障转移
TOCTitle: 对镜像数据库进行故障转移
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204991(v=OCS.15)
ms:contentKeyID: 49313206
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中对镜像数据库进行故障转移

 

_**上一次修改主题：** 2014-03-14_

如果已将后端数据库配置为使用具有见证的同步镜像，则故障转移是自动的。如果已配置没有见证的同步镜像，则可使用以下过程进行故障转移并返回数据库。即使也配置见证，也可以使用这些过程手动对数据库进行故障转移和故障回复。

## 故障转移到后端数据库

1.  在故障转移之前，通过键入以下 cmdlet 确定哪个后端数据库是主体，哪个是镜像：
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  如果在此池中承载 中央管理存储，请键入以下 cmdlet，以确定 中央管理存储的主体和镜像：
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  对用户数据库执行故障转移：
    
      - 如果主体已出现故障并且您要故障转移到镜像，请键入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - 如果镜像已出现故障并且您要故障转移到主体，请键入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  如果池承载 中央管理服务器，请对 中央管理存储执行故障转移。
    
      - 如果主体已出现故障并且您要故障转移到镜像，请键入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - 如果镜像已出现故障并且您要故障转移到主体，请键入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose


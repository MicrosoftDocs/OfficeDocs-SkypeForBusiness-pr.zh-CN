---
title: Lync Server 2013：配置现有中央管理服务器
TOCTitle: 配置现有中央管理服务器
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205315(v=OCS.15)
ms:contentKeyID: 49314393
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置现有中央管理服务器

 

_**上一次修改主题：** 2013-02-21_

如果您从现有 Lync Server 2013 部署中重用 中央管理服务器，则必须下面介绍的过程以确保 Lync Server 控制面板 和 Windows PowerShell 正常运行。

## 配置现有 中央管理服务器

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  使用 **Update-CsAdminRole** cmdlet 更新存储在 中央管理服务器中的基于角色的访问控制 (RBAC) 角色。
    
    > [!NOTE]  
    > 除非出错，否则不应有任何输出。
    


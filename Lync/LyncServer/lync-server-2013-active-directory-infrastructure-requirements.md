---
title: Lync Server 2013：Active Directory 基础结构要求
TOCTitle: Active Directory 基础结构要求
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412955(v=OCS.15)
ms:contentKeyID: 49314135
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的 Active Directory 基础结构要求

 

_**上一次修改主题：** 2016-12-08_

开始为 Lync Server 2013 准备 Active Directory 域服务 的过程之前，请确保您的 Active Directory 基础结构满足以下先决条件：

  - 部署 Lync Server 的林中的所有域控制器（其中包括所有全局编录服务器）运行以下操作系统之一：
    
      - Windows Server 2012 R2 操作系统
    
      - Windows Server 2012 操作系统
    
      - Windows Server 2008 R2 操作系统
    
      - Windows Server 2008 操作系统
    
      - Windows Server 2008 Enterprise 32 位版本
    
      - 32 位或 64 位版本的 Windows Server 2003 R2 操作系统
    
      - 32 位或 64 位版本的 Windows Server 2003 操作系统

  - 在其中部署 Lync Server 的所有域都提升到 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的域功能级别。

  - 在其中部署 Lync Server 的林提升到 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的林功能级别。
    
    > [!NOTE]  
    > 要更改域或林的功能级别，请参阅 TechNet 库中的“提升域和林的功能级别”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=263775" class="uri">http://go.microsoft.com/fwlink/?linkid=263775</a>。
    


  - 在部署 Lync Server 计算机或用户的每个域中部署全局编录。

Lync Server 2013 支持 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 和 Windows Server 2003 操作系统中的通用组。通用组的成员可包括域树或林中任何域中的其他组和帐户，并且可将域树或林中任何域中的权限分配给这些成员。通用组支持与管理员委派相结合，可简化对 Lync Server 部署的管理。例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。


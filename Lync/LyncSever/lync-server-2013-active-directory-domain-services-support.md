---
title: Lync Server 2013：Active Directory 域服务支持
TOCTitle: Active Directory 域服务支持
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412831(v=OCS.15)
ms:contentKeyID: 49313953
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Active Directory 域服务支持

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 使用 中央管理存储存储服务器和服务的配置数据，而不是像过去那样依赖 Active Directory 域服务 存储该信息。 Lync Server 2013 仍在 AD DS 中存储以下内容：

  - **架构扩展**
    
      - 用户对象扩展
    
      - 用于维护与支持的早期版本向后兼容的 Lync Server 2010 和 Office Communications Server 2007 R2 类扩展

  - **数据**（存储在 Lync Server 2013 扩展架构和现有类中）
    
      - 用户 SIP URI 和其他用户设置
    
      - 应用程序的联系人对象（例如， 响应组应用程序和 会议助理应用程序）
    
      - 为实现向后兼容而发布的数据
    
      - 中央管理存储的服务控制点 (SCP)
    
      - Kerberos 身份验证帐户（可选计算机对象）

本节介绍 Lync Server 2013 的 AD DS 支持要求。有关拓扑支持的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中支持的 Active Directory 拓扑](lync-server-2013-supported-active-directory-topologies.md)。

## 支持的域控制器操作系统

Lync Server 2013 支持运行以下操作系统的域控制器：

  - Windows Server 2012 R2 操作系统

  - Windows Server 2012 操作系统

  - Windows Server 2008 R2 操作系统

  - Windows Server 2008 操作系统

  - Windows Server 2008 Enterprise 32 位版本

  - 32 位或 64 位版本的 Window Server 2003 R2 操作系统

  - 32 位或 64 位版本的 Windows Server 2003 操作系统

## 林和域功能级别

必须将部署有 Lync Server 2013 的所有域提升到 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的域功能级别。

必须将部署有 Lync Server 2013 的所有林提升到 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的林功能级别。

## 对只读域控制器的支持

Lync Server 2013 支持包含只读域控制器或只读全局编录服务器的 Active Directory 域服务 部署，前提是这些部署中存在可写域控制器。

## 域名

Lync Server 不支持单标签域。例如，支持具有名为 **contoso.local** 的根域的林，但不支持名为 **local** 的根域。有关详细信息，请参阅 Microsoft 知识库文章 300684“关于如何为使用单标签 DNS 名称的域配置 Windows 的信息”，网址为 <http://go.microsoft.com/fwlink/?linkid=143752>。

> [!NOTE]  
> Lync Server 不支持重命名域。如果需要重命名部署有 Lync Server 的域，则需要先卸载 Lync Server，然后重命名域，最后重新安装 Lync Server。



## 锁定的 AD DS 环境

在锁定的 AD DS 环境中，通常将用户对象和计算机对象放置在禁用了权限继承的特定组织单位 (OU) 中，以帮助确保管理委派的安全以及允许使用组策略对象 (GPO) 实施安全策略。可以在锁定的 Active Directory 环境中部署 Lync Server 2013。有关在锁定的环境中部署 Lync Server 的要求的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。


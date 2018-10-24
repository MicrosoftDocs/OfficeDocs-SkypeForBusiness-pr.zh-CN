---
title: 最佳做法分析器的组成员身份和用户权限要求
TOCTitle: 最佳做法分析器的组成员身份和用户权限要求
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg591354(v=OCS.15)
ms:contentKeyID: 49314787
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 最佳做法分析器的组成员身份和用户权限要求

 

_**上一次修改主题：** 2012-10-21_

要成功运行最佳做法分析器，您用于登录的用户帐户必须是本地计算机上 Administrators 组的成员。另外，要扫描您的环境，用户帐户必须是下列组的成员：

  - **Domain Admins** - 枚举 Active Directory 域服务信息和呼叫域控制器和全局目录服务器上的 Windows Management Instrumentation (WMI) 提供商。

  - **Administrators** - 在每个 Lync Server 2013 内部计算机和每个边缘服务器上呼叫 Windows Management Instrumentation (WMI) 提供商和访问注册表时需要。

  - **RTCUniversalReadOnlyAdmins** - 完全或委派只读 Lync Server 2013 管理权限。

  - **Exchange View Only Administrator** - Microsoft Exchange 组织上的完全或委派的 Exchange View Only Administrator。

如果您的用户帐户没有充分的用户权限，则您有两个选项：

  - 在命令提示符下，使用 **runas** 命令在具有充分用户权限的帐户下运行该工具。语法如下所示：
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - 在“连接到 Active Directory”页面上，为您计划用于运行最佳做法分析器的帐户设置凭据。单击“显示高级登录选项”。可以输入三个帐户：一个连接到 Active Directory 域服务、一个连接到 Lync Server 2013边缘服务器和一个连接到 Exchange Server。如果您不指定这些任何帐户，则使用用于登录和运行最佳做法分析器的帐户。


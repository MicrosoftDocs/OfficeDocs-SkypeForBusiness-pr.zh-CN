---
title: 'Lync Server 2013: 为智能卡身份验证配置企业 CA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 890a69d1c863702db0a70cfb2ce3d61f6a75eeae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中配置用于智能卡身份验证的企业 CA

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-07-03_

以下部分介绍了如何配置企业根证书颁发机构 (CA) 以支持智能卡身份验证。 有关如何安装企业根 CA 的详细信息, 请参阅在以下位置[http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)安装企业根证书颁发机构。

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>配置企业根证书颁发机构以支持智能卡身份验证

以下步骤介绍如何配置企业根 CA 以支持智能卡身份验证：

1.  使用域管理员帐户登录到企业 CA 计算机。

2.  启动系统管理器，并验证是否已安装“证书颁发机构 Web 注册”角色。

3.  从“管理工具”**** 菜单中，打开“证书颁发机构”**** 管理控制台。

4.  在导航窗格中，展开“证书颁发机构”****。

5.  右键单击“证书模板”****，选择“新建”****，然后选择“要颁发的证书模板”****。

6.  选择“注册代理”****、“智能卡用户”**** 和“智能卡登录”****。

7.  单击“**确定**”。

8.  右键单击“证书模板”****。

9.  选择“管理”****。

10. 打开智能卡用户模板的属性。

11. 单击“安全”**** 选项卡。

12. 更改权限，如下所示：
    
      - 添加具有读取/注册（允许）权限的各个用户 AD 帐户，或者
    
      - 添加具有读取/注册（允许）权限且包含智能卡用户的安全组，或者
    
      - 添加具有读取/注册（允许）权限的域用户组

</div>

</div>

<span> </span>

</div>

</div>

</div>


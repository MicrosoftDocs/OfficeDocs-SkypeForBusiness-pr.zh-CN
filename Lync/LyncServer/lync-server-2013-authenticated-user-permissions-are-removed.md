---
title: Lync Server 2013：删除经过身份验证的用户权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45080baa0839731808aefcc31c1551bfab5293db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>在 Lync Server 2013 中删除经过身份验证的用户权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

在锁定的 Active Directory 环境中，从默认的 Active Directory 容器中删除经过身份验证的用户访问控制项（Ace），包括用户、配置或系统以及用户和计算机的组织单位（Ou）。存储对象。 删除经过身份验证的用户 Ace 可防止对 Active Directory 信息进行读取访问。 但是，删除 Ace 会为 Lync Server 2013 创建问题，因为它依赖于这些容器的读取权限以允许用户运行域准备。

在这种情况下，域管理员组中的成员身份（若要运行域准备、服务器激活和池创建）不再授予对存储在默认容器中的 Active Directory 信息的读取权限。 您必须手动授予对林根域中各个容器的读取访问权限，以检查先决条件林准备过程是否已完成。

若要使用户能够在任何非林根域上运行域准备、服务器激活或池创建，您可以选择以下选项：

  - 使用作为 Enterprise Admins 组成员的帐户来运行域准备。

  - 使用属于 Domain Admins 组成员的帐户，并为此帐户授予对林根域中以下每个容器的读取访问权限：
    
      - 域
    
      - 配置或系统

如果不想使用作为 Enterprise Admins 组成员的帐户来运行域准备或其他安装任务，请明确授予要在林根的相关容器上使用 "读取" 访问权限的帐户。

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>向用户授予对林根域中容器的读取访问权限

1.  使用作为林根域的 Domain Admins 组成员的帐户登录加入到林根域的计算机。

2.  为林根域运行 adsiedit。
    
    如果从域、配置或系统容器中删除了经过身份验证的用户 Ace，则必须向容器授予只读权限，如以下步骤所述。

3.  右键单击容器，然后单击 "**属性**"。

4.  单击“安全性”**** 选项卡。

5.  单击“**高级**”。

6.  在“**权限**”选项卡上，单击“**添加**”。

7.  使用以下格式键入接收权限的用户或组的名称： `domain\account name`，然后单击 **"确定"**。

8.  在 "**对象**" 选项卡上的 "**应用**于" 中，单击 "**仅此对象**"。

9.  在 "**权限**" 中，通过单击 "**允许**列：**列表内容**"、"**读取所有属性**" 和 "**读取权限**"，选择以下允许 ace。

10. 单击“**确定**”两次。

11. 对步骤2中列出的任何相关容器重复这些步骤。

</div>

</div>

<span> </span>

</div>

</div>

</div>


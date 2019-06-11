---
title: Lync Server 2013：向 Active Directory 中添加 Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc057318a0d241a28b8529802ea9f2016a1f5b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>在 Lync Server 2013 中向 Active Directory 中添加 Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-23_

如果你计划部署 Survivable 分支设备, 则必须将 Survivable 分支装置添加到 Active Directory 域服务。 在中心站点执行此过程。

<div>


> [!IMPORTANT]  
> 仅在部署 Survivable 分支设备时执行此过程。 如果要部署 Survivable 分支服务器, 请不要执行此操作。



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>将 Survivable 分支装置添加到 Active Directory 域服务

1.  作为企业管理员组的成员登录到成员服务器。

2.  单击 "**开始**", 单击 "**管理工具**", 然后单击 " **Active Directory 用户和计算机**"。

3.  在 "**操作**" 菜单上, 单击 "**新建**", 然后单击 "**计算机**"。

4.  在 "**新建对象-计算机**" 对话框中, 键入 Survivable 分支装置计算机对象的名称 (例如, BranchOffice1), 然后单击 "**更改**"。

5.  在 "**选择用户或组**" 对话框中, 添加 "RTCUniversalSBATechnicians" 组, 然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 分支站点的 RTCUniversalSBATechnicians 组的成员将在以后将此设备添加到该域。

    
    </div>

6.  单击 **"确定"** 保存 Survivable 分支装置计算机对象。

7.  单击 "**开始**", 单击 "**管理工具**", 然后单击 " **ADSI 编辑**"。

8.  在 " **ADSI 编辑**" 中, 右键单击您在前面的步骤中创建的计算机对象, 然后单击 "**属性**"。

9.  在 "属性" 列表中, 单击 " **servicePrincipalName**", 然后单击 "**编辑**"。

10. 在 "**要添加的值**" 字段中,\<键入 HOST\> / \<SBA FQDN\> , 其中 SBA fqdn 是你的 Survivable 分支装置的完全限定的域名 (FQDN)。 例如, 键入**HOST/BranchOffice1**。

11. 单击 **"确定"** 保存**servicePrincipalName**属性设置, 然后单击 **"确定"** 以保存计算机对象属性。

12. 在 " **Active Directory 用户和计算机**" 中, 右键单击 "**用户**", 单击 "**新建**", 然后单击 "**用户**"。

13. 在向导中输入信息, 为 Survivable 分支装置技术人员创建域用户帐户。

14. 在 " **Active Directory 用户和计算机**" 中, 单击 "**用户**", 右键单击用户对象, 然后单击 "**添加到组**"。

15. 在 "**输入要选择的对象名称**" 中, 键入**RTCUniversalSBATechnicians**, 然后单击 **"确定"**。

16. 对每个分支站点技术人员重复步骤12-15。

**下一步**:[在 Lync Server 2013 中向拓扑添加分支站点](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：为虚拟智能卡配置 Windows 8
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb8fe9fb9bcca80e7e84f19bdc484dc693b1ee68
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>为在 Lync Server 2013 中使用虚拟智能卡配置 Windows 8

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-03_

部署双因素身份验证和智能卡技术时要考虑的一个因素是实施成本。 Windows 8 提供了许多新的安全功能，最感兴趣的新功能之一是支持虚拟智能卡。

对于安装了符合规范版本1.2 的受信任的平台模块（TPM）芯片的计算机，组织现在可以获得智能卡登录的好处，而无需在硬件中进行任何额外的投资。 有关详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)使用虚拟智能卡和 Windows 8。

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>为虚拟智能卡配置 Windows 8

1.  使用启用了 Lync 的用户的凭据登录到 Windows 8 计算机。

2.  在 Windows 8 "开始" 屏幕上，将光标移到屏幕的右下角。

3.  选择 "**搜索**" 选项，然后搜索 "**命令提示符**"。

4.  右键单击 "**命令提示符**"，然后选择 "**以管理员身份运行**"。

5.  通过运行以下命令打开受信任的平台模块（TPM）管理控制台：
    
        Tpm.msc

6.  在 TPM 管理控制台中，验证你的 TPM 规范版本是否至少为1。2
    
    <div>
    

    > [!NOTE]  
    > 如果您收到一个指示找不到兼容的信任平台模块（TPM）的对话框，请验证该计算机是否具有兼容的 TPM 模块以及是否已在系统 BIOS 中启用。

    
    </div>

7.  关闭 TPM 管理控制台

8.  在命令提示符处，使用以下命令创建新的虚拟智能卡：
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > 若要在创建虚拟智能卡时提供自定义 PIN 值，请改用/pin prompt。

    
    </div>

9.  在命令提示符处，通过运行以下命令打开 "计算机管理" 控制台：
    
        CompMgmt.msc

10. 在 "计算机管理" 控制台中，选择 "**设备管理**"。

11. 展开 "**智能卡读取器**"。

12. 验证是否已成功创建新的虚拟智能卡读卡器。

</div>

</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: b6298f7aa6a500a71c0b3732dd2f3d180e7192d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>配置用于将虚拟智能卡与 Lync Server 2013 结合使用的 Windows 8

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-07-03_

部署双重身份验证和智能卡技术时要考虑的一个因素是实施成本。 Windows 8 提供了许多新的安全功能，最有趣的新增功能之一是支持虚拟智能卡。

对于配备了符合规范版本 1.2 要求的受信任的平台模块 (TPM) 芯片的计算机，组织现在可以享受智能卡登录带来的好处，不必在硬件方面做任何额外投资。 有关详细信息，请参阅在[http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)Windows 8 中使用虚拟智能卡。

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>为 Windows 8 配置虚拟智能卡

1.  使用启用了 Lync 的用户的凭据登录到 Windows 8 计算机。

2.  在 Windows 8“开始”屏幕中，将您的光标移动到屏幕右下角。

3.  选择“搜索”**** 选项，然后搜索**Command Prompt**。

4.  右键单击“命令提示符”****，然后选择“以管理员身份运行”****。

5.  通过以下命令打开受信任的平台模块 (TPM) 管理控制台：
    
        Tpm.msc

6.  从 TPM 管理控制台中，验证您的 TPM 规范版本是否至少为 1.2
    
    <div>
    

    > [!NOTE]  
    > 如果您收到一个对话框表明找不到兼容的受信任的平台模块 (TPM)，请验证计算机是否具有兼容的 TPM 模块以及是否在系统 BIOS 中启用了它。

    
    </div>

7.  关闭 TPM 管理控制台

8.  从命令提示符处，使用以下命令创建新的虚拟智能卡：
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > 要在创建虚拟智能卡时提供自定义 PIN 值，请使用 /pin 提示符。

    
    </div>

9.  从命令提示符处，通过运行以下命令来打开计算机管理控制台：
    
        CompMgmt.msc

10. 在计算机管理控制台中，选择“设备管理”****。

11. 展开“智能卡读取器”****。

12. 验证是否已成功创建新的智能卡读取器。

</div>

</div>

<span> </span>

</div>

</div>

</div>


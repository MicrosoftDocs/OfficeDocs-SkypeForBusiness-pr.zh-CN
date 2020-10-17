---
title: Lync Server 2013：为 Lync Phone Edition 配置安全设置
description: Lync Server 2013：为 Lync Phone Edition 配置安全设置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e6a6488db66a8497930ee6b2d1aec6fc8b0b2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564348"
---
# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>在 Lync Server 2013 中配置 Lync Phone Edition 的安全设置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

通过 SIP 安全设置和电话锁定设置，帮助改进运行 Lync Phone Edition 的设备的安全性。

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>为 Lync Phone Edition 配置安全设置

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“客户端”****，然后单击“设备配置”****。

4.  在“设备配置”**** 页上的设备配置列表中，双击要更改安全设置的配置。

5.  在“编辑设备配置”**** 的“SIP 安全”**** 中，指定 SIP 安全级别。默认级别为“高”****，建议使用此级别。

6.  在“编辑设备配置”**** 中的“电话锁定”**** 下，选中或清除“强制设备锁定”**** 复选框（默认为选中）并指定最小 PIN 长度（默认为 6 个字符）和超时期限（默认为 10 分钟）。建议使用这些默认值或增加 PIN 长度和/或减小超时期限。
    
    <div>
    

    > [!NOTE]  
    > 有关详细信息，请参阅 <A href="lync-server-2013-enforce-phone-locking.md">在 Lync Server 2013 中强制执行电话锁定</A>。

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 为 Lync Phone Edition 电话配置安全设置

可以使用 Lync Server 命令行管理程序和 **CsUCPhoneConfiguration** cmdlet 来管理安全设置。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-modify-the-sip-security-mode"></a>修改 SIP 安全模式

  - 此命令将 UC 电话设置全局集合的 SIPSecurityMode 设置为“中”。还可以将 SIP 安全性设置为“低”或“高”（默认值）。
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>修改最小 PIN 长度

  - 在此示例中，会将所有 UC 电话设置修改为需要 7 位最小 PIN 长度。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

有关详细信息，请参阅 [CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[管理 Lync Server 2013 身份验证](lync-server-2013-managing-lync-server-authentication.md)  


[在 Lync Server 2013 中管理设备、电话和客户端应用程序](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


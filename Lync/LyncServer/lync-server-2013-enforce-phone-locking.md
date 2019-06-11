---
title: 'Lync Server 2013: 强制执行电话锁定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4961aabf2edce33f1e5975497844704ac0feae03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a>在 Lync Server 2013 中强制执行电话锁定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

出于安全考虑, 可以锁定 Lync 手机版设备。 如果强制使用电话锁定, 则运行 Lync Phone Edition 的设备将在你配置的时间段后锁定。 当电话锁定时, 用户可以进行呼叫, 但无法访问日历和联系人信息、语音邮件或呼叫日志或使用搜索。 若要解锁手机, 用户可输入 PIN 码。

若要强制执行电话锁定, 请使用 Lync Server 控制面板或 Lync Server PowerShell cmdlet 启用和配置它。 你可以全局或仅在配置它的网站内强制执行电话锁定。

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>配置和强制实施电话锁定

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  单击 "**客户端**", 然后单击 "**设备配置**"。

4.  在 "**设备配置**" 选项卡上的设备配置列表中, 双击要更改电话锁定设置的配置。

5.  在 "**编辑设备配置**" 对话框中, 验证 "**强制设备锁定**" 复选框是否已选中。

6.  在 "**最小 PIN 长度**" 中, 接受解锁 PIN 必须包含的最小数字位数或指定新值的默认值。 PIN 长度的范围是4到15位数字, 默认值是6。

7.  在 "**电话锁定超时**" 中, 接受电话锁定自身之前的最短时间长度的默认值, 或指定新值。 Timeout 的范围是0到60分钟, 默认值是10。 以 HH: MM: SS 格式输入值。

8.  单击“**提交**”。

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 强制执行电话锁定

可通过使用 CsUCPhoneConfiguration cmdlet 强制执行电话锁定。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-phone-locking"></a>启用电话锁定

  - 以下命令为 Redmond 网站启用电话锁定。 若要禁用电话锁定, 请将 EnforcePhoneLock 属性设置为 False ($False)。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>启用电话锁定和修改电话锁定超时

  - 此命令启用电话锁定, 同时将电话锁定超时设置为30分钟。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>在整个组织中启用电话锁定

  - 在此示例中, 在组织中使用的所有 UC 电话配置设置上启用了电话锁定。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

有关详细信息, 请参阅[CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet 的帮助主题。

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


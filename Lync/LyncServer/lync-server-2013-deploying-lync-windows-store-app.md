---
title: Lync Server 2013：部署 Lync Windows 应用商店应用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d27f7a2402fabbc28080ca5efc2532497c93c653
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>在 Lync Server 2013 中部署 Lync Windows 应用商店应用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-12-03_

在使 Lync Windows 应用商店应用程序可供用户使用之前，请确保您的部署满足[Lync Server 2013 的 Lync windows 应用商店应用要求](lync-server-2013-lync-windows-store-app-requirements.md)。 有关配置 Lync Server 2013 以支持 Lync Windows 应用商店应用的详细信息，请参阅 NextHop 博客文章： "Lync Server 自动发现和 Lync Windows 应用商店应用[https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966)"，网址为。 正确配置服务器环境后，可以通过搜索 "Lync" 引导用户从 Windows 应用商店下载 Lync 应用。

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>为 Lync Windows 应用商店应用启用多重身份验证

Lync Server 2013 的累积更新：六月2013为 Lync Windows 应用商店应用程序客户端添加对多重身份验证的支持。 除了用户名和密码之外，还可以要求其他身份验证方法（如智能卡或 Pin），以便在外部用户登录 Lync 会议时对其进行身份验证。 若要启用多重身份验证，请在 Lync Server 2013 中部署 Active Directory 联合身份验证服务（AD FS）联合服务器并启用被动身份验证。 配置 AD FS 后，尝试加入 Lync 会议的外部用户将显示一条 AD FS 多重身份验证网页，其中包含用户名和密码质询以及已配置的任何其他身份验证方法.

<div class=" ">


> [!IMPORTANT]  
> 如果您计划为 Lync Windows 应用商店应用程序配置针对多重身份验证的 AD FS，请务必考虑以下事项： 
> <UL>
> <LI>
> <P>Lync Server 2013 （包含适用于 Lync Server 2013 的累积更新：至少需要6月2013）。 Lync 2013 桌面客户端不需要 Lync Server 2013 的累积更新：6月2013，因此可能会出现被动身份验证，因为 Lync 2013 客户端能够进行身份验证。 但是，Lync Windows 应用商店应用程序客户端的身份验证过程将无法完成，并且不会显示任何通知或错误消息。</P>
> <LI>
> <P>必须配置服务器，以便被动身份验证是提供的唯一身份验证类型。</P>
> <LI>
> <P>如果使用硬件负载平衡器，请在负载平衡器上启用 cookie 持久性，以便来自 Lync Windows 应用商店应用程序客户端的所有请求均由同一前端服务器处理。</P>
> <LI>
> <P>当您在 Lync Server 和 AD FS 服务器之间建立信赖方信任时，请分配足够长的令牌有效期，以跨越 Lync 会议的最大长度。 通常情况下，令牌寿命为240分钟就足够了。</P></LI></UL>



</div>

**配置多重身份验证**

1.  安装 AD FS 联合服务器角色。 有关详细信息，请参阅《 Active Directory 联合身份验证服务<https://go.microsoft.com/fwlink/p/?linkid=267511>2.0 部署指南》。

2.  为 AD FS 创建证书。 有关详细信息，请参阅的规划和部署 AD FS 的 "联合服务器证书" 一节，其中的单一登录主题可供使用[https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376)。

3.  从 Windows PowerShell 命令行界面中，运行以下命令：
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  通过运行以下命令建立合作关系：
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  设置以下信赖方规则：
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>可阻止登录的已知问题

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>在运行 Lync Windows 应用商店应用的设备上未准确设置时间和日期

设备上的 "时间" 设置必须与服务器上的 "时间" 设置同步。 对于 Microsoft Surface 等设备以及其他运行 Windows RT 且未加入域的设备来说，这一点尤其重要。 若要从时间服务器自动设置这些设备上的时间，请从设备上提升的命令提示符处运行以下命令：
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Lync Windows 应用商店应用无法访问 Lync 服务器或服务

Lync Windows 应用商店应用可能无法通过网络适配器（如 4G LTE USB 调制解调器）访问 Lync server 或服务，而不能在 Windows 8 中注册为物理设备。 即使桌面应用程序和浏览器能够访问其他服务器和网站，Lync Windows 应用商店应用也可能会遇到此问题。

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Lync Windows 应用商店应用无法使用 Lync Server 2010 和 Office 通信服务器 2007 R2 Edge 服务器进行登录

如果您的拓扑由 Lync Server 2010 与 Office 通信服务器 2007 R2 Edge 服务器组成，则需要运行 Lync Server 2010 累积更新中提供的更新版本的拓扑生成器：七月2013。 早期版本的拓扑生成器不会创建 Office 通信服务器2007边缘服务器所需的映射，因此 Lync Windows 应用商店应用客户端无法登录。 以下步骤是必需的：

1.  在 Lync Server 2010 池和 Lync Server 2010 控制器上安装 Lync Server 2010 的累积更新：7月2013日。

2.  通过执行以下操作，更新 Lync 自动发现配置，以指示外部 SIP 入口点为边缘服务器地址：
    
    1.  打开 Lync Server 命令行管理程序。
    
    2.  运行以下命令：
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>由于证书名称验证失败，Lync Windows 应用商店应用无法登录

未运行最新版本的 Lync Windows 应用商店应用程序的 Office 365 用户可能会发生登录问题。 此问题通常发生在使用多个域（例如，SIP URI 为**userA@domainZ.com** ，但边缘服务器为**sip.domainX.com**）时。 若要解决此问题，用户应安装最新版本的 Lync Windows 应用商店应用，这也需要 Windows 8.1。

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>使用 Lync Windows 应用商店应用日志解决问题

您可以使用设备上生成的日志来解决问题。 日志存储在以下文件夹中：

% LocalAppData%\\程序包\\LyncMX\_8wekyb3d8bbwe\\LocalState\\跟踪

在从用户获取日志之前，请确保已启用日志记录，然后要求用户保存日志，以便存储在内存中的所有信息也保存在硬盘上的文件中。

**启用日志记录**

1.  在设备上打开 Lync Windows 应用商店应用。

2.  从屏幕右侧轻扫。 如果使用的是鼠标，请指向屏幕右上角，然后将鼠标指针在屏幕上向下移动。

3.  选择 "**设置**"，选择 "**选项**"，然后将 "**诊断日志**" 设置为 **"打开"**。

4.  如果以前的**诊断日志**已关闭，则必须重新启动 Lync。 若要重新启动 Lync，请执行以下操作之一：
    
      - 重新启动设备。
    
      - 结束 Lync 任务并再次启动应用程序。 若要结束任务，请打开 Windows 任务管理器，选择 " **Lync**"，然后点击 "**结束任务**"。 如果未列出 Lync，请点击 "**更多详细信息**"，并在 "**后台流程**" 下查找 Lync。

**保存日志**

1.  在设备上打开 Lync Windows 应用商店应用。

2.  尝试登录。

3.  从屏幕右侧轻扫。 如果使用的是鼠标，请指向屏幕右上角，然后将鼠标指针在屏幕上向下移动。

4.  选择 "**设置**"，选择 "**关于**"，然后选择 "**保存日志**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 部署 Lync Windows 应用商店应用
TOCTitle: 部署 Lync Windows 应用商店应用
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ822971(v=OCS.15)
ms:contentKeyID: 52061086
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 部署 Lync Windows 应用商店应用

 

_**上一次修改主题：** 2016-12-08_

在使 Lync Windows 应用商店应用 供用户使用之前，请确保您的部署满足 [Lync Windows Store 应用程序要求](lync-server-2013-lync-windows-store-app-requirements.md)。有关配置 Lync Server 2013 以支持 Lync Windows 应用商店应用的详细信息，请参阅 NextHop 博客文章“Lync Server 自动发现和 Lync Windows 应用商店应用”，网站为 [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)。在您的服务器环境正确配置之后，您可以指导用户通过搜索“Lync”从 Windows 应用商店下载 Lync 应用。

## 针对 Lync Windows 应用商店应用 启用多重身份验证

2013 年 6 月 Lync Server 2013 累积更新 针对 Lync Windows 应用商店应用客户端增加了多重身份验证支持。当外部用户登录到 Lync 会议时，除了用户名和密码以外，您可能需要其他身份验证方法（如智能卡或 PIN）来对他们进行身份验证。要启用多重身份验证，请部署 Active Directory 联合身份验证服务 (AD FS) 联盟服务器并在 Lync Server 2013 中启用被动身份验证。在配置 AD FS 之后，会向尝试加入 Lync 会议的外部用户呈现 AD FS 多重身份验证网页，该网页包含用户名和密码质询，以及您已配置的任何其他身份验证方法。

> [!IMPORTANT]  
> 如果您计划为 Lync Windows 应用商店应用配置 AD FS 以进行多重身份验证，以下是一些重要注意事项：
> <ul>
> <li><p>至少需要具有 2013 年 6 月 Lync Server 2013 累积更新 的 Lync Server 2013。 Lync 2013 桌面客户端不需要 2013 年 6 月 Lync Server 2013 累积更新，因此它可能会显示被动身份验证正在工作，因为 Lync 2013 客户端能够进行身份验证。但是，Lync Windows 应用商店应用客户端的身份验证过程无法完成，不会显示任何通知或错误消息。</p></li>
> <li><p>服务器必须进行配置，以便被动身份验证是提供的唯一身份验证类型。</p></li>
> <li><p>如果您使用硬件负载平衡器，请启用负载平衡器上的 Cookie 持久性，以便来自 Lync Windows 应用商店应用 客户端的所有请求均由同一前端服务器进行处理。</p></li>
> <li><p>在 Lync Server 与 AD FS 服务器之间建立信赖方信任时，请分配足够长的令牌使用时间，以跨越 Lync 会议的最大长度。通常，240 分钟的令牌使用时间就足够了。</p></li>
> </ul>


**配置多重身份验证**

1.  安装 AD FS 联盟服务器角色。有关详细信息，请参阅《Active Directory 联合身份验证服务 2.0 部署指南》，网址为 [http://go.microsoft.com/fwlink/?linkid=267511\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=267511%26clcid=0x804)。

2.  为 AD FS 创建证书。有关详细信息，请参阅“规划和部署 AD FS 以用于单一登录”主题（网址是 [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)）中的“联合服务器证书”一节。

3.  从 Windows PowerShell 命令行界面，运行以下命令：
    
        add-pssnapin Microsoft.Adfs.powershell

4.  通过运行以下命令来建立合作关系：
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  设置以下信赖方规则：
    
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'

       &nbsp;
    
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules

       &nbsp;
    
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml

## 可能会阻止登录的已知问题

## 运行 Lync Windows 应用商店应用的设备上未准确设置时间和日期

设备上的时间设置必须与服务器上的时间设置保持同步。这对于 Microsoft Surface 等设备和其他运行 Windows RT 的未加入域的设备尤其重要。要从时间服务器自动设置这些设备上的时间，请在设备上从提升的命令提示符处运行以下命令：

    w32tm /resync

## Lync Windows 应用商店应用无法访问 Lync 服务器或服务

Lync Windows 应用商店应用可能无法通过未在 Windows 8 中注册为物理设备的网络适配器（如 4G LTE USB 调制解调器）访问 Lync 服务器或服务。即使桌面应用程序和浏览器能够访问其他服务器和网站，Lync Windows 应用商店应用也可能存在此问题。

## Lync Windows 应用商店应用无法使用 Lync Server 2010 和 Office Communications Server 2007 R2 边缘服务器登录

如果您的拓扑由 Lync Server 2010 和 Office Communications Server 2007 R2 边缘服务器组成，您需要运行 Lync Server 2010 2013 年 7 月的累积更新中可用的拓扑生成器的更新版本。拓扑生成器的早期版本不会创建与 Office Communications Server 2007 边缘服务器的必需映射，因此 Lync Windows 应用商店应用客户端无法登录。需要执行以下步骤：

1.  在 Lync Server 2010 池和 Lync Server 2010 控制器上安装 Lync Server 2010 2013 年 7 月的累积更新。

2.  通过执行下列操作更新 Lync 自动发现配置，以指明外部 SIP 入口点是边缘服务器地址：
    
    1.  打开 Lync Server 命令行管理程序。
    
    2.  运行以下命令：
        
            Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443

## 由于证书名称验证失败，Lync Windows 应用商店应用无法登录

对于未运行 Lync Windows 应用商店应用 的最新版本的 Office 365 用户，可能会发生登录问题。使用多个域时通常会发生此问题（例如，当 SIP URI 是 **userA@domainZ.com**，但是边缘服务器是 **sip.domainX.com** 时）。要解决该问题，用户应安装 Lync Windows 应用商店应用 的最新版本，它也需要 Windows 8.1。

## 使用 Lync Windows 应用商店应用日志解决问题

您可以使用设备上生成的日志解决问题。日志存储在下面的文件夹中：

%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing

在从用户那里获得日志之前，请确保打开日志记录，然后让用户保存日志，以便存储在内存中的所有信息也会保存到硬盘驱动器上的文件中。

**打开日志记录**

1.  打开设备上的 Lync Windows 应用商店应用。

2.  从屏幕右侧滑动。如果您使用的是鼠标，请指向屏幕右上角，然后沿着屏幕向下移动鼠标指针。

3.  选择“设置”，选择“选项”，然后将“诊断日志”设置为“打开”。

4.  如果“诊断日志”以前已关闭，您必须重新启动 Lync。要重新启动 Lync，请执行以下操作之一：
    
      - 重新启动设备。
    
      - 结束 Lync 任务，然后再次启动应用。要结束任务，请打开 Windows 任务管理器，选择“Lync”，然后点击“结束任务”。如果 Lync 未列出，请点击“更多详细信息”并在“后台进程”下方查找 Lync。

**保存日志**

1.  打开设备上的 Lync Windows 应用商店应用。

2.  尝试登录。

3.  从屏幕右侧滑动。如果您使用的是鼠标，请指向屏幕右上角，然后沿着屏幕向下移动鼠标指针。

4.  选择“设置”，选择“关于”，然后选择“保存日志”。


---
title: 配置会议邀请
TOCTitle: 配置会议邀请
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398638(v=OCS.15)
ms:contentKeyID: 49313400
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置会议邀请

 

_**上一次修改主题：** 2013-07-16_

您可以自定义 Lync 2013 联机会议外接程序发送的会议邀请，方法是将以下可选项包含在会议邀请的正文中：

  - **您的组织的徽标** 使用徽标 URL 选项将您的组织的徽标添加到会议邀请。如果会议邀请要发送到您的组织以外的人员，则应将图像放在公开发布的 URL 上。支持的图像格式为 GIF 和 JPG。尽管 Lync Server 2013 存储 URL 时对图像没有大小限制，但为了获得最佳结果，图像的最大大小应为 30 像素高 x 188 像素宽。

  - **自定义帮助或支持链接** 为您组织的帮助或支持团队网站添加 URL。如果会议邀请要发送到您的组织以外的人员，则应公开发布该 URL。最大 URL 长度为 1 KB。

  - **法律免责声明文本** 为将显示在所有会议邀请中的法律文本或免责声明添加 URL。如果会议邀请要发送到您的组织以外的人员，则应公开发布该 URL。最大 URL 长度为 1 KB。

  - **自定义页脚文本** 添加将在邀请中呈现为自定义页脚的文本。可添加的文本的最大长度为 2 KB。

您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序配置这些选项。


**使用 Lync Server 控制面板自定义会议邀请**

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“会议配置”。

4.  在“会议配置”页上，单击“新建”，然后执行下列操作之一：
    
      - 要创建站点级别的策略，请单击“站点配置”。在“选择站点”搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击“确定”。
    
      - 要创建池级别的策略，请单击“池配置”。在“选择服务”搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击“确定”。

5.  执行下列任一操作：
    
      - 在“徽标 URL”字段中，键入组织的徽标图像的 URL。
    
      - 在“帮助 URL”字段中，键入组织的帮助或支持站点的 URL。
    
      - 在“法律文本”字段中，键入要包含在会议邀请中的法律文本或免责声明的 URL。
    
      - 在“自定义页脚文本”字段中，键入页脚文本，最大为 2 KB。

**使用 Lync Server 命令行管理程序自定义会议邀请**

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 **New-CsMeetingConfiguration** 或 **Set-CsMeetingConfiguration** cmdlet 以创建或配置会议邀请选项。例如，运行：
    
        New-CsMeetingConfiguration -Identity site:Redmond -EnableInviteCustomization $True -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."


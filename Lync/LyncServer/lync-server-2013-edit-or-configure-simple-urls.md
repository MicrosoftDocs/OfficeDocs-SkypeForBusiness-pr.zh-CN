---
title: Lync Server 2013：编辑或配置简单 URL
TOCTitle: 编辑或配置简单 URL
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398063(v=OCS.15)
ms:contentKeyID: 49311798
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中编辑或配置简单 URL

 

_**上一次修改主题：** 2014-02-04_

此过程不需要本地管理员或特许域组中的成员身份。您应该以标准用户身份登录到计算机。

Lync Server 2013 使用简单 URL 将内部和外部呼叫定向到前端服务器或控制器（如果已经部署）上的服务。有关简单 URL 的更多信息，请参阅规划文档中的[在 Lync Server 2013 中规划简单 URL](lync-server-2013-planning-for-simple-urls.md)。您可以从许多选项中选择简单 URL 的格式。有关这些选项的详细信息，请参阅规划文档中的[Lync Server 2013 中简单 URL 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)。

默认情况下，将按以下格式配置简单 URL（以电话拨入式简单 URL 为例）：https://dialin.\<SIP domain\>

## 配置简单 URL

1.  在拓扑生成器中，右键单击“Lync Server”节点，然后单击“编辑属性”。

2.  在“简单 URL”窗格中，选择要编辑的“电话访问 URL：”（拨入）或“会议 URL：”（会议），然后单击“编辑 URL”。

3.  将 URL 更新为所需的值，然后单击“确定”保存已编辑的 URL。此处显示的示例已将电话拨入式 URL 修改为 https://pool01.contoso.net/dialin。

4.  如有必要，使用相同的步骤编辑会议 URL。

## 定义可选的管理简单 URL

1.  在拓扑生成器中，右键单击“Lync Server”节点，然后单击“编辑属性”。

2.  在“管理访问 URL”框中，输入要用于对 Lync Server 2013 控制面板进行管理访问的简单 URL，然后单击“确定”。
    
    > [!TIP]
    > 建议尽可能使用最简单的 URL 作为管理 URL。最简单的选项是 <strong>https://admin.</strong><em>&lt;domain&gt;</em>。
    
    > [!IMPORTANT]
    > 如果在初始部署后更改简单 URL，您必须注意哪些更改会影响简单 URL 的域名系统 (DNS) 记录和证书。如果该更改影响简单 URL 的基础，则还必须更改 DNS 记录和证书。例如，将 https://lync.contoso.com/Meet 更改为 https://meet.contoso.com 时，会将基 URL 由 lync.contoso.com 更改为 meet.contoso.com，因此需要更改 DNS 记录和证书，以引用 meet.contoso.com。如果将简单 URL 由 https://lync.contoso.com/Meet 更改为 https://lync.contoso.com/Meetings，其中基 URL lync.contoso.com 保持不变，则无需更改 DNS 或证书。但是，每次更改简单 URL 名称时，都必须在每台控制器和前端服务器上运行 <strong>Enable-CsComputer</strong> cmdlet，以注册该更改。


## 另请参阅

#### 概念

[在 Lync Server 2013 中规划简单 URL](lync-server-2013-planning-for-simple-urls.md)


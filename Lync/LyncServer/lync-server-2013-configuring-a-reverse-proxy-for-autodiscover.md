---
title: Lync Server 2013：为自动发现配置反向代理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c50704508c09d1f30a9fb8e31060e2a3b69885d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中为自动发现配置反向代理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-12-12_

使用自动发现的客户端的自动发现和支持需要修改现有的 web 发布规则或为反向代理创建新的 web 发布规则。 修改或创建新的发布规则并不依赖于更新或不更新反向代理证书上的主题备用名称列表的决定。

如果您决定对初始 Lync Server 2013 自动发现服务请求使用 HTTPS，并在反向代理证书上更新 "主题备用名称" 列表，则需要将更新的公共证书分配给位于 "安全套接字层（SSL）" 的安全套接字层（SSL）侦听器。您的反向代理。 对外部（公用）证书所需的更新将包含 lyncdiscover. 的主题备用名称（SAN）条目。\<域名称\>。 然后，您需要修改外部 web 服务的现有侦听器或为外部自动发现服务 URL 创建新的 web 发布规则，例如**lyncdiscover.contoso.com**。 如果您没有用于前端池和控制器池的外部 Lync Server 2013 Web 服务 URL 的 web 发布规则（如果部署了控制器），您还需要为此发布一个规则。

<div>


> [!NOTE]  
> 只要分配给侦听器的证书同时包含针对外部 Web 服务和自动发现服务的必要的使用者名称和使用者替代名称，反向代理发布规则和侦听器就可以为这两种服务提供服务。 有关 web 侦听器和发布规则的默认配置的详细信息，请参阅为<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 设置反向代理服务器</A>，了解更多详细信息。



</div>

如果您决定对初始自动发现服务请求使用 HTTP 以便无需更新反向代理的使用者替代名称，则需要为端口 80 创建或修改一条 Web 发布规则。

本节中的过程介绍如何使用 Microsoft Forefront Threat Management Gateway 2010 创建或修改一条 Web 发布规则以实现自动发现。

<div>


> [!NOTE]  
> 这些过程假定您已安装 Forefront Threat Management Gateway (TMG) 2010 Standard Edition。如果您使用另一个反向代理，则这些过程是类似的，只不过需要将其映射到第三方产品的文档。



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>为外部自动发现 URL 创建 Web 发布规则

1.  单击“开始”****，依次指向“程序”****、“Microsoft Forefront TMG”****，然后单击“Forefront TMG 管理”****。

2.  在左窗格中，展开“服务器名称”****，右键单击“防火墙策略”****，指向“新建”****，然后单击“网站发布规则”****。

3.  在“欢迎使用新建 Web 发布规则向导”**** 页上，为新的发布规则键入一个显示名称（例如，LyncDiscoveryURL）。

4.  在“选择规则操作”**** 页上，选择“允许”****。

5.  在“发布类型”**** 页上，选择“发布单个网站或负载平衡器”****。

6.  在“服务器连接安全性”**** 页上，选择“使用 SSL 连接到发布的 Web 服务器或服务器场”****。

7.  在 "**内部发布详细信息**" 页上的 "**内部站点名称**" 中，键入控制器池的完全限定域名（FQDN）（例如，lyncdir01）。 如果要为前端池上的外部 Web 服务 URL 创建规则，请键入前端池的 FQDN （例如，lyncpool01）。

8.  在 "**内部发布详细信息**" 页上的 "**路径（可选）**" 中，键入** / **作为要发布的文件夹的路径，然后选择 **"转发原始主机标头"**。

9.  在“公共名称细节”**** 页上，执行以下操作：
    
      - 在“接受请求”**** 下，选择“此域名”****。
    
      - 在 "**公用名称**" 中，键入**lyncdiscover.。**\<sipdomain\> （外部自动发现服务 URL）。 如果要为前端池上的外部 Web 服务 URL 创建规则，请在前端池上键入外部 Web 服务的 FQDN （例如，lyncwebextpool01.contoso.com）。
    
      - 在 "**路径**" ** /** 中，键入。

10. 在“选择 Web 侦听器”**** 页上的“Web 侦听器”**** 中，选择具有已更新的公共证书的现有 SSL 侦听器。

11. 在“身份验证委派”**** 页上，选择“无委派，但是客户端可以直接进行身份验证”****。

12. 在“用户集”**** 页上，选择“所有用户”****。

13. 在“正在完成新建 Web 发布规则向导”**** 页上，确认 Web 发布规则设置正确，然后单击“完成”****。

14. 在 Web 发布规则的 Forefront TMG 列表中，双击您刚添加的新规则以打开“属性”****。

15. 在“收件人”**** 选项卡上，执行以下操作：
    
      - 选择“转发原始主机头而不是实际主机头”****。
    
      - 选择“使请求显示为来自 Forefront TMG 计算机”****。

16. 在“桥接”**** 选项卡上，配置以下设置：
    
      - 选择“Web 服务器”****。
    
      - 选择“将请求重定向到 HTTP 端口”****，并键入 **8080** 作为端口号。
    
      - 选择“将请求重定向到 SSL 端口”****，然后键入端口号 **4443**。

17. 单击“确定”****。

18. 在详细信息窗格中，单击“应用”****，以保存所做的更改并更新配置。

19. 单击“测试规则”**** 以验证是否正确设置了新规则。

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>修改现有 Web 发布规则以添加外部自动发现 SAN 和 URL

1.  单击“开始”****，依次指向“程序”****、“Microsoft Forefront TMG”****，然后单击“Forefront TMG 管理”****。
    
    <div>
    

    > [!IMPORTANT]  
    > 您将对您拥有的每个发布规则和侦听器重复进行此修改。 通常情况下，这将是前端池的一个规则和侦听器，另一个是可选控制器或控制器池（如果已部署）。

    
    </div>

2.  在左窗格中展开“服务器名称”****，右键单击“防火墙策略”****，再单击适用的规则。在“任务”**** 选项卡上，单击“编辑所选规则”****。

3.  在“公共名称”**** 选项卡上的“此规则应用于”**** 中，选择“以下网站的请求”****。

4.  单击“添加”****，键入新的 Autodiscover 网站的名称（例如，“lyncdiscover.contoso.com”），然后单击“确定”****。

5.  在“侦听器”**** 选项卡上，单击“选择证书”**** 并指定具有添加的自动发现 SAN 条目的新证书。关闭侦听器和 Web 发布属性。

6.  在细节窗格中，单击“应用”****，以保存所做的更改并更新配置。

7.  单击“测试规则”**** 以验证是否正确设置了新规则。

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>为端口 80 创建 Web 发布规则

1.  单击“开始”****，依次指向“程序”****、“Microsoft Forefront TMG”****，然后单击“Forefront TMG 管理”****。

2.  在左窗格中，展开“服务器名称”****，右键单击“防火墙策略”****，指向“新建”****，然后单击“网站发布规则”****。

3.  在“欢迎使用新建 Web 发布规则向导”**** 页上，为新的发布规则键入一个显示名称（例如，Lync Autodiscover (HTTP)）。

4.  在“选择规则操作”**** 页上，选择“允许”****。

5.  在“发布类型”**** 页上，选择“发布单个网站或负载平衡器”****。

6.  在“服务器连接安全性”**** 页上，选择“使用不安全的连接连接发布的 Web 服务器或服务器场”****。

7.  在 "**内部发布详细信息**" 页上的 "**内部站点名称**" 中，键入您的前端池的内部 Web 服务 FQDN （例如，lyncpool01）。

8.  在 "**内部发布详细信息**" 页上的 "**路径（可选）**" 中，键入** / **作为要发布的文件夹的路径，然后选择 "**转发原始主机标头"，而不是 "内部站点名称" 字段中指定的主机头**。

9.  在“公共名称细节”**** 页上，执行以下操作：
    
      - 在“接受请求”**** 下，选择“此域名”****。
    
      - 在 "**公用名称**" 中，键入**lyncdiscover.。**\<sipdomain\> （外部自动发现服务 URL）。
    
      - 在 "**路径**" ** /** 中，键入。

10. 在“选择 Web 侦听器”**** 页上的“Web 侦听器”**** 中，选择 Web 侦听器或使用新建 Web 侦听器定义向导新建一个 Web 侦听器。

11. 在“身份验证委派”**** 页上，选择“无委派，并且客户端无法直接进行身份验证”****。

12. 在“用户集”**** 页上，选择“所有用户”****。

13. 在“正在完成新建 Web 发布规则向导”**** 页上，确认 Web 发布规则设置正确，然后单击“完成”****。

14. 在 Web 发布规则的 Forefront TMG 列表中，双击您刚添加的新规则以打开“属性”****。

15. 在“桥接”**** 选项卡上，配置以下设置：
    
      - 选择“Web 服务器”****。
    
      - 选择“将请求重定向到 HTTP 端口”****，并键入 **8080** 作为端口号。
    
      - 确认未选中“将请求重定向到 SSL 端口”****。

16. 单击“确定”****。

17. 在详细信息窗格中，单击“应用”****，以保存所做的更改并更新配置。

18. 单击“测试规则”**** 以验证是否正确设置了新规则。

19. 确认未针对任何其他 Web 发布规则定义外部自动发现服务 URL。

</div>

<div>

## <a name="see-also"></a>另请参阅


[为 Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


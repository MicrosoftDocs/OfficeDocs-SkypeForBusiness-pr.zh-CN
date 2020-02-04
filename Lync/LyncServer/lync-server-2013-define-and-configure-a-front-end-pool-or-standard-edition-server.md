---
title: 定义和配置前端池或 Standard Edition 服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddc430370c59e279e0e36aa662da0f33973e0d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-08_

此过程不需要本地管理员或特权域组的成员身份。 您应以标准用户身份登录到计算机。

如果要部署企业服务器，池中的最少前端服务器数必须始终运行。 下表总结了这些要求。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中的前端服务器总数</th>
<th>使池发挥作用所必须运行的服务器的数量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>ppls-2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> 对于 Lync Server 2013，无论何时在池中添加或删除前端服务器，都必须重新启动服务。 删除和添加服务器应作为单独的操作完成。 例如，如果你打算添加两台前端服务器并删除两台前端服务器，请使用以下过程： 
> <OL>
> <LI>
> <P>删除这两个前端服务器。</P>
> <LI>
> <P>发布并重新激活拓扑。</P>
> <LI>
> <P>重新启动服务</P>
> <LI>
> <P>添加两个前端服务器。</P>
> <LI>
> <P>发布并重新激活拓扑。</P>
> <LI>
> <P>重新启动服务。</P></LI></OL>



</div>

定义拓扑后，请使用以下过程定义网站的前端池。 有关定义拓扑的详细信息，请参阅[在 Lync Server 2013 的拓扑生成器中定义和配置拓扑](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。

<div>

## <a name="to-define-a-front-end-pool"></a>定义前端池

1.  在 "定义新的前端池" 向导的 "**定义新的前端池**" 页面上，单击 "**下一步**"。

2.  在 "**定义前端池 FQDN** " 页面上，输入要创建的池的完全限定的域名（FQDN），单击 "**企业版前端池**"，然后单击 "**下一步**"。

3.  在 "**在此池中定义计算机**" 页面上，输入池中第一个前端服务器的计算机 FQDN，然后单击 "**添加**"。 对要添加到池中的任何其他计算机（最多12个）重复此步骤，然后单击 "**下一步**"。

4.  在 "**选择功能**" 页面上，选中您希望在此前端池上的功能所对应的复选框。 例如，如果您仅部署即时消息（IM）和状态功能，则可以选择 "**会议**" 复选框以允许多方 IM，但不会选择 "**拨入（PSTN）会议**"、"**企业语音**" 或 "**呼叫许可控制**" 复选框，因为它们代表语音、视频和协作会议功能。
    
      - **会议**   此选择支持一组丰富的功能，包括：
        
          - Im 会话中有两个以上双方的 IM。
        
          - 会议，包括文档协作、应用程序共享和桌面共享。
        
          - A/V 会议，使用户可以在不需要外部服务（如 Live Meeting 服务或第三方音频桥）的情况下进行实时音频/视频（A/V）会议。
    
      - **拨入（PSTN）会议**   允许用户通过使用公共交换电话网络（PSTN）电话（无需音频会议提供商）加入 Lync Server 2013 会议的音频部分。
    
      - **企业语音**   企业语音是 Lync Server 2013 中的 "通过 IP 进行语音通话" （VoIP）解决方案，允许用户拨打和接听电话。 如果您计划将 Lync Server 2013 用于语音呼叫、语音邮件和其他使用硬件设备或软件客户端的功能，则可以部署此功能。
    
      - **呼叫许可控制（CAC）**   CAC 根据可用的网络带宽确定是否允许建立实时通信会话（如语音或视频通话）。 如果你仅部署了 IM 和状态，则不需要 CAC，因为这两个功能都不会使用 CAC。
    
      - **存档**   存档提供了一种通过 Lync Server 2013 存档 IM 内容、会议（会议）内容或这两者的方式。
    
      - **通过监视**   监视服务器，你可以收集用于描述你的网络和终结点上的媒体质量的数值数据、与 VoIP 呼叫、即时消息、A/V 对话、会议、应用程序共享和文件传输相关的使用信息，以及呼叫错误和故障排除信息。
    
    <div>
    

    > [!NOTE]
    > 如果你想要在部署中启用 CAC，则需要在每个中心站点的恰好一个池中启用 CAC。 如果你要部署语音功能或 A/V 会议，则建议使用 CAC。

    
    </div>
    
    下表显示了可用功能（top）和向用户提供的函数（左图）。 表格中的选择是为您的组织启用这些功能应选择的内容。
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>网络会议</th>
    <th>电话拨入式会议</th>
    <th>企业语音</th>
    <th>呼叫允许控制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>即时消息和状态</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>网络会议</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>A/V 会议</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>企业语音</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  在 "**选择 collocated 服务器角色**" 页面上，你可以在前端服务器上 Collocate 中介服务器或将其作为独立服务器进行部署。
    
    你可以 collocate 前端池中的中介服务器。
    
      - 如果打算在企业版前端池上 collocate 中介服务器，请确保选中该复选框。 将在池服务器上部署服务器角色。
    
      - 如果打算将中介服务器部署为独立服务器，请清除相应的复选框。 在完全部署前端服务器之后，你将在单独的部署步骤中部署中介服务器。
    
    <div>
    

    > [!NOTE]
    > 如果可能，我们建议您 collocate 中介服务器。 有关 collocated 或独立中介服务器支持的详细信息，请参阅规划文档中<A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013 中的中介服务器组件和拓扑</A>。

    
    </div>

6.  "**关联服务器角色与此前端池**" 页面允许你定义服务器角色并将其与前端池相关联。 以下角色可用：
    
    **启用边缘池**   定义和关联单个边缘服务器或边缘服务器池。 边缘服务器为组织内的用户和组织外的用户（包括联盟用户）进行通信和协作提供方便。
    
    你可以使用两种可能的方案来部署和关联服务器角色：
    
    对于方案一，为新的安装定义新的拓扑。 你可以采用以下两种方式之一进行安装：
    
      - 将复选框留空，然后继续定义拓扑。 在发布、配置和测试前端和后端服务器角色之后，您可以再次运行拓扑生成器以将角色服务器添加到拓扑中。 此策略将使你能够测试运行 SQL Server 的前端池和服务器，而不会增加其他角色的复杂性。 完成初始测试后，可以再次运行拓扑生成器来选择需要部署的角色。
    
      - 选择需要安装的角色，然后设置硬件以适应所选择的角色。
    
    对于第二种方案，你已有一个现有部署，并且你的基础结构已准备好用于新角色，或者你需要将现有角色与新的前端服务器相关联：
    
      - 在这种情况下，你将选择要部署的角色或与新的前端服务器关联的角色。 无论在哪种情况下，都需要定义角色，设置任何所需硬件，然后继续安装。

7.  在 "**定义 SQL 应用商店**" 页面上，执行下列操作之一：
    
      - 若要使用已在拓扑中定义的现有 SQL Server 存储，请选择“**SQL 存储**”中的一个实例。
    
      - 若要定义新的 SQL Server 实例以存储池信息，请单击 "**新建**"，然后在 "**定义新的 sql 存储**" 对话框中指定**SQL Server FQDN**。
    
      - 要指定 SQL Server 实例的名称，请选择“**命名实例**”，然后指定实例的名称。
    
      - 要使用默认实例，请单击“**默认实例**”。
    
      - 若要使用 SQL 镜像，请选择 "**启用 sql 镜像**"，然后选择现有实例或创建新实例。

8.  在 "**定义文件共享**" 页面上，执行下列操作之一：
    
      - 要使用已经在拓扑中定义的文件共享，请选择“**使用先前定义的文件共享**”。
    
      - 要定义新文件共享，请选择“**定义新的文件共享**”，在“**文件服务器 FQDN**”框中，输入要放置文件共享的现有文件服务器的 FQDN，然后在“**文件共享**”框中输入文件共享的名称。
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server 2013 的文件共享不能位于前端服务器上。 请注意，在此示例中，文件共享位于基于 SQL Server 的后端服务器上。 这可能不是组织要求的最佳位置，文件服务器可能是更好的选择。 你可以在未创建文件共享的情况下定义文件共享。 你需要首先在定义的位置创建文件共享，然后才能发布拓扑。

    
    </div>

9.  在 "**指定 Web 服务 URL** " 页面上，执行下列一项或两项操作：
    
    <div>
    

    > [!IMPORTANT]
    > 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 是https://pool01.contoso.net，则基 URL 为 pool01.contoso.net。

    
    </div>
    
    <div>
    

    > [!WARNING]
    > 如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。 例如，如果你将前端服务器的外部 Web 服务 FQDN 定义为<STRONG>pool01.contoso.com</STRONG>，则不能将<STRONG>Pool01.contoso.com</STRONG>用于其他前端池或前端服务器。

    
    </div>
    
    1.  如果你要配置 DNS 负载平衡，请选中 "**替代内部 Web 服务池 FQDN** " 复选框，然后输入内部基础 url 中的内部基本 url （必须不同于池 FQDN，例如，内部-\<你的基本\>url） **。**
        
        <div>
        

        > [!WARNING]
        > 如果你决定使用自定义的 FQDN 替代内部 web 服务，则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。 定义 URL 或完全限定的域名时<STRONG>仅使用标准字符</STRONG>（包括 A–Z、a–z、0–9 和连字符）。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共 CA 通常不支持在 URL 或 FQDN 中使用非标准字符（即，当必须向证书中的使用者名称或使用者替代名称分配 URL 或 FQDN）。

        
        </div>
    
    2.  （可选）在**外部基 url**中输入外部基 url。 你将输入外部基 URL，以将其与你的内部域命名区区分开。 例如，你的内部域是 contoso.net，但你的外部域名是 contoso.com。 你可以使用 contoso.com 域名定义 URL。 如果是反向代理，这也很重要。 外部基 URL 域名应该与反向代理的 FQDN 域名相同。 即时消息和状态确实需要 HTTP 访问前端池。
    
    <div>
    

    > [!NOTE]
    > 若要使用 DNS 负载平衡，必须创建相应的 DNS 记录。 有关详细信息，请参阅<A href="lync-server-2013-configure-dns-for-load-balancing.md">在 Lync Server 2013 中配置用于负载平衡的 DNS</A>。

    
    </div>

10. 如果在 "**选择功能**" 页面上选择了 "**会议**"，请在 "**选择 office web apps 服务器**" 页面上选择 "**将池与 Office web Apps 关联**"，然后单击 "**新建**" （或从下拉列表中选择现有的 Office Web Apps 服务器）。

11. 在“**定义新的 Office Web Apps 服务器**”对话框的“**Office Web Apps 服务器 FQDN**”框中，键入你的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，你的 Office Web Apps 服务器搜索 URL 应自动输入到“**Office Web Apps 服务器搜索 URL**”框中。
    
    如果 Office Web Apps 服务器在本地安装，并且在与 Lync Server 2013 相同的网络区域中安装，则不应选择 " **Office Web Apps 服务器" 部署在外部网络（即周边/Internet）中**。
    
    如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器**”。
    
    <div>
    

    > [!NOTE]
    > 有关详细信息，请参阅<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">配置与 Office Web Apps server 和 Lync server 2013 的集成</A>。

    
    </div>

12. 在 "**定义存档 SQL 存储"** 页面上，选择一个现有实例或 SQL Server，或定义一个新实例以存储与存档数据相关联的数据。

13. 在 "**定义监视 SQL 存储**" 页面上，选择一个现有实例或 SQL Server，或定义一个新实例以存储与监视数据相关联的数据。

14. 单击" **下一步**"。 如果在 "**关联服务器角色与此前端池**" 页面中定义了其他角色服务器，将打开 "单独的角色配置向导" 页面，让你配置服务器角色。 有关详细信息，请参阅以下内容：
    
    [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)

15. 如果未选择要配置和部署的其他服务器角色，或者完成了其他角色服务器的配置，请单击 "**完成**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>


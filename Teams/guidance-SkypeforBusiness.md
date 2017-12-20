---
title: "与 Skype for Business 并行启用 Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "并行使用 Skype for Business 和 Microsoft Teams 指导"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7943765ec33e01f6237f74d5f8b171b267948961
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a>与 Skype for Business 并行启用 Microsoft Teams 
=============================================================

对于具有 Skype for Business Online 现有部署的组织，最近推出的 Microsoft Teams 提供了一个评估 Teams 作为唯一通信与协作解决方案的可能性的机会，提出了在两个解决方案之间进行抉择的挑战，以及它们如何在你的环境中共存。

如果 Teams 现在可以满足你的业务需求，你可以开始采用 Teams 以作为贵组织唯一的通信与协作解决方案。

默认情况下，在所有符合条件的租户中启用 Teams。 因此，你需要确定如何与 Skype for Business 并行管理 Teams，并继续满足用户期望。

通常，有两种主要的并行客户旅程。 它们是：

-   **选项 1：** 不受管理的并行客户旅程。

    IT 不主动控制并行体验，用户可以选择首选应用。

-   **选项 2：** 受管理的并行客户旅程。

    IT 控制并行体验，带领用户完成逐渐采用 Teams 的旅程，先在 Teams 中采用基于聊天的新型协作工作区（可以进行私人聊天），然后体验会议，最后体验通话。

![两种并行客户旅程示意图：受管理和不受管理。](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a>并行优势和考虑事项
----------------------------------------

在根据贵组织的情况确定正确前进方向时，每种旅程都有要评估的优势和考虑事项。 下表比较了受管理和不受管理的并行客户旅程。


<table>
<thead>
<tr class="header">
<th align="left">迁移途径</th>
<th align="left">不受管理的并行</th>
<th align="left">受管理的并行</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>组织情况</strong></td>
<td align="left"><ul>
<li>通常是没有专门的 IT 资源的小型组织</li>
<li>IT 允许用户自行选择适合其工作的工具</li>
<li>Skype for Business 主要用途是 IM/P 和会议</li>
</ul></td>
<td align="left"><ul><li>通常是大中型组织</li>
<li>IT 希望更加严格地控制新工具的部署</li>
<li>现在深入采用 Skype for Business</li>
<li>网络和基础结构的复杂性增加</li>
<li>多个位置</p>
<li>首选具有独特 UC 功能的单一应用</li></ul></td>
</tr>
<tr class="even">
<td align="left"><strong>优势</strong></td>
<td align="left"><ul>
<li>利用 Teams 中提供但 Skype for Business 中未提供的功能</li>
<li>在 Office 365 中具有增强的新式工作场所</li>
<li>提高了用户灵活性</li>
<li>一次性启用所有功能</li>
</ul></td>
<td align="left"><ul><li>利用 Teams 中提供但 Skype for Business 中未提供的功能</li>
<li>在 Office 365 中具有增强的新式工作场所</li>
<li>最大限度地降低用户工作效率影响</li>
<li>减少功能重叠</li>
<li>顺利为 UC 应用场景选择工具</li>
<li>使组织中的 IT 和业务部门能够根据需要启用功能</li>
<li>控制用户的改变步伐</li></ul></td>
</tr>
<tr class="odd">
<td align="left"><strong>考虑事项</strong></td>
<td align="left"><ul>
<li>存在多个具有相似、重叠功能的应用</li>
<li>增加了用户混乱的可能性，这可能会导致支持电话增加、IT 工作量增加、工作效率受影响</li>
<li>网络规划和监控必须考虑使用两种服务</li>
<li>所需的变更管理工作量增加且迫切：认知、培训和支持</li>
<li>用户可能会遇到应用之间存在的互操作性限制</li>
</ul></td>
<td align="left"><ul><li>IT 进行从许可到用户体验的细化控制，从而需要额外的规划和实施周期</li>
<li>需要用户培训和操作以在 Teams 中禁用选择功能</li>
<li>需要变更管理工作以在 Teams 中禁用选择功能</li>
<li>网络规划和监控必须考虑使用两种服务</li>
<li>用户可能会遇到应用之间存在的互操作性限制</li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a>不受管理的并行客户旅程
---------------------------------------


![不受管理的并行客户旅程示意图。](media/guidance_SkypeforBusiness_image4.png)

在不受管理的并行客户旅程中，Teams 作为协作解决方案采用（基于聊天的工作区、频道、应用、与其他 Office 365 工作负荷集成等），涉及桌面计算机（PC 或 Mac）和移动设备上的客户端软件和 Web 客户端。


默认情况下，Teams 还提供与 Skype for Business 重叠的功能，其中包括私人聊天和通话以及安排的会议。 这意味着 Teams 最终为组织提供完整的通信与协作，而同时 Skype for Business 提供类似的功能。

Teams 支持与 Skype for Business Online 用户的互操作性，用户将在启动 Teams 时可以选择其首选的聊天和通话应用。 如果一个用户选择 Teams 作为首选应用，而另一个用户未安装 Teams 或选择了 Skype for Business 作为首选的聊天和通话应用，他们可以通过属于 Teams 的互操作性功能继续相互聊天和通话。

Microsoft 一直在改进互操作性体验。 在初期，可能会出现互操作性体验未达到用户期望的一些情况。 由于用户仍可使用 Skype for Business，他们可以切换到 Skype for Business 来使用 Teams 当前无法提供的功能。

Teams 中安排的会议是另一项重叠功能，即用户可以安排 Teams 会议，也可以安排 Skype for Business 会议。 两者均有自己的优势，以后，当 Teams 会议体验满足业务需求或优于 Skype for Business 会议的功能时，我们希望用户顺理成章地切换到 Teams 会议。

在此不受管理的并行客户旅程中，应准备你的支持团队以处理用户遇到互操作性功能方面的问题时拨打的支持电话。 或者建议用户何时选择 Teams 会议而非 Skype for Business 会议，反之亦然。

如果用户更愿意接受不受管理的并行体验方式，并且组织公开允许用户选择适合其要求的最佳通信与协作工具，则此并行客户旅程可能适用于贵组织。

<a name="managed-side-by-side-customer-journey"></a>受管理的并行客户旅程
-------------------------------------

![受管理的并行客户旅程示意图。](media/guidance_SkypeforBusiness_image2.png)

受管理的并行客户旅程适用于希望对 Teams 的采用方式进行更多控制的组织。

-   此旅程的**第一步**是进行有限的 Teams 试点，范围限于新式协作需求（基于聊天的工作区、频道、应用、与其他 Office 365 工作负荷的集成等）。 此外，还启用 Teams 中的临时频道会议和私人聊天，以便试点用户可以评估 Teams 会议体验和私人聊天体验。 在此阶段禁用 Teams 中的安排的会议和专线通话功能。 要开始试点，请访问[在使用 Skype for Business 的同时试用 Teams](pilot-essentials.md)。
    
-   此旅程的**第二步**是扩展 Teams 的部署以用于在整个组织中通过私人聊天进行新式协作。 继续在 Teams 中禁用安排的会议和专线通话，以减少与 Skype for Business 功能的重叠。

    在此阶段，你可能需要考虑应将整个组织的首选聊天应用设置为 Teams 还是 Skype for Business。

    - 如果设置为 Teams，请让你的用户准备好处理在与组织内部和之间的其他用户通信时面临的初期互操作性挑战。
    
    - 如果设置为 Skype for Business，Teams 中的私人聊天将仍在 Teams 中进行，最终用户可以立即利用 Teams 中聊天功能的跨平台持久特性，他们将继续使用 Skype for Business 在组织内部和之间进行 Skype for Business 用户之间的私人聊天。


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>注意</p></td>
<td align="left"><br><br>当前，仅在客户端级别提供首选聊天应用设置。 要推动预期的组织范围的配置，需要用户培训和采用推行活动。</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

当组织确定 Teams 会议体验和功能满足其业务需求时，开始受管理的并行客户旅程的**第三步**。 在 Teams 中启用私人会议和频道会议后，将向用户显示用于安排 Teams 会议和 Skype for Business 会议的选项。 因此，预计以后如果 Teams 中不断增加创新功能，用户将顺理成章地切换到 Teams 会议。 为了成功引导从使用 Skype for Business 转向使用 Teams，应实施有力的变更管理计划，包括培训、支持和沟通（介绍 Teams 为用户提供的增值服务），以及有关如何开始使用 Teams 的清晰指导。 利用我们的[用户就绪](http://aka.ms/UserReadiness)资源来帮助设计你的认知推行活动。


受管理的并行客户旅程的**第四步**是先在 Teams 中启用通话。 为确保实现无缝的并行体验，Teams 互操作性功能将在此步骤中起重要作用。 理想情况下，为了强制使用 Teams 进行专线通话，Teams 设置为默认通话应用。 

随着时间的推移，可能整个组织会仅依赖 Teams 满足通信与协作需求并采取**第五步**。 要查看 Teams 中何时会添加新功能，请参阅 [Office 365 路线图](http://aka.ms/TeamsRoadmap)。 

<a name="managing-side-by-side-experience"></a>管理并行体验
--------------------------------

默认情况下，对于具有符合条件的 Office 365 订阅的组织，会启用 Microsoft Teams。 如果贵组织的情况适合不受管理的并行客户旅程，我们强烈建议你保持原样以便自然地采用 Microsoft Teams。

可以通过新式 Web 浏览器桌面客户端（不需要 IT 管理权限 - 对于安装，当前仅适用于 PC）和移动客户端访问 Teams。

默认情况下，启用 Teams 中的所有功能（私人聊天和通话、临时和安排的会议以及应用），从而允许用户尝试和使用适合其需求的功能。 Teams 中的首次运行体验会指引用户选择其首选聊天和通话应用（Microsoft Teams 或 Skype for Business）。

如果贵组织需要对新工具（例如 Teams）的发放进行更多的控制，可以在你的受管理的并行客户旅程中考虑以下选项：

-   试用和部署 Teams 用于协作。 请参阅[在使用 Skype for Business 的同时试用 Teams](pilot-essentials.md)

-   部署 Teams 用于会议

-   部署 Teams 用于通话

### <a name="teams-pilot-and-rollout-for-collaboration"></a>用于协作的 Teams 试点和部署

从其核心来看，Microsoft Teams 是通过增强 Office 365 组围绕持久聊天以及与 Office 365 集成构建而成的。

由于默认情况下对于具有符合条件的 Office 365 订阅的贵组织中的用户会启用 Teams，因此，如果要进行有限的 Teams 试点，就要对试点组外的所有用户禁用 Teams 许可证。

为了重点体现 Teams 版本作为协作与私人聊天解决方案，以及减少由于与 Skype for Business 的重叠功能导致的用户混乱，你可以在 Office 365 租户级别更改以下设置。 要更改这些 Office 365 设置，请参阅[在你的 Office 365 组织中设置 Microsoft Teams](Office-365-set-up.md)。

<table>
<thead>
<tr class="header">
<th align="left">部分</th>
<th align="left">设置</th>
<th align="left">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>通话和会议</strong></td>
<td align="left"><p>允许安排私人会议：<strong>关闭</strong></p><p>允许安排频道会议：<strong>关闭</strong></p><p>允许专线通话：<strong>关闭</strong></p></td>
<td align="left"><p>禁用此设置将防止用户安排私人会议</p><p>禁用此设置将防止用户安排频道会议</p><p>禁用此设置将防止用户进行私人通话（音频和视频）</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>注意</p></td>
<td align="left"><br><br>你必须对企业用户和来宾用户（如果来宾访问适用于贵组织）都禁用专线通话。</td>
</tr>
</thead>
<tbody>
</tbody>
</table>



借助此配置，可以通过提倡使用临时频道聚会、在新式协作体验中支持使用语音、视频和屏幕共享，向用户展现 Teams 中的会议工作方式。 最终用户还可以从 Teams 持久、跨平台、私人聊天功能受益。

针对协作与私人聊天的 Teams 试点成功后，可以向所有用户启用 Teams 许可证以在整个组织中全面部署。

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>注意</p></td>
<td align="left">在试点期间启用了私人聊天的第二阶段，与 Skype for Business 用户聊天的 Teams 用户将无法执行以下操作：<br>
- 从聊天会话启动视频通话<br>
- 传输文件 <br>
- 从聊天会话启动多方通话<br>
- 用户将无法启动桌面共享会话<br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a>部署 Teams 用于会议

随着用户逐渐习惯使用 Microsoft Teams 进行协作，可以考虑将安排的会议作为组织中下一个启用的功能。

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>注意</p></td>
<td align="left"><br><br>安排的会议的组织者必须在 Exchange Online 多租户（或 Exchange Online Dedicated vNext）中有自己的邮箱。</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

可以在租户级别配置以下设置以在 Teams 中启用安排的会议，这些设置仅适用于企业用户。

<table>
<thead>
<tr class="header">
<th align="left">部分</th>
<th align="left">设置</th>
<th align="left">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>通话和会议</strong></td>
<td align="left"><p>允许安排私人会议：<strong>开启</strong></p><p>允许安排频道会议：<strong>开启</strong></p></td>
<td align="left"><p>启用此设置将允许用户安排私人会议</p><p>启用此设置将允许用户安排频道会议</p></td>
</tr>
</tbody>
</table>


可以通过 Teams 桌面客户端或浏览器，或者使用适用于 Microsoft Teams 的会议外接程序通过 Microsoft Outlook，来组织安排的会议。 一旦在 Teams 中启用了安排的会议，我们建议你开始培训用户创建新的 Teams 会议或将现有 Skype for Business 会议更新为 Teams 会议。

### <a name="rollout-of-teams-for-calling"></a>部署 Teams 用于通话

专线通话是将持续开发的 Teams 功能，并将逐步提供取代 Skype for Business 的优势功能。 贵组织考虑 Teams 专线通话功能满足关键业务需求时，可以在租户级别配置以下设置以在 Teams 中启用专线通话。 

<table>
<thead>
<tr class="header">
<th align="left">部分</th>
<th align="left">设置</th>
<th align="left">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>通话和会议</strong></td>
<td align="left"><p>允许专线通话：<strong>开启</strong></p></td>
<td align="left"><p>启用此设置将允许用户进行私人通话（音频和视频）</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>注意</p></td>
<td align="left"><br><br>允许用户私人聊天：启用此设置将允许用户与其他用户进行私人聊天。</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


在此阶段，必须指示所有用户选择 Teams 作为首选通话应用。

通过启用专线通话，Teams 将提供 Skype for Business 当前提供的所有功能，用户可以开始使用 Teams 满足其通信与协作需求。


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><strong>下一步操作：</strong> 一旦 Teams 启动并与 Skype for Business 并行运行，即可[通过用户采用推动价值](continue-journey.md)，同时继续从 Skype for Business 到 Teams 的旅程。</td>
</tr>
</thead>
<tbody>
</tbody>
</table>
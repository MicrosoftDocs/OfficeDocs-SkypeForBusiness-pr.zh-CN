---
title: 配置网络，对于 Microsoft 小组的服务清单
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 当您配置您的网络小组按照核心待办任务，此核对清单中的活动。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39c0fe1eb20ca19179f02c9f0395696118770e8d
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="configure-networking"></a>配置网络

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 评审团队的网络要求 | 进入网络的详细信息之前，有全面了解您的网络要求。 | | [对于 Microsoft 小组准备您组织的网络](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| 2  | 提供网络准备工作研讨会 | 完成网络准备工作研讨会从 MyAdvisor，并使用您的团队能够识别解决关注的领域采取补救措施的一部分。 | | [MyAdvisor 网络就绪资产](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| 3  | 使用网络计划 | 使用网络规划人员来计算所需的所有位置和作用域中的网站的带宽。 | | [MyAdvisor 网络规划器](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)                                                                                   |
| 4  | 验证用户连接所需的 NAT 池大小 | 确保足够的公用 IP 地址分配到 NAT 池中以防止端口耗尽。 端口的耗尽将导致内部用户和设备无法连接到 Office 365 提供服务。 <br/><br/>连接性问题都是云服务的用户感觉问题的主要原因。 | | [与 Office 365 的 NAT 支持](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 5  | 实现最有效的路由到 Microsoft 数据中心 | 确定可以使用本地或各地区的出口点以尽可能高效地连接到 Microsoft 网络的位置。 <br/><br/>在**附加信息**列中介绍了客户端可以利用 Office 365 提供名称解析和 IP 路由有效地连接到最接近的区域数据中心中的功能。 | | [Office 365 客户端连接](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 6  | 配置防火墙端口请求连接到工作组 | 查看 Office 365 Url 和 IPs 来识别和测试所需的内部部署客户端和服务器以及 Office 365 提供服务之间的连接的防火墙端口。 <br/><br/>对于受支持的环境，必须在防火墙上打开所有端口。 未能打开某些端口或范围将会对用户体验产生负面影响。 配置您的防火墙根据本指南中的**其他信息**列上媒体端口。 | | [Office 365 Url 和 IP 地址-Microsoft 小组](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| 7  | 配置代理服务器 | 配置您的环境，以便绕过代理服务器，可以直接到 Office 365 连接用户，通过使用 UDP，最佳音频和视频质量。 当实时媒体不得不遍历一个代理服务器时，将强制在团队中的媒体堆栈故障回复到 TCP，对质量产生负面影响。 <br/><br/>为高质量的用户体验中，总是更喜欢使用 UDP TCP 段。 | | [规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) |
| 8  | 配置拆分隧道 VPN | 我们建议绕过 VPN，通常称为*拆分隧道 VPN*的团队通信提供的备用路径。 拆分隧道意味着 Office 365 的通讯不通过 VPN 但而直接转到 Office 365。 此更改对质量，将产生积极影响，而且还提供辅助福利减少从 VPN 设备和组织的网络负载。 | | 若要实现拆分隧道 VPN，请咨询 VPN 配置详细信息的供应商联系。 |
| 9  | 通过使用 QoS 配置数据包优先级 | 在受管网络的所有环节上应实现 QoS。 甚至当网络供应充足的带宽，QoS 提供意料之外的网络事件发生的风险。 当实现 QoS 时，语音通信确定优先级别，以便这些意外的事件不会对质量产生负面影响。 | | [规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) <br/><br/>[在 Microsoft 团队的服务质量](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| 10 | Wi-fi 网络的质量和性能优化 | 有几个因素会影响到您优化您的 Wi-fi® 网络： <ul><li>实现 QoS 或 Wi-fi 多媒体 (WMM)，以确保该媒体通讯通过 Wi-fi 网络优先顺序。</li><li>规划和优化 Wi-Fi 区段和访问点的位置。 2.4 GHz 范围可能提供足够的性能，具体取决于访问点位置。</li></ul> 有关具体指导，请参考 Wi-Fi 供应商。 | | [终结点的的 Wi-Fi 建议](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#wi-fi-recommendations-for-endpoints) |
| 11 | 通过使用网络评估工具来验证网络连接 | 使用 Skype 业务和团队网络评估工具来测试连接到所有 IP 地址和端口中使用 Skype 在线业务和团队的呼叫和会议。 下载该工具，以及有关如何使用该工具和解释测试结果的详细信息，请参阅 Usage.docx。 我们建议您从客户端计算机在每个团队使用者所在的位置运行该工具。 | | [Skype 业务和团队网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799) |
---
title: 编辑 Office Web Apps 服务器设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/19/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
description: 编辑配置的 Office Web Apps Server 的属性。 可编辑以下属性：
ms.openlocfilehash: e9f4a188c5cb58be685db4ea44157f2897ebe5ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095536"
---
# <a name="edit-office-web-apps-server-settings"></a><span data-ttu-id="b8e41-104">编辑 Office Web Apps Server 设置</span><span class="sxs-lookup"><span data-stu-id="b8e41-104">Edit Office Web Apps Server Settings</span></span>

<span data-ttu-id="b8e41-105">编辑配置的 Office Web Apps Server 的属性。</span><span class="sxs-lookup"><span data-stu-id="b8e41-105">You edit the properties of the configured Office Web Apps Server.</span></span> <span data-ttu-id="b8e41-106">可编辑以下属性：</span><span class="sxs-lookup"><span data-stu-id="b8e41-106">The following properties are available to edit:</span></span>

 <span data-ttu-id="b8e41-107">**Office Web Apps Server FQDN：** 此属性定义 Office Web Apps Server 的完全限定域名，如果 IPv6 用于) 记录，则应该匹配域名系统 (DNS) 主机 A 或 AAAA (。</span><span class="sxs-lookup"><span data-stu-id="b8e41-107">**Office Web Apps Server FQDN**: This property defines the fully qualified domain name of the Office Web Apps Server and should match a domain name system (DNS) host A or AAAA (if IPv6 is being used) record.</span></span>

 <span data-ttu-id="b8e41-108">**Office Web Apps Server** 发现 URL：统一资源定位器 (URL) ，对于客户端访问 Office Web Apps Server，如果服务器位于除内部网络外的其他网络区域中，可能需要编辑默认地址。</span><span class="sxs-lookup"><span data-stu-id="b8e41-108">**Office Web Apps Server discovery URL**: The uniform resource locator (URL) for client access to the Office Web Apps Server, you may need to edit this address from its default if the server is placed in another network zone other than the internal network for your deployment.</span></span>

<span data-ttu-id="b8e41-109">如果此服务器部署在外围网络或将外围网络、信任度低的网络和互联网与您内部部署隔离的内部防火墙外部的其他网络区域中，则选中“Office Web Apps 服务器部署在外部网络中”复选框。</span><span class="sxs-lookup"><span data-stu-id="b8e41-109">Select the check box **Office Web Apps Server is deployed in an external network** if this server is deployed in your perimeter network or other network zone that is outside of your internal firewall separating the perimeter network, less trusted networks, and the Internet from your internal deployment.</span></span>

![Office Web Apps 设置扩展器](../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="b8e41-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8e41-111">See also</span></span>

[<span data-ttu-id="b8e41-112">用于会议的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="b8e41-112">Components and Topologies for Conferencing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)
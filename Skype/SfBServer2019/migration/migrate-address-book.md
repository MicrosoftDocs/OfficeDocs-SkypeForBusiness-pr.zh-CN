---
title: 迁移通讯簿
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 一般情况下，您的拓扑的其余部分以及迁移通讯簿。 但是，您可能需要执行一些迁移后的步骤，如果旧环境中自定义以下：
ms.openlocfilehash: 01279284086499b112028644ea0e1ca2fc708dd0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370767"
---
# <a name="migrate-address-book"></a><span data-ttu-id="11cb3-104">迁移通讯簿</span><span class="sxs-lookup"><span data-stu-id="11cb3-104">Migrate Address Book</span></span>

<span data-ttu-id="11cb3-105">一般情况下，您的拓扑的其余部分以及迁移通讯簿。</span><span class="sxs-lookup"><span data-stu-id="11cb3-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="11cb3-106">但是，您可能需要执行一些迁移后的步骤，如果旧环境中自定义以下：</span><span class="sxs-lookup"><span data-stu-id="11cb3-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="11cb3-107">将**PartitionbyOU** WMI 属性设置为按组织单位 (OU) 的组通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="11cb3-107">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span> 

- <span data-ttu-id="11cb3-108">自定义通讯簿规范化规则。</span><span class="sxs-lookup"><span data-stu-id="11cb3-108">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="11cb3-109">更改将**UseNormalizationRules**参数的默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="11cb3-109">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 

  <span data-ttu-id="11cb3-110">**分组的通讯簿条目**</span><span class="sxs-lookup"><span data-stu-id="11cb3-110">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="11cb3-111">如果将**PartitionbyOU** WMI 属性设置为 True 可为每个 OU 中创建通讯簿，您需要的用户和联系人设置**Msrtcsip-groupingid** Active Directory 属性，如果您想要继续进行通讯簿条目分组。</span><span class="sxs-lookup"><span data-stu-id="11cb3-111">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="11cb3-112">您可能希望为通讯簿条目分组来限制的通讯簿搜索的范围。</span><span class="sxs-lookup"><span data-stu-id="11cb3-112">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="11cb3-113">若要使用**Msrtcsip-groupingid**属性，编写脚本以填充属性，分配的所有用户想要组合在一起的相同值。</span><span class="sxs-lookup"><span data-stu-id="11cb3-113">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="11cb3-114">例如，分配一个 single 值，在对 OU 中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="11cb3-114">For example, assign a single value for all the users in an OU.</span></span> 

 <span data-ttu-id="11cb3-115">**通讯簿规范化规则**</span><span class="sxs-lookup"><span data-stu-id="11cb3-115">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="11cb3-116">如果旧环境中自定义通讯簿规范化规则，您必须将自定义的规则迁移到试点池。</span><span class="sxs-lookup"><span data-stu-id="11cb3-116">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="11cb3-117">如果您未自定义通讯簿规范化规则，则必须 nothing 通讯簿服务的迁移。</span><span class="sxs-lookup"><span data-stu-id="11cb3-117">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="11cb3-118">有关业务服务器 2019年的 Skype 的默认规范化规则是旧安装的默认规则相同。</span><span class="sxs-lookup"><span data-stu-id="11cb3-118">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="11cb3-119">按照本节迁移自定义的规范化规则后面的过程。</span><span class="sxs-lookup"><span data-stu-id="11cb3-119">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="11cb3-120">如果您的组织使用远程呼叫控制并且您自定义通讯簿规范化规则，您必须在本主题中执行过程，然后才能使用远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="11cb3-120">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="11cb3-121">过程要求中的 RTCUniversalServerAdmins 组或同等权限的成员身份。</span><span class="sxs-lookup"><span data-stu-id="11cb3-121">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="11cb3-122">**UseNormalizationRules 设置为 False**</span><span class="sxs-lookup"><span data-stu-id="11cb3-122">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="11cb3-123">如果您将值设置为**UseNormalizationRules**为 False，以便用户可以使用电话号码，如中定义无业务服务器 2019 Skype 的 Active Directory 域服务应用规范化规则，您需要设置**UseNormalizationRules**和**IgnoreGenericRules**参数为 True。</span><span class="sxs-lookup"><span data-stu-id="11cb3-123">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="11cb3-124">按照此部分将这些参数设置为 True 中稍后介绍的过程。</span><span class="sxs-lookup"><span data-stu-id="11cb3-124">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="11cb3-125">迁移通讯簿自定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="11cb3-125">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="11cb3-126">通讯簿共享文件夹的根目录中查找 Company_Phone_Number_Normalization_Rules.txt 文件，并将其复制到您的业务服务器 2019年试点池的 Skype 中的通讯簿共享文件夹的根目录。</span><span class="sxs-lookup"><span data-stu-id="11cb3-126">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="11cb3-127">已在 ABS Web 组件文件目录中安装通讯簿规范化规则示例。</span><span class="sxs-lookup"><span data-stu-id="11cb3-127">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="11cb3-128">路径为 **$installedDriveLetter: \Program Files\Microsoft Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt 的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="11cb3-128">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="11cb3-129">可复制此文件，并将其重命名为**Company_Phone_Number_Normalization_Rules.txt**为通讯簿共享的文件夹的根目录。</span><span class="sxs-lookup"><span data-stu-id="11cb3-129">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="11cb3-130">例如，通讯簿中 **$serverX**共享，则路径将会类似于： \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*。</span><span class="sxs-lookup"><span data-stu-id="11cb3-130">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="11cb3-131">使用文本编辑器，如记事本中，打开 Company_Phone_Number_Normalization_Rules.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="11cb3-131">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="11cb3-132">某些类型的项将无法正常工作 Skype 中的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="11cb3-132">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="11cb3-133">在此步骤中所述的条目的类型的文件中查找、 根据需要，对其进行编辑和保存对试点池中通讯簿共享文件夹的更改。</span><span class="sxs-lookup"><span data-stu-id="11cb3-133">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="11cb3-134">包含需要的空格或标点符号原因规范化规则失败，因为这些字符去除超出输入到的规范化规则的字符串的字符串。</span><span class="sxs-lookup"><span data-stu-id="11cb3-134">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="11cb3-135">如果必须包含必需的空格或标点的字符串，您需要修改字符串。</span><span class="sxs-lookup"><span data-stu-id="11cb3-135">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="11cb3-136">例如，以下字符串会导致规范化规则失败：</span><span class="sxs-lookup"><span data-stu-id="11cb3-136">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="11cb3-137">以下字符串不会导致规范化规则失败：</span><span class="sxs-lookup"><span data-stu-id="11cb3-137">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="11cb3-138">若要将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true</span><span class="sxs-lookup"><span data-stu-id="11cb3-138">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="11cb3-139">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="11cb3-139">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="11cb3-140">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="11cb3-140">Do one of the following:</span></span>

   - <span data-ttu-id="11cb3-141">如果您的部署包括仅 Skype 的业务服务器 2019，在要以**将 UseNormalizationRules**和**IgnoreGenericRules**的值更改为 True 的全局级别运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="11cb3-141">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="11cb3-142">如果您的部署包括业务服务器 2019年和旧安装 Skype 的组合，运行以下 cmdlet 并将其分配给每个 Skype 业务服务器 2019年池拓扑中：</span><span class="sxs-lookup"><span data-stu-id="11cb3-142">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="11cb3-143">等待在所有池上发生中央管理存储复制。</span><span class="sxs-lookup"><span data-stu-id="11cb3-143">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="11cb3-144">修改电话规范化规则文件，若要清除的内容部署"Company_Phone_Number_Normalization_Rules.txt"。</span><span class="sxs-lookup"><span data-stu-id="11cb3-144">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="11cb3-145">文件是在每个 Skype 业务服务器 2019年池的文件共享上。</span><span class="sxs-lookup"><span data-stu-id="11cb3-145">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="11cb3-146">如果文件不存在，然后创建一个名为"Company_Phone_Number_Normalization_Rules.txt"的空文件。</span><span class="sxs-lookup"><span data-stu-id="11cb3-146">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="11cb3-147">等待几分钟，以便所有前端池读取新文件。</span><span class="sxs-lookup"><span data-stu-id="11cb3-147">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="11cb3-148">在部署中的业务服务器 2019年池的每个 Skype 上运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="11cb3-148">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```



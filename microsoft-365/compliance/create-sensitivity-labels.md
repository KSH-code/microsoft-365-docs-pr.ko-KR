---
title: 민감도 레이블 생성 및 게시
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 조직의 문서 및 전자 메일을 분류하고 보호하는 데 필요한 민감도 레이블을 생성, 구성 및 게시하기 위한 지침입니다.
ms.openlocfilehash: edcfcf5a4f4891e4e1159c4c42327e59ceb35449
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238405"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="3a034-103">민감도 레이블과 해당 정책 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="3a034-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="3a034-104">[우편물 레이블을 만들고 게시하려면](sensitivity-labels.md), [Microsoft 365 준수 센터](https://compliance.microsoft.com/)와 같은 레이블 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-104">To create and publish your [sensitivity labels](sensitivity-labels.md), go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="3a034-105">Microsoft 365 보안 센터나 Office 365 보안 및 준수 센터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-105">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="3a034-106">먼저 Office 앱과 서비스에서 사용할 수 있게 하고자 하는 민감도 레이블을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-106">First, create and configure the sensitivity labels that you want to make available in Office apps and for services.</span></span> <span data-ttu-id="3a034-107">그런 다음 구성한 레이블과 정책 설정을 포함하는 레이블 정책을 하나 이상 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-107">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="3a034-108">이 정책은 선택된 사용자와 위치에 대한 레이블과 설정을 게시하는 레이블 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-108">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="3a034-109">민감도 레이블 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="3a034-109">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="3a034-110">레이블 관리 센터에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-110">In your labeling admin center, navigate to ClassificationSensitivity labels.</span></span>
    
    - <span data-ttu-id="3a034-111">Microsoft 365 규정 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="3a034-111">Microsoft 365 compliance center</span></span> 
        - <span data-ttu-id="3a034-112">**솔루션** > **정보 보호(미리 보기)**</span><span class="sxs-lookup"><span data-stu-id="3a034-112">**Solutions** > **Information protection (preview)**</span></span>
        
        <span data-ttu-id="3a034-113">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-113">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="3a034-114">Microsoft 365 보안 센터:</span><span class="sxs-lookup"><span data-stu-id="3a034-114">Microsoft 365 security center</span></span> 
        - <span data-ttu-id="3a034-115">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="3a034-115">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="3a034-116">Office 365 보안 및 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="3a034-116">Office 365 Security & Compliance Center</span></span>
        - <span data-ttu-id="3a034-117">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="3a034-117">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="3a034-118">**레이블** 탭에서 **+레이블 만들기**를 선택하 여 **새 민감도 레이블** 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-118">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="3a034-119">레이블 설정에 대한 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-119">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="3a034-120">레이블 설정에 대한 자세한 정보는 개요 정보에서 [할 수 있는 민감도 레이블](sensitivity-labels.md#what-sensitivity-labels-can-do)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a034-120">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="3a034-121">이 단계를 반복하여 레이블을 더 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-121">Repeat these steps to create more labels.</span></span> <span data-ttu-id="3a034-122">그러나 하위 레이블을 만들고자 하는 경우 먼저 상위 레이블을 선택하고 **추가 작업**에서 **...** 을 선택한 다음 **하위 레이블 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-122">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="3a034-123">필요한 레이블을 모두 만든 경우 해당 주문을 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-123">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="3a034-124">레이블 순서를 변경하려면 **추가 작업**에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-124">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="3a034-125">자세한 내용은 개요 정보에서 [레이블 우선 순위(순서가 중요함)](sensitivity-labels.md#label-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a034-125">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="3a034-126">기존 레이블을 편집하려면 레이블을 선택하고 **레이블 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-126">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="3a034-127">이렇게 하면 3단계에서 모든 레이블 설정을 변경할 수 있는 **민감도 레이블 편집** 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-127">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> <span data-ttu-id="3a034-128">레이블 정책을 사용하여 레이블을 이미 게시한 경우에는 추가 단계가 필요 하지 않지만 변경 사항이 사용자 및 위치로 복제될 때까지 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-128">If the label is already published by using a label policy, no extra steps are needed, but allow up to 24 hours for the changes to replicate to users and locations.</span></span>

<span data-ttu-id="3a034-129">레이블을 게시할 때까지 레이블을 앱이나 서비스에서 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-129">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="3a034-130">레이블을 게시하려면 레이블 정책에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-130">To publish the labels, they must be added to a label policy.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="3a034-131">Office 365 보안 및 준수 센터 PowerShell를 이용한 추가 레이블 설정</span><span class="sxs-lookup"><span data-stu-id="3a034-131">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="3a034-132">추가 레이블 설정은 [Office 365 보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)에서 [레이블 설정](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-132">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="3a034-133">예를 들어 *LocaleSettings* 매개 변수를 사용하여 레이블 이름 및 도구 설명에 다른 언어를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-133">For example, use the the *LocaleSettings* parameter to specify different languages for your label names and tooltips.</span></span> 

<span data-ttu-id="3a034-134">이 cmdlet을 사용하여 Azure Information Protection 통합 레이블 클라이언트에 대한 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-134">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="3a034-135">이 고급 설정에는 레이블 색상 설정이 포함되며, 레이블이 적용된 경우에는 사용자 지정 속성 적용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-135">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="3a034-136">전체 목록을 확인하려면 [레이블 정책에 대해 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a034-136">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="3a034-137">레이블 정책을 만들어 민감도 레이블 게시</span><span class="sxs-lookup"><span data-stu-id="3a034-137">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="3a034-138">레이블 관리 센터에서 **분류** > **민감도 레이블**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-138">In your labeling admin center, navigate to **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="3a034-139">**레이블 정책** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-139">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="3a034-140">**레이블 게시**를 선택하여 **정책 만들기 마법사**를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-140">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="3a034-141">**민감도 레이블을 선택하여 게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-141">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="3a034-142">앱과 서비스에서 사용할 수 있도록 설정할 레이블을 선택한 다음 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-142">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="3a034-143">선택한 레이블을 검토하 고 내용을 변경하려면 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-143">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="3a034-144">그렇지 않으면 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-144">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="3a034-145">화면에 나타나는 메시지에 따라 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-145">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="3a034-146">설정에 대한 자세한 정보는 개요 정보에서 [할 수 있는 레이블 정책](sensitivity-labels.md#what-label-policies-can-do)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a034-146">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="3a034-147">여러 사용자나 위치에 대해 서로 다른 정책 설정이 필요한 경우에는 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-147">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="3a034-148">예를 들어 사용자 그룹에 대한 추가 레이블이나 사용자 하위 집합에 대해 다른 기본 레이블을 원하는 경우가 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-148">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="3a034-149">사용자 또는 위치에 충돌이 발생할 수 있는 레이블 정책을 여러 개 만드는 경우에는 정책 순서를 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-149">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="3a034-150">레이블 정책 순서를 변경하려면 **추가 작업**에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-150">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="3a034-151">자세한 내용은 개요 정보에서 [레이블 정책 우선 순위(순서가 중요함)](sensitivity-labels.md#label-policy-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a034-151">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="3a034-152">마법사를 완료하면 자동으로 레이블 정책이 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-152">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="3a034-153">게시된 정책을 변경하려면 정책을 편집하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-153">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="3a034-154">사용자가 선택할 특정 게시 또는 재게시 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-154">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="3a034-155">기존 레이블 정책을 편집하려면 레이블을 선택하고 **정책 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-155">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="3a034-156">이렇게 하면 포함할 레이블과 레이블 설정을 편집할 수 있는 **정책 만들기** 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-156">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="3a034-157">마법사를 완료하면 변경 내용이 선택된 사용자 및 위치로 자동 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-157">When you complete the wizard, any changes are automatically replicated to the selected users and locations.</span></span> <span data-ttu-id="3a034-158">복제를 완료하기 위해 최대 24시간을 허용하세요.</span><span class="sxs-lookup"><span data-stu-id="3a034-158">Allow up to 24 hours for the replication to complete.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="3a034-159">Office 365 보안 및 준수 센터 PowerShell를 이용한 추가 레이블 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3a034-159">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="3a034-160">추가 레이블 정책 설정은 [Office 365 보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)에서 [레이블 설정](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-160">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="3a034-161">이 cmdlet을 사용하여 Azure Information Protection 통합 레이블 클라이언트에 대한 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-161">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="3a034-162">이 고급 설정에는 Outlook에 다른 기본 레이블 설정이 포함되어 있으며, Outlook에서 보내는 전자 메일에 대해 경고, 정렬 또는 차단하는 팝업 메시지를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-162">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="3a034-163">전체 목록을 확인하려면 [레이블에 대해 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a034-163">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="3a034-164">이 cmdlet을 사용하여 레이블 정책에서 레이블을 추가하거나 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a034-164">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="3a034-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3a034-165">Next steps</span></span>

<span data-ttu-id="3a034-166">특정 시나리오에 대해 민감도 레이블을 구성하고 사용하려면 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a034-166">To configure and use your sensitivity labels for specific scenarios, see the following articles:</span></span>

- [<span data-ttu-id="3a034-167">민감도 레이블에서 암호화를 사용하여 콘텐츠 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="3a034-167">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="3a034-168">민감도 레이블을 콘텐츠에 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="3a034-168">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="3a034-169">팀, 그룹 및 사이트와 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="3a034-169">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="3a034-170">SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="3a034-170">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="3a034-171">레이블이 사용되는 방식을 모니터링 하려면 [레이블 분석을 통한 레이블 사용량 보기](label-analytics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a034-171">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>
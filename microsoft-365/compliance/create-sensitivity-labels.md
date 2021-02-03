---
title: 민감도 레이블 생성 및 게시
f1.keywords:
- NOCSH
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
description: '모든 Microsoft Information Protection 솔루션에 대한 요구 사항: 조직의 문서와 전자 메일을 분류하고 보호하기 위해 민감도 레이블을 생성, 구성 및 게시합니다.'
ms.openlocfilehash: b7943259d3a20cbf4fd6d8b0b57ca7c027e74d3f
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084659"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="0d110-103">민감도 레이블과 해당 정책 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="0d110-103">Create and configure sensitivity labels and their policies</span></span>

><span data-ttu-id="0d110-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="0d110-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0d110-105">모든 Microsoft Information Protection 솔루션(때로는 MIP로 줄여서 부름)은 [민감도 레이블](sensitivity-labels.md)을 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-105">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="0d110-106">이러한 레이블을 만들고 게시하려면, [Microsoft 365 준수 센터](https://compliance.microsoft.com/)와 같은 레이블 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-106">To create and publish these labels, go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="0d110-107">Microsoft 365 보안 센터나 보안 및 준수 센터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-107">You can also use the Microsoft 365 security center, or the Security & Compliance Center.</span></span>

<span data-ttu-id="0d110-108">먼저 앱과 다른 서비스에서 사용할 수 있게 하고자 하는 민감도 레이블을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-108">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="0d110-109">예를 들어 사용자가 Office 앱에서 보고 적용하도록 하려는 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-109">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="0d110-110">그런 다음 구성한 레이블과 정책 설정을 포함하는 레이블 정책을 하나 이상 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-110">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="0d110-111">이 정책은 선택된 사용자와 위치에 대한 레이블과 설정을 게시하는 레이블 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-111">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0d110-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="0d110-112">Before you begin</span></span>

<span data-ttu-id="0d110-113">조직의 전역 관리자는 민감도 레이블의 모든 측면을 작성하고 관리할 수있는 모든 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-113">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="0d110-114">전역 관리자로 로그인하지 않은 경우 [민감도 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d110-114">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="0d110-115">민감도 레이블 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="0d110-115">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="0d110-116">레이블 관리 센터에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-116">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="0d110-117">Microsoft 365 규정 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="0d110-117">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="0d110-118">**솔루션** > **정보 보호**</span><span class="sxs-lookup"><span data-stu-id="0d110-118">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="0d110-119">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-119">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="0d110-120">Microsoft 365 보안 센터:</span><span class="sxs-lookup"><span data-stu-id="0d110-120">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="0d110-121">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="0d110-121">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="0d110-122">보안 및 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="0d110-122">Security & Compliance Center:</span></span>
        - <span data-ttu-id="0d110-123">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="0d110-123">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="0d110-124">**레이블** 페이지에서 **+레이블 만들기** 를 선택하여 새 민감도 레이블 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-124">On the **Labels** page, select **+ Create a label** to start the New sensitivity label wizard.</span></span> 
    
    <span data-ttu-id="0d110-125">예를 들어, Microsoft 365 규정 준수 센터에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-125">For example, from the Microsoft 365 compliance center:</span></span>
    
    ![민감도 레이블 만들기](../media/create-sensitivity-label-full.png)
    
    > [!NOTE]
    > <span data-ttu-id="0d110-127">기본적으로 테넌트에는 레이블이 없으며 레이블을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-127">By default, tenants don't have any labels and you must create them.</span></span> <span data-ttu-id="0d110-128">예제 그림에 나와 있는 레이블에 [Azure Information Protection에서 마이그레이션된](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) 기본 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-128">The labels in the example picture show default labels that were [migrated from Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels).</span></span>

3. <span data-ttu-id="0d110-129">**이 레이블에 대한 범위 정의** 페이지에서 선택한 옵션은 구성할 수 있는 설정에 대한 레이블 범위와 게시될 때 표시되는 위치를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-129">On the **Define the scope for this label** page, the options selected determine the label's scope for the settings that you can configure and where they will be visible when they are published:</span></span>
    
    ![민감도 레이블 범위](../media/sensitivity-labels-scopes.png)
    
    - <span data-ttu-id="0d110-131">**파일 및 전자 메일** 이 선택된 경우, 이 마법사에서 Office Word 및 Outlook과 같은 민감도 레이블을 지원하는 앱에 적용되는 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-131">If **Files & emails** is selected, you can configure settings in this wizard that apply to apps that support sensitivity labels, such as Office Word and Outlook.</span></span> <span data-ttu-id="0d110-132">이 옵션이 선택되지 않은 경우, 마법사는 해당 설정의 첫 번째 페이지를 표시하지만 사용자는 설정을 구성할 수 없으며 레이블은 이들 앱에서 사용자들이 선택하도록 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-132">If this option isn't selected, the wizard displays the first page of these settings but you can't configure them and the labels won't be available for users to select in these apps.</span></span>
    
    - <span data-ttu-id="0d110-133">**그룹 및 사이트** 가 선택된 경우, 이 마법사에서 Microsoft 365 그룹 및 Teams와 SharePoint용 사이트에 적용되는 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-133">If **Groups & sites** is selected, you can configure settings in this wizard that apply to Microsoft 365 groups, and sites for Teams and SharePoint.</span></span> <span data-ttu-id="0d110-134">이 옵션이 선택되지 않은 경우, 마법사는 해당 설정의 첫 번째 페이지를 표시하지만 사용자는 설정을 구성할 수 없으며 레이블은 그룹 및 사이트에 대해 사용자들이 선택하도록 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-134">If this option isn't selected, the wizard displays the first page of these settings but you can't configure them and the labels won't be available for users to select for groups and site.</span></span>
    
    <span data-ttu-id="0d110-135">**Azure Purview 자산(미리 보기)** 범위에 대한 자세한 내용은 [Azure Purview에서 내용에 자동으로 레이블을 지정](https://docs.microsoft.com/azure/purview/create-sensitivity-label)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-135">For information about the **Azure Purview assets (preview)** scope, see [Automatically label your content in Azure Purview](https://docs.microsoft.com/azure/purview/create-sensitivity-label).</span></span>

4. <span data-ttu-id="0d110-136">화면에 나타나는 레이블 설정 마법사 메시지를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-136">Follow the prompts in the wizard for the label settings.</span></span>
    
    <span data-ttu-id="0d110-137">레이블 설정에 대한 자세한 정보는 개요 정보에서 [민감도 레이블이 수행하는 작업](sensitivity-labels.md#what-sensitivity-labels-can-do)을 참조하고 개별 설정 마법사의 도움말을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-137">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information and use the help in the wizard for individual settings.</span></span>

5. <span data-ttu-id="0d110-138">이 단계를 반복하여 레이블을 더 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-138">Repeat these steps to create more labels.</span></span> <span data-ttu-id="0d110-139">그러나 하위 레이블을 만들고자 하는 경우 먼저 상위 레이블을 선택하고 **추가 작업** 에서 **...** 을 선택한 다음 **하위 레이블 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-139">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

6. <span data-ttu-id="0d110-140">필요한 레이블을 모두 만든 경우 해당 주문을 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-140">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="0d110-141">레이블 순서를 변경하려면 **추가 작업** 에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-141">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="0d110-142">자세한 내용은 개요 정보에서 [레이블 우선 순위(순서가 중요함)](sensitivity-labels.md#label-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-142">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="0d110-143">기존 레이블을 편집하려면 해당 레이블을 선택하고 **레이블 편집** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-143">To edit an existing label, select it, and then select the **Edit label** button:</span></span>

![레이블 단추를 편집하여 민감도 레이블 편집](../media/edit-sensitivity-label-full.png)

<span data-ttu-id="0d110-145">이 단추를 선택하면 4단계에서 모든 레이블 설정을 변경할 수 있는 **민감도 레이블 편집** 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-145">This button starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 4.</span></span>

<span data-ttu-id="0d110-146">사용자에게 미치는 영향을 이해하지 못하는 경우 레이블을 삭제하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-146">Don't delete a label unless you understand the impact for users.</span></span> <span data-ttu-id="0d110-147">자세한 내용은 [레이블 제거 및 삭제](#removing-and-deleting-labels) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-147">For more information, see the [Removing and deleting labels](#removing-and-deleting-labels) section.</span></span> 

> [!NOTE]
> <span data-ttu-id="0d110-148">레이블 정책을 사용하여 이미 게시된 레이블을 편집하면 마법사를 완료할 때 추가 단계가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-148">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="0d110-149">예를 들어 동일한 사용자가 변경 내용을 사용할 수 있도록 새 레이블 정책에 추가하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-149">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="0d110-150">그러나 변경 사항이 모든 앱과 서비스에 복제되려면 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-150">However, allow up to 24 hours for the changes to replicate to all apps and services.</span></span>

<span data-ttu-id="0d110-151">레이블을 게시할 때까지 레이블을 앱이나 서비스에서 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-151">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="0d110-152">레이블을 게시하려면 [레이블 정책에 추가](#publish-sensitivity-labels-by-creating-a-label-policy)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-152">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d110-153">이 **레이블** 탭에서, 새 레이블 정책을 만들어야 하는 경우가 아니면 **레이블 게시** 탭 (또는 레이블을 편집할 때 **레이블 게시** 단추)을 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-153">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="0d110-154">다른 레이블이나 다른 정책 설정이 필요한 경우에만 여러 레이블 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-154">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="0d110-155">레이블 정책을 최대한 적게 보유하는 것이 좋습니다. 조직에 대한 레이블 정책을 하나만 보유하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-155">Aim to have as few label policies as possible—it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-security--compliance-center-powershell"></a><span data-ttu-id="0d110-156">보안 및 준수 센터 PowerShell를 이용한 추가 레이블 설정</span><span class="sxs-lookup"><span data-stu-id="0d110-156">Additional label settings with Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="0d110-157">추가 레이블 설정은 [보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell)에서 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/set-label) cmdlet으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-157">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/set-label) cmdlet from [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell).</span></span>

<span data-ttu-id="0d110-158">예시:</span><span class="sxs-lookup"><span data-stu-id="0d110-158">For example:</span></span>

- <span data-ttu-id="0d110-159">사용자가 로컬 언어로 레이블 이름과 도구 설명을 확인하기 위한 다국적 배포에는 *LocaleSettings* 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-159">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="0d110-160">[다음 섹션](#example-configuration-to-configure-a-sensitivity-label-for-different-languages)에는 프랑스어, 이탈리아어, 독일어에 대한 레이블 이름 및 도구 설명 텍스트를 지정하는 예제 구성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-160">The [following section](#example-configuration-to-configure-a-sensitivity-label-for-different-languages) has an example configuration that specifies the label name and tooltip text for French, Italian, and German.</span></span>

- <span data-ttu-id="0d110-161">Azure Information Protection 통합 레이블 클라이언트의 경우, 레이블 색 설정과 레이블이 적용된 경우 사용자 지정 속성 적용을 포함하는 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-161">For the Azure Information Protection unified labeling client only, specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) that include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="0d110-162">전체 목록을 보려면 이 클라이언트의 관리자 가이드에서 [레이블의 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-162">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels) from this client's admin guide.</span></span>

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="0d110-163">다양한 언어로 민감도 레이블을 구성하는 예제 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-163">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="0d110-164">다음 예제는 도구 설명에 대한 개체 틀 텍스트를 사용하 여 "Public" 이라는 레이블의 PowerShell 구성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-164">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="0d110-165">이 예제에서는 프랑스어, 이탈리아어, 독일어에 대한 레이블 이름 및 도구 설명 텍스트가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-165">In this example, the label name and tooltip text are configured for French, Italian, and German.</span></span>

<span data-ttu-id="0d110-166">이 구성의 결과로 해당 표시 언어를 사용하는 Office 앱을 사용하는 사용자는 동일한 언어로 레이블 이름과 도구 설명을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-166">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="0d110-167">마찬가지로, 파일 탐색기에서 파일을 레이블 지정하기 위해 Azure Information Protection 통합 레이블 클라이언트를 설치한 경우 해당 언어 버전의 Windows를 사용하는 사용자는 레이블 지정을 위해 마우스 오른쪽 단추 클릭 작업을 할 때 로컬 언어로 레이블 이름과 도구 설명을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-167">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="0d110-168">지원해야 하는 언어의 경우에는 Office [언어 식별자](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers)(언어 태그라고도 함)를 사용하여 레이블 이름 및 도구 설명에 대한 고유한 번역을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-168">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="0d110-169">PowerShell에서 명령을 실행하기 전에 먼저 [보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-169">Before you run the commands in PowerShell, you must first [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>


```powershell
$Languages = @("fr-fr","it-it","de-de")
$DisplayNames=@("Publique","Publico","Oeffentlich")
$Tooltips = @("Texte Français","Testo italiano","Deutscher text")
$label = "Public"
$DisplayNameLocaleSettings = [PSCustomObject]@{LocaleKey='DisplayName';
Settings=@(
@{key=$Languages[0];Value=$DisplayNames[0];}
@{key=$Languages[1];Value=$DisplayNames[1];}
@{key=$Languages[2];Value=$DisplayNames[2];})}
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress),(ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="0d110-170">레이블 정책을 만들어 민감도 레이블 게시</span><span class="sxs-lookup"><span data-stu-id="0d110-170">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="0d110-171">레이블 관리 센터에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-171">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="0d110-172">Microsoft 365 규정 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="0d110-172">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="0d110-173">**솔루션** > **정보 보호**</span><span class="sxs-lookup"><span data-stu-id="0d110-173">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="0d110-174">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-174">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="0d110-175">Microsoft 365 보안 센터:</span><span class="sxs-lookup"><span data-stu-id="0d110-175">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="0d110-176">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="0d110-176">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="0d110-177">보안 및 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="0d110-177">Security & Compliance Center:</span></span>
        - <span data-ttu-id="0d110-178">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="0d110-178">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="0d110-179">**레이블 정책** 탭을 선택한 다음 **레이블 게시** 를 선택하여 정책 만들기 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-179">Select the **Label policies** tab, and then **Publish labels** to start the Create policy wizard:</span></span>
    
    <span data-ttu-id="0d110-180">예를 들어, Microsoft 365 규정 준수 센터에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-180">For example, from the Microsoft 365 compliance center:</span></span>
        
    ![레이블 게시](../media/publish-sensitivity-labels-full.png)
    
    > [!NOTE]
    > <span data-ttu-id="0d110-182">기본적으로 테넌트에는 레이블 정책이 없으며 레이블 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-182">By default, tenants don't have any label policies and you must create them.</span></span> 

3. <span data-ttu-id="0d110-183">마법사에서 **민감도 레이블을 선택하여 게시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-183">In the wizard, select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="0d110-184">앱과 서비스에서 사용할 수 있도록 설정할 레이블을 선택한 다음 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-184">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0d110-185">하위 레이블을 선택한 경우 해당 상위 레이블도 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-185">If you select a sublabel, make sure you also select its parent label.</span></span>
    
4. <span data-ttu-id="0d110-186">선택한 레이블을 검토하 고 내용을 변경하려면 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-186">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="0d110-187">그렇지 않으면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-187">Otherwise, select **Next**.</span></span>

5. <span data-ttu-id="0d110-188">화면에 나타나는 메시지에 따라 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-188">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="0d110-189">표시되는 정책 설정은 선택한 레이블의 범위와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-189">The policy settings that you see match the scope of the labels that you selected.</span></span> <span data-ttu-id="0d110-190">예를 들어 **파일 및 전자 메일** 범위만을 포함하는 레이블을 선택한 경우, **기본적으로 그룹 및 사이트에 이 레이블 적용** 및 **사용자가 그룹 및 사이트에 레이블을 적용하도록 요구** 정책 설정은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-190">For example, if you selected labels that have just the **Files & emails** scope, you don't see the policy settings **Apply this label by default to groups and sites** and **Require users to apply a label to their groups and sites**.</span></span>
    
    <span data-ttu-id="0d110-191">정책 설정에 대한 자세한 정보는 개요 정보에서 [레이블 정책이 수행하는 작업](sensitivity-labels.md#what-label-policies-can-do)을 참조하고 개별 설정 마법사의 도움말을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-191">For more information about these settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information and use the help in the wizard for individual settings.</span></span>
    
    <span data-ttu-id="0d110-192">**Azure Purview 자산에 (미리 보기)** 대해 구성된 레이블의 경우: 이러한 레이블에는 연결된 정책 설정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-192">For labels configured for **Azure Purview assets (preview)**: These labels don't have any associated policy settings.</span></span>

7. <span data-ttu-id="0d110-193">다양한 사용자나 위치에 대해 다양한 정책 설정이 필요한 경우에는 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-193">Repeat these steps if you need different policy settings for different users or scopes.</span></span> <span data-ttu-id="0d110-194">예를 들어 사용자 그룹에 대한 추가 레이블이나 사용자 하위 집합에 대한 다른 기본 레이블을 원하는 경우가 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-194">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span> <span data-ttu-id="0d110-195">또는 레이블이 다양한 범위를 갖도록 구성한 경우가 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-195">Or, if you have configured labels to have different scopes.</span></span>

8. <span data-ttu-id="0d110-196">사용자에 충돌이 발생할 수 있는 레이블 정책을 여러 개 만드는 경우에는 정책 순서를 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-196">If you create more than one label policy that might result in a conflict for a user, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="0d110-197">레이블 정책 순서를 변경하려면 **추가 작업** 에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-197">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="0d110-198">자세한 내용은 개요 정보에서 [레이블 정책 우선 순위(순서가 중요함)](sensitivity-labels.md#label-policy-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-198">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="0d110-199">마법사를 완료하면 자동으로 레이블 정책이 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-199">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="0d110-200">게시된 정책을 변경하려면 정책을 편집하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-200">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="0d110-201">사용자가 선택할 특정 게시 또는 재게시 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-201">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="0d110-202">기존 레이블 정책을 편집하려면 해당 정책을 선택하고 **정책 편집** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-202">To edit an existing label policy, select it, and then select the **Edit Policy** button:</span></span> 

![민감도 레이블 편집하기](../media/edit-sensitivity-label-policy-full.png)

<span data-ttu-id="0d110-204">이 단추를 선택하면 포함할 레이블과 레이블 설정을 편집할 수 있는 **정책 만들기** 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-204">This button starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="0d110-205">마법사를 완료하면 변경 내용이 선택된 사용자 및 서비스로 자동 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-205">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="0d110-206">Windows, macOS, iOS 및 Android에서 Office 앱용 기본 제공 레이블을 사용하는 경우 사용자에게 4시간 이내, 웹용 Office의 경우 1시간 이내에 새 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-206">When you use built-in labeling for Office apps on Windows, macOS, iOS, and Android, users see new labels within four hours, and within one hour for Office on the web.</span></span> <span data-ttu-id="0d110-207">그러나 변경 사항이 모든 앱과 서비스에 복제되려면 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-207">However, allow up to 24 hours for changes to replicate to all apps and services.</span></span>

### <a name="additional-label-policy-settings-with-security--compliance-center-powershell"></a><span data-ttu-id="0d110-208">보안 및 준수 센터 PowerShell를 이용한 추가 레이블 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0d110-208">Additional label policy settings with Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="0d110-209">추가 레이블 정책 설정은 [보안 및 규정 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell)에서 [Set-LabelPolicy](https://docs.microsoft.com/powershell/module/exchange/set-labelpolicy) cmdlet으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-209">Additional label policy settings are available with the [Set-LabelPolicy](https://docs.microsoft.com/powershell/module/exchange/set-labelpolicy) cmdlet from [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell).</span></span>

<span data-ttu-id="0d110-210">Azure Information Protection 통합 레이블 지정 클라이언트의 경우에만, Outlook에 대해 다양한 기본 레이블 설정이 포함된 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정하고, Outlook에서 보내는 전자 메일에 대해 경고, 정렬 또는 차단하는 팝업 메시지를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-210">For the Azure Information Protection unified labeling client only, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) that include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="0d110-211">전체 목록을 보려면 이 클라이언트의 관리자 가이드에서 [레이블 정책에 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-211">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies) from this client's admin guide.</span></span>

## <a name="use-powershell-for-sensitivity-labels-and-their-policies"></a><span data-ttu-id="0d110-212">민감도 레이블과 해당 정책에 PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="0d110-212">Use PowerShell for sensitivity labels and their policies</span></span>

<span data-ttu-id="0d110-213">이제 [보안 및 규정 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell)에서 레이블 지정 관리 센터에 표시되는 모든 설정을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-213">You can now use [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell) to create and configure all the settings you see in your labeling admin center.</span></span> <span data-ttu-id="0d110-214">레이블 지정 관리 센터에서 사용할 수 없는 설정에 대해 PowerShell을 사용하는 것 외에, 이제 민감도 레이블 및 민감도 레이블 정책의 만들기 및 유지 보수를 전체적으로 스크립팅할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="0d110-214">This means that in addition to using PowerShell for settings that aren't available in the labeling admin centers, you can now fully script the creation and maintenance of sensitivity labels and sensitivity label policies.</span></span> 

<span data-ttu-id="0d110-215">지원되는 매개 변수와 값에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-215">See the following documentation for supported parameters and values:</span></span>

- [<span data-ttu-id="0d110-216">New-Label</span><span class="sxs-lookup"><span data-stu-id="0d110-216">New-Label</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-label)
- [<span data-ttu-id="0d110-217">New-LabelPolicy</span><span class="sxs-lookup"><span data-stu-id="0d110-217">New-LabelPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-labelpolicy)
- [<span data-ttu-id="0d110-218">Set-Label</span><span class="sxs-lookup"><span data-stu-id="0d110-218">Set-Label</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-label)
- [<span data-ttu-id="0d110-219">Set-LabelPolicy</span><span class="sxs-lookup"><span data-stu-id="0d110-219">Set-LabelPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-labelpolicy)

<span data-ttu-id="0d110-220">민감도 레이블 또는 민감도 레이블 정책의 삭제를 스크립팅해야 하는 경우에는 [Remove-Label](https://docs.microsoft.com/powershell/module/exchange/remove-label) 및 [Remove-LabelPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-labelpolicy)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-220">You can also use [Remove-Label](https://docs.microsoft.com/powershell/module/exchange/remove-label) and [Remove-LabelPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-labelpolicy) if you need to script the deletion of sensitivity labels or sensitivity label policies.</span></span> <span data-ttu-id="0d110-221">그러나 민감도 레이블을 삭제하기 전에 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-221">However, before you delete sensitivity labels, make sure you read the following section.</span></span>

## <a name="removing-and-deleting-labels"></a><span data-ttu-id="0d110-222">레이블 제거 및 삭제</span><span class="sxs-lookup"><span data-stu-id="0d110-222">Removing and deleting labels</span></span>

<span data-ttu-id="0d110-223">프로덕션 환경에서는 레이블 정책에서 민감도 레이블을 제거하거나 민감도 레이블을 삭제하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-223">In a production environment, it's unlikely that you will need to remove sensitivity labels from a label policy, or delete sensitivity labels.</span></span> <span data-ttu-id="0d110-224">초기 테스트 단계를 진행하는 동안에는 이 작업 중 하나를 수행해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-224">It's more likely that you might need to do one or either of these actions during an initial testing phase.</span></span> <span data-ttu-id="0d110-225">이 작업 중 하나를 수행할 때 어떻게 되는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-225">Make sure you understand what happens when you do either of these actions.</span></span>

<span data-ttu-id="0d110-226">레이블 정책에서 레이블을 제거하는 것이 삭제하는 것보다 덜 위험하며, 필요한 경우 언제든지 레이블 정책에 다시 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-226">Removing a label from a label policy is less risky than deleting it, and you can always add it back to a label policy later if needed:</span></span>

- <span data-ttu-id="0d110-227">레이블이 원래 지정된 사용자에게 더 이상 게시되지 않도록 레이블 정책에서 레이블을 제거하는 경우, 다음에 레이블 정책을 새로 고칠 때 사용자가 Office 앱에서 선택할 수 있는 레이블이 더 이상 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-227">When you remove a label from a label policy so that the label is no longer published to the originally specified users, the next time the label policy is refreshed, users no longer see that label to select in their Office app.</span></span> <span data-ttu-id="0d110-228">그러나 레이블이 문서나 전자 메일에 적용된 경우, 레이블이 해당 콘텐츠에서 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-228">However, if the label has been applied to documents or emails, the label isn't removed from that content.</span></span> <span data-ttu-id="0d110-229">레이블이 적용된 모든 암호화가 유지되고 기본 보호 템플릿은 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-229">Any encryption that was applied by the label remains and the underlying protection template remains published.</span></span> 

- <span data-ttu-id="0d110-230">제거었지만 이전에 콘텐츠에 적용한 레이블의 경우, Word, Excel 및 PowerPoint에 대한 기본 제공 레이블을 사용하는 사용자에게 상태 표시줄에 적용된 레이블 이름이 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-230">For labels that are removed but have previously been applied to content, users who are using built-in labeling for Word, Excel, and PowerPoint, still see the applied label name on the status bar.</span></span> <span data-ttu-id="0d110-231">마찬가지로, 제거되었지만 SharePoint 사이트에 적용된 레이블에는 **민감도** 열에 레이블 이름이 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-231">Similarly, labels that are removed that were applied to SharePoint sites still display the label name in the **Sensitivity** column.</span></span>

<span data-ttu-id="0d110-232">비교해보면, 레이블을 삭제하는 경우:</span><span class="sxs-lookup"><span data-stu-id="0d110-232">In comparison, when you delete a label:</span></span>

- <span data-ttu-id="0d110-233">레이블에서 암호화를 적용한 경우, 이전에 보호된 콘텐츠가 계속 열려 있도록 기본 보호 서식 파일을 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-233">If the label applied encryption, the underlying protection template is archived so that previously protected content can still be opened.</span></span> <span data-ttu-id="0d110-234">보관된 보호 서식 파일로 인해, 새 레이블을 동일한 이름으로 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-234">Because of this archived protection template, you won't be able to create a new label with the same name.</span></span> <span data-ttu-id="0d110-235">[PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate)을 사용하여 보호 서식 파일을 삭제할 수 있는 경우에도, 보관된 서식 파일로 암호화된 콘텐츠를 열 필요가 없다고 확신이 들지 않으면 이 작업을 수행하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-235">Although it's possible to delete a protection template by using [PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate), don't do this unless you're sure you don't need to open content that was encrypted with the archived template.</span></span>

- <span data-ttu-id="0d110-236">데스크톱 앱의 경우: 메타데이터의 레이블 정보는 유지되지만, 레이블 ID와 이름 매핑은 더 이상 사용할 수 없기 때문에 사용자에게 적용된 레이블 이름이 표시되지 않으므로 사용자가 해당 콘텐츠에 레이블이 지정되지 않은 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-236">For desktop apps: The label information in the metadata remains, but because a label ID to name mapping is no longer possible, users don't see the applied label name displayed (for example, on the status bar) so users will assume the content isn't labeled.</span></span> <span data-ttu-id="0d110-237">레이블에서 암호화를 적용하는 경우, 암호화가 유지되며 콘텐츠를 여는 경우 사용자에게 지금 보관된 보호 서식 파일의 이름과 설명이 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-237">If the label applied encryption, the encryption remains and when the content is opened, uses still see the name and description of the now archived protection template.</span></span>

- <span data-ttu-id="0d110-238">웹용 Office의 경우: 사용자에게 상태 표시줄이나 **민감도** 열에 레이블 이름이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-238">For Office on the web: Users don't see the label name on status bar or in the **Sensitivity** column.</span></span> <span data-ttu-id="0d110-239">해당 레이블에 암호화가 적용되지 않은 경우에만 메타데이터의 레이블 정보가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-239">The label information in the metadata remains only if the label didn't apply encryption.</span></span> <span data-ttu-id="0d110-240">레이블에서 암호화를 적용하고 [SharePoint 및 OneDrive용 민감도 레이블](sensitivity-labels-sharepoint-onedrive-files.md)을 사용하도록 설정한 경우, 메타데이터의 레이블 정보가 제거되고 암호화가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-240">If the label applied encryption, and you've enabled [sensitivity labels for SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), the label information in the metadata is removed and the encryption is removed.</span></span> 

<span data-ttu-id="0d110-241">레이블 정책에서 민감도 레이블을 제거 하거나 민감도 레이블을 삭제하는 경우, 이 변경 사항은 모든 사용자 및 서비스에 복제 하는데 최대 1시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d110-241">When you remove a sensitivity label from a label policy, or delete a sensitivity label, these changes can take up to one hour to replicate to all users and services.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0d110-242">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0d110-242">Next steps</span></span>

<span data-ttu-id="0d110-243">특정 시나리오에 대해 민감도 레이블을 구성하고 사용하려면 다음 문서를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-243">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="0d110-244">민감도 레이블에서 암호화를 사용하여 콘텐츠 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="0d110-244">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="0d110-245">민감도 레이블을 콘텐츠에 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="0d110-245">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="0d110-246">팀, 그룹 및 사이트와 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="0d110-246">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="0d110-247">SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="0d110-247">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="0d110-248">레이블의 사용 방법을 모니터링하려면 [데이터 분류 시작](data-classification-overview.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d110-248">To monitor how your labels are being used, see [Get started with data classification](data-classification-overview.md).</span></span>

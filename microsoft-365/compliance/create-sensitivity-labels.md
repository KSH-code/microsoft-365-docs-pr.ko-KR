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
ms.openlocfilehash: d2300a54583c0b2d12de86e3dbb5f3116daf6460
ms.sourcegitcommit: 7dc36305721a92e19a6e397f906e19dcafa0073b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2020
ms.locfileid: "42101228"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="6aaf6-103">민감도 레이블과 해당 정책 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="6aaf6-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="6aaf6-104">모든 Microsoft Information Protection 솔루션(때로는 MIP로 줄여서 부름)은 [민감도 레이블](sensitivity-labels.md)을 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-104">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="6aaf6-105">이러한 레이블을 만들고 게시하려면, [Microsoft 365 준수 센터](https://compliance.microsoft.com/)와 같은 레이블 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-105">To create and publish these labels, go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="6aaf6-106">Microsoft 365 보안 센터나 Office 365 보안 및 준수 센터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-106">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="6aaf6-107">먼저 앱과 다른 서비스에서 사용할 수 있게 하고자 하는 민감도 레이블을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-107">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="6aaf6-108">예를 들어 사용자가 Office 앱에서 보고 적용하도록 하려는 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-108">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="6aaf6-109">그런 다음 구성한 레이블과 정책 설정을 포함하는 레이블 정책을 하나 이상 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-109">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="6aaf6-110">이 정책은 선택된 사용자와 위치에 대한 레이블과 설정을 게시하는 레이블 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-110">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6aaf6-111">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="6aaf6-111">Before you begin</span></span>

<span data-ttu-id="6aaf6-112">조직의 전역 관리자는 민감도 레이블의 모든 측면을 작성하고 관리할 수있는 모든 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-112">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="6aaf6-113">전역 관리자로 로그인하지 않은 경우 [민감도 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-113">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="6aaf6-114">민감도 레이블 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="6aaf6-114">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="6aaf6-115">레이블 관리 센터에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-115">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="6aaf6-116">Microsoft 365 규정 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-116">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="6aaf6-117">**솔루션** > **정보 보호**</span><span class="sxs-lookup"><span data-stu-id="6aaf6-117">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="6aaf6-118">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-118">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="6aaf6-119">Microsoft 365 보안 센터:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-119">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="6aaf6-120">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="6aaf6-120">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="6aaf6-121">Office 365 보안 및 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-121">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="6aaf6-122">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="6aaf6-122">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="6aaf6-123">**레이블** 탭에서 **+레이블 만들기**를 선택하 여 **새 민감도 레이블** 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-123">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="6aaf6-124">레이블 설정에 대한 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-124">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="6aaf6-125">레이블 설정에 대한 자세한 정보는 개요 정보에서 [할 수 있는 민감도 레이블](sensitivity-labels.md#what-sensitivity-labels-can-do)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-125">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="6aaf6-126">이 단계를 반복하여 레이블을 더 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-126">Repeat these steps to create more labels.</span></span> <span data-ttu-id="6aaf6-127">그러나 하위 레이블을 만들고자 하는 경우 먼저 상위 레이블을 선택하고 **추가 작업**에서 **...** 을 선택한 다음 **하위 레이블 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-127">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="6aaf6-128">필요한 레이블을 모두 만든 경우 해당 주문을 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-128">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="6aaf6-129">레이블 순서를 변경하려면 **추가 작업**에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-129">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="6aaf6-130">자세한 내용은 개요 정보에서 [레이블 우선 순위(순서가 중요함)](sensitivity-labels.md#label-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-130">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="6aaf6-131">기존 레이블을 편집하려면 레이블을 선택하고 **레이블 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-131">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="6aaf6-132">이렇게 하면 3단계에서 모든 레이블 설정을 변경할 수 있는 **민감도 레이블 편집** 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-132">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="6aaf6-133">레이블 정책을 사용하여 이미 게시된 레이블을 편집하면 마법사를 완료할 때 추가 단계가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-133">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="6aaf6-134">예를 들어 동일한 사용자가 변경 내용을 사용할 수 있도록 새 레이블 정책에 추가하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-134">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="6aaf6-135">그러나 변경 사항이 사용자 및 서비스에 복제되려면 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-135">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="6aaf6-136">레이블을 게시할 때까지 레이블을 앱이나 서비스에서 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-136">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="6aaf6-137">레이블을 게시하려면 [레이블 정책에 추가](#publish-sensitivity-labels-by-creating-a-label-policy)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-137">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6aaf6-138">이 **레이블** 탭에서, 새 레이블 정책을 만들어야 하는 경우가 아니면 **레이블 게시** 탭 (또는 레이블을 편집할 때 **레이블 게시** 단추)을 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-138">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="6aaf6-139">다른 레이블이나 다른 정책 설정이 필요한 경우에만 여러 레이블 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-139">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="6aaf6-140">레이블 정책을 최대한 적게 보유하는 것이 좋습니다. 조직에 대한 레이블 정책을 하나만 보유하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-140">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="6aaf6-141">Office 365 보안 및 준수 센터 PowerShell를 이용한 추가 레이블 설정</span><span class="sxs-lookup"><span data-stu-id="6aaf6-141">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="6aaf6-142">추가 레이블 설정은 [Office 365 보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)에서 [레이블 설정](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-142">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="6aaf6-143">사용자가 로컬 언어로 레이블 이름과 도구 설명을 확인하기 위한 다국적 배포에는 *LocaleSettings* 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-143">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="6aaf6-144">예제 구성에 대한 자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-144">See the following section for an example configuration.</span></span> 

<span data-ttu-id="6aaf6-145">이 cmdlet을 사용하여 Azure Information Protection 통합 레이블 클라이언트에 대한 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-145">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="6aaf6-146">이 고급 설정에는 레이블 색상 설정이 포함되며, 레이블이 적용된 경우에는 사용자 지정 속성 적용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-146">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="6aaf6-147">전체 목록을 확인하려면 [레이블 정책에 대해 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-147">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="6aaf6-148">다양한 언어로 민감도 레이블을 구성하는 예제 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-148">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="6aaf6-149">다음 예제는 도구 설명에 대한 개체 틀 텍스트를 사용하 여 "Public" 이라는 레이블의 PowerShell 구성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-149">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="6aaf6-150">이 예제에서는 프랑스어, 이탈리아어, 독일어에 대한 레이블 이름 및 도구 설명 텍스트가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-150">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="6aaf6-151">이 구성의 결과로 해당 표시 언어를 사용하는 Office 앱을 사용하는 사용자는 동일한 언어로 레이블 이름과 도구 설명을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-151">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="6aaf6-152">마찬가지로, 파일 탐색기에서 파일을 레이블 지정하기 위해 Azure Information Protection 통합 레이블 클라이언트를 설치한 경우 해당 언어 버전의 Windows를 사용하는 사용자는 레이블 지정을 위해 마우스 오른쪽 단추 클릭 작업을 할 때 로컬 언어로 레이블 이름과 도구 설명을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-152">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="6aaf6-153">지원해야 하는 언어의 경우에는 Office [언어 식별자](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers)(언어 태그라고도 함)를 사용하여 레이블 이름 및 도구 설명에 대한 고유한 번역을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-153">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="6aaf6-154">PowerShell에서 명령을 실행하기 전에 먼저 [Office 365 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-154">Before you run the commands in PowerShell, you must first [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


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
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress)
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="6aaf6-155">레이블 정책을 만들어 민감도 레이블 게시</span><span class="sxs-lookup"><span data-stu-id="6aaf6-155">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="6aaf6-156">레이블 관리 센터에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-156">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="6aaf6-157">Microsoft 365 규정 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-157">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="6aaf6-158">**솔루션** > **정보 보호**</span><span class="sxs-lookup"><span data-stu-id="6aaf6-158">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="6aaf6-159">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-159">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="6aaf6-160">Microsoft 365 보안 센터:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-160">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="6aaf6-161">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="6aaf6-161">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="6aaf6-162">Office 365 보안 및 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-162">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="6aaf6-163">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="6aaf6-163">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="6aaf6-164">**레이블 정책** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-164">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="6aaf6-165">**레이블 게시**를 선택하여 **정책 만들기 마법사**를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-165">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="6aaf6-166">**민감도 레이블을 선택하여 게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-166">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="6aaf6-167">앱과 서비스에서 사용할 수 있도록 설정할 레이블을 선택한 다음 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-167">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="6aaf6-168">선택한 레이블을 검토하 고 내용을 변경하려면 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-168">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="6aaf6-169">그렇지 않으면 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-169">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="6aaf6-170">화면에 나타나는 메시지에 따라 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-170">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="6aaf6-171">설정에 대한 자세한 정보는 개요 정보에서 [할 수 있는 레이블 정책](sensitivity-labels.md#what-label-policies-can-do)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-171">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="6aaf6-172">여러 사용자나 위치에 대해 서로 다른 정책 설정이 필요한 경우에는 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-172">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="6aaf6-173">예를 들어 사용자 그룹에 대한 추가 레이블이나 사용자 하위 집합에 대해 다른 기본 레이블을 원하는 경우가 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-173">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="6aaf6-174">사용자 또는 위치에 충돌이 발생할 수 있는 레이블 정책을 여러 개 만드는 경우에는 정책 순서를 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-174">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="6aaf6-175">레이블 정책 순서를 변경하려면 **추가 작업**에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-175">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="6aaf6-176">자세한 내용은 개요 정보에서 [레이블 정책 우선 순위(순서가 중요함)](sensitivity-labels.md#label-policy-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-176">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="6aaf6-177">마법사를 완료하면 자동으로 레이블 정책이 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-177">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="6aaf6-178">게시된 정책을 변경하려면 정책을 편집하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-178">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="6aaf6-179">사용자가 선택할 특정 게시 또는 재게시 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-179">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="6aaf6-180">기존 레이블 정책을 편집하려면 레이블을 선택하고 **정책 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-180">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="6aaf6-181">이렇게 하면 포함할 레이블과 레이블 설정을 편집할 수 있는 **정책 만들기** 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-181">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="6aaf6-182">마법사를 완료하면 변경 내용이 선택된 사용자 및 서비스로 자동 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-182">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="6aaf6-183">일반적으로 사용자에게 몇 시간 내 Office 앱의 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-183">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="6aaf6-184">그러나 레이블 정책 및 변경 사항이 모든 사용자 및 서비스에 복제될 때까지 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-184">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="6aaf6-185">Office 365 보안 및 준수 센터 PowerShell를 이용한 추가 레이블 정책 설정</span><span class="sxs-lookup"><span data-stu-id="6aaf6-185">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="6aaf6-186">추가 레이블 정책 설정은 [Office 365 보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)에서 [레이블 설정](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-186">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="6aaf6-187">이 cmdlet을 사용하여 Azure Information Protection 통합 레이블 클라이언트에 대한 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-187">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="6aaf6-188">이 고급 설정에는 Outlook에 다른 기본 레이블 설정이 포함되어 있으며, Outlook에서 보내는 전자 메일에 대해 경고, 정렬 또는 차단하는 팝업 메시지를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-188">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="6aaf6-189">전체 목록을 확인하려면 [레이블에 대해 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-189">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="6aaf6-190">이 cmdlet을 사용하여 레이블 정책에서 레이블을 추가하거나 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-190">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="6aaf6-191">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6aaf6-191">Next steps</span></span>

<span data-ttu-id="6aaf6-192">특정 시나리오에 대해 민감도 레이블을 구성하고 사용하려면 다음 문서를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-192">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="6aaf6-193">민감도 레이블에서 암호화를 사용하여 콘텐츠 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="6aaf6-193">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="6aaf6-194">민감도 레이블을 콘텐츠에 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="6aaf6-194">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="6aaf6-195">팀, 그룹 및 사이트와 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="6aaf6-195">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="6aaf6-196">SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="6aaf6-196">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="6aaf6-197">레이블이 사용되는 방식을 모니터링 하려면 [레이블 분석을 통한 레이블 사용량 보기](label-analytics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-197">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>

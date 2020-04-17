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
ms.openlocfilehash: 196efe65eda1265d6f2c0578d1f444709dadb26c
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516823"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="c8a9c-103">민감도 레이블과 해당 정책 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="c8a9c-103">Create and configure sensitivity labels and their policies</span></span>

><span data-ttu-id="c8a9c-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="c8a9c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c8a9c-105">모든 Microsoft Information Protection 솔루션(때로는 MIP로 줄여서 부름)은 [민감도 레이블](sensitivity-labels.md)을 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-105">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="c8a9c-106">이러한 레이블을 만들고 게시하려면, [Microsoft 365 준수 센터](https://compliance.microsoft.com/)와 같은 레이블 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-106">To create and publish these labels, go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="c8a9c-107">Microsoft 365 보안 센터나 Office 365 보안 및 준수 센터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-107">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="c8a9c-108">먼저 앱과 다른 서비스에서 사용할 수 있게 하고자 하는 민감도 레이블을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-108">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="c8a9c-109">예를 들어 사용자가 Office 앱에서 보고 적용하도록 하려는 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-109">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="c8a9c-110">그런 다음 구성한 레이블과 정책 설정을 포함하는 레이블 정책을 하나 이상 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-110">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="c8a9c-111">이 정책은 선택된 사용자와 위치에 대한 레이블과 설정을 게시하는 레이블 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-111">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c8a9c-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c8a9c-112">Before you begin</span></span>

<span data-ttu-id="c8a9c-113">조직의 전역 관리자는 민감도 레이블의 모든 측면을 작성하고 관리할 수있는 모든 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-113">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="c8a9c-114">전역 관리자로 로그인하지 않은 경우 [민감도 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-114">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="c8a9c-115">민감도 레이블 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="c8a9c-115">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="c8a9c-116">레이블 관리 센터에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-116">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="c8a9c-117">Microsoft 365 규정 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="c8a9c-117">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="c8a9c-118">**솔루션** > **정보 보호**</span><span class="sxs-lookup"><span data-stu-id="c8a9c-118">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="c8a9c-119">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-119">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="c8a9c-120">Microsoft 365 보안 센터:</span><span class="sxs-lookup"><span data-stu-id="c8a9c-120">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="c8a9c-121">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="c8a9c-121">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="c8a9c-122">Office 365 보안 및 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="c8a9c-122">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="c8a9c-123">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="c8a9c-123">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="c8a9c-124">**레이블** 탭에서 **+레이블 만들기**를 선택하 여 **새 민감도 레이블** 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-124">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="c8a9c-125">레이블 설정에 대한 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-125">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="c8a9c-126">레이블 설정에 대한 자세한 정보는 개요 정보에서 [할 수 있는 민감도 레이블](sensitivity-labels.md#what-sensitivity-labels-can-do)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-126">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="c8a9c-127">이 단계를 반복하여 레이블을 더 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-127">Repeat these steps to create more labels.</span></span> <span data-ttu-id="c8a9c-128">그러나 하위 레이블을 만들고자 하는 경우 먼저 상위 레이블을 선택하고 **추가 작업**에서 **...** 을 선택한 다음 **하위 레이블 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-128">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="c8a9c-129">필요한 레이블을 모두 만든 경우 해당 주문을 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-129">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="c8a9c-130">레이블 순서를 변경하려면 **추가 작업**에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-130">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="c8a9c-131">자세한 내용은 개요 정보에서 [레이블 우선 순위(순서가 중요함)](sensitivity-labels.md#label-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-131">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="c8a9c-132">기존 레이블을 편집하려면 레이블을 선택하고 **레이블 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-132">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="c8a9c-133">이렇게 하면 3단계에서 모든 레이블 설정을 변경할 수 있는 **민감도 레이블 편집** 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-133">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="c8a9c-134">레이블 정책을 사용하여 이미 게시된 레이블을 편집하면 마법사를 완료할 때 추가 단계가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-134">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="c8a9c-135">예를 들어 동일한 사용자가 변경 내용을 사용할 수 있도록 새 레이블 정책에 추가하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-135">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="c8a9c-136">그러나 변경 사항이 사용자 및 서비스에 복제되려면 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-136">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="c8a9c-137">레이블을 게시할 때까지 레이블을 앱이나 서비스에서 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-137">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="c8a9c-138">레이블을 게시하려면 [레이블 정책에 추가](#publish-sensitivity-labels-by-creating-a-label-policy)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-138">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8a9c-139">이 **레이블** 탭에서, 새 레이블 정책을 만들어야 하는 경우가 아니면 **레이블 게시** 탭 (또는 레이블을 편집할 때 **레이블 게시** 단추)을 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-139">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="c8a9c-140">다른 레이블이나 다른 정책 설정이 필요한 경우에만 여러 레이블 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-140">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="c8a9c-141">레이블 정책을 최대한 적게 보유하는 것이 좋습니다. 조직에 대한 레이블 정책을 하나만 보유하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-141">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="c8a9c-142">Office 365 보안 및 준수 센터 PowerShell를 이용한 추가 레이블 설정</span><span class="sxs-lookup"><span data-stu-id="c8a9c-142">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="c8a9c-143">추가 레이블 설정은 [Office 365 보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)에서 [레이블 설정](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-143">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="c8a9c-144">사용자가 로컬 언어로 레이블 이름과 도구 설명을 확인하기 위한 다국적 배포에는 *LocaleSettings* 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-144">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="c8a9c-145">예제 구성에 대한 자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-145">See the following section for an example configuration.</span></span> 

<span data-ttu-id="c8a9c-146">이 cmdlet을 사용하여 Azure Information Protection 통합 레이블 클라이언트에 대한 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-146">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="c8a9c-147">이 고급 설정에는 레이블 색상 설정이 포함되며, 레이블이 적용된 경우에는 사용자 지정 속성 적용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-147">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="c8a9c-148">전체 목록을 확인하려면 [레이블 정책에 대해 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-148">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="c8a9c-149">다양한 언어로 민감도 레이블을 구성하는 예제 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-149">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="c8a9c-150">다음 예제는 도구 설명에 대한 개체 틀 텍스트를 사용하 여 "Public" 이라는 레이블의 PowerShell 구성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-150">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="c8a9c-151">이 예제에서는 프랑스어, 이탈리아어, 독일어에 대한 레이블 이름 및 도구 설명 텍스트가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-151">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="c8a9c-152">이 구성의 결과로 해당 표시 언어를 사용하는 Office 앱을 사용하는 사용자는 동일한 언어로 레이블 이름과 도구 설명을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-152">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="c8a9c-153">마찬가지로, 파일 탐색기에서 파일을 레이블 지정하기 위해 Azure Information Protection 통합 레이블 클라이언트를 설치한 경우 해당 언어 버전의 Windows를 사용하는 사용자는 레이블 지정을 위해 마우스 오른쪽 단추 클릭 작업을 할 때 로컬 언어로 레이블 이름과 도구 설명을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-153">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="c8a9c-154">지원해야 하는 언어의 경우에는 Office [언어 식별자](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers)(언어 태그라고도 함)를 사용하여 레이블 이름 및 도구 설명에 대한 고유한 번역을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-154">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="c8a9c-155">PowerShell에서 명령을 실행하기 전에 먼저 [Office 365 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-155">Before you run the commands in PowerShell, you must first [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


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

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="c8a9c-156">레이블 정책을 만들어 민감도 레이블 게시</span><span class="sxs-lookup"><span data-stu-id="c8a9c-156">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="c8a9c-157">레이블 관리 센터에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-157">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="c8a9c-158">Microsoft 365 규정 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="c8a9c-158">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="c8a9c-159">**솔루션** > **정보 보호**</span><span class="sxs-lookup"><span data-stu-id="c8a9c-159">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="c8a9c-160">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-160">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="c8a9c-161">Microsoft 365 보안 센터:</span><span class="sxs-lookup"><span data-stu-id="c8a9c-161">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="c8a9c-162">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="c8a9c-162">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="c8a9c-163">Office 365 보안 및 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="c8a9c-163">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="c8a9c-164">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="c8a9c-164">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="c8a9c-165">**레이블 정책** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-165">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="c8a9c-166">**레이블 게시**를 선택하여 **정책 만들기 마법사**를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-166">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="c8a9c-167">**민감도 레이블을 선택하여 게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-167">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="c8a9c-168">앱과 서비스에서 사용할 수 있도록 설정할 레이블을 선택한 다음 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-168">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>
    
    <span data-ttu-id="c8a9c-169">하위 레이블을 선택한 경우 해당 상위 레이블도 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-169">If you select a sublabel, make sure you also select its parent label.</span></span>
    
5. <span data-ttu-id="c8a9c-170">선택한 레이블을 검토하 고 내용을 변경하려면 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-170">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="c8a9c-171">그렇지 않으면 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-171">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="c8a9c-172">화면에 나타나는 메시지에 따라 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-172">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="c8a9c-173">설정에 대한 자세한 정보는 개요 정보에서 [할 수 있는 레이블 정책](sensitivity-labels.md#what-label-policies-can-do)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-173">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="c8a9c-174">여러 사용자나 위치에 대해 서로 다른 정책 설정이 필요한 경우에는 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-174">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="c8a9c-175">예를 들어 사용자 그룹에 대한 추가 레이블이나 사용자 하위 집합에 대해 다른 기본 레이블을 원하는 경우가 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-175">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="c8a9c-176">사용자 또는 위치에 충돌이 발생할 수 있는 레이블 정책을 여러 개 만드는 경우에는 정책 순서를 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-176">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="c8a9c-177">레이블 정책 순서를 변경하려면 **추가 작업**에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-177">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="c8a9c-178">자세한 내용은 개요 정보에서 [레이블 정책 우선 순위(순서가 중요함)](sensitivity-labels.md#label-policy-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-178">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="c8a9c-179">마법사를 완료하면 자동으로 레이블 정책이 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-179">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="c8a9c-180">게시된 정책을 변경하려면 정책을 편집하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-180">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="c8a9c-181">사용자가 선택할 특정 게시 또는 재게시 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-181">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="c8a9c-182">기존 레이블 정책을 편집하려면 레이블을 선택하고 **정책 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-182">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="c8a9c-183">이렇게 하면 포함할 레이블과 레이블 설정을 편집할 수 있는 **정책 만들기** 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-183">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="c8a9c-184">마법사를 완료하면 변경 내용이 선택된 사용자 및 서비스로 자동 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-184">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="c8a9c-185">일반적으로 사용자에게 몇 시간 내 Office 앱의 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-185">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="c8a9c-186">그러나 레이블 정책 및 변경 사항이 모든 사용자 및 서비스에 복제될 때까지 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-186">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="c8a9c-187">Office 365 보안 및 준수 센터 PowerShell를 이용한 추가 레이블 정책 설정</span><span class="sxs-lookup"><span data-stu-id="c8a9c-187">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="c8a9c-188">추가 레이블 정책 설정은 [Office 365 보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)에서 [레이블 설정](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-188">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="c8a9c-189">이 cmdlet을 사용하여 Azure Information Protection 통합 레이블 클라이언트에 대한 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-189">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="c8a9c-190">이 고급 설정에는 Outlook에 다른 기본 레이블 설정이 포함되어 있으며, Outlook에서 보내는 전자 메일에 대해 경고, 정렬 또는 차단하는 팝업 메시지를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-190">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="c8a9c-191">전체 목록을 확인하려면 [레이블에 대해 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-191">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="c8a9c-192">이 cmdlet을 사용하여 레이블 정책에서 레이블을 추가하거나 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-192">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>

## <a name="removing-and-deleting-labels"></a><span data-ttu-id="c8a9c-193">레이블 제거 및 삭제</span><span class="sxs-lookup"><span data-stu-id="c8a9c-193">Removing and deleting labels</span></span>

<span data-ttu-id="c8a9c-194">프로덕션 환경에서는 레이블 정책에서 민감도 레이블을 제거하거나 민감도 레이블을 삭제하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-194">In a production environment, it's unlikely that you will need to remove sensitivity labels from a label policy, or delete sensitivity labels.</span></span> <span data-ttu-id="c8a9c-195">초기 테스트 단계를 진행하는 동안에는 이 작업 중 하나를 수행해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-195">It's more likely that you might need to do one or either of these actions during an initial testing phase.</span></span> <span data-ttu-id="c8a9c-196">이 작업 중 하나를 수행할 때 어떻게 되는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-196">Make sure you understand what happens when you do either of these actions.</span></span>

<span data-ttu-id="c8a9c-197">레이블 정책에서 레이블을 제거하는 것이 삭제하는 것보다 덜 위험하며, 필요한 경우 언제든지 레이블 정책에 다시 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-197">Removing a label from a label policy is less risky than deleting it, and you can always add it back to a label policy later if needed:</span></span>

- <span data-ttu-id="c8a9c-198">레이블이 원래 지정된 사용자에게 더 이상 게시되지 않도록 레이블 정책에서 레이블을 제거하는 경우, 다음에 레이블 정책을 새로 고칠 때 사용자가 Office 앱에서 선택할 수 있는 레이블이 더 이상 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-198">When you remove a label from a label policy so that the label is no longer published to the originally specified users, the next time the label policy is refreshed, users no longer see that label to select in their Office app.</span></span> <span data-ttu-id="c8a9c-199">그러나 레이블이 문서나 전자 메일에 적용된 경우, 레이블이 해당 콘텐츠에서 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-199">However, if the label has been applied to documents or emails, the label isn't removed from that content.</span></span> <span data-ttu-id="c8a9c-200">레이블이 적용된 모든 암호화가 유지되고 기본 보호 템플릿은 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-200">Any encryption that was applied by the label remains and the underlying protection template remains published.</span></span> 

- <span data-ttu-id="c8a9c-201">제거었지만 이전에 콘텐츠에 적용한 레이블의 경우, Word, Excel 및 PowerPoint에 대한 기본 제공 레이블을 사용하는 사용자에게 상태 표시줄에 적용된 레이블 이름이 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-201">For labels that are removed but have previously been applied to content, users who are using built-in labeling for Word, Excel, and PowerPoint, still see the applied label name on the status bar.</span></span> <span data-ttu-id="c8a9c-202">마찬가지로, 제거되었지만 SharePoint 사이트에 적용된 레이블에는 **민감도** 열에 레이블 이름이 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-202">Similarly, labels that are removed that were applied to SharePoint sites still display the label name in the **Sensitivity** column.</span></span>

<span data-ttu-id="c8a9c-203">비교해보면, 레이블을 삭제하는 경우:</span><span class="sxs-lookup"><span data-stu-id="c8a9c-203">In comparison, when you delete a label:</span></span>

- <span data-ttu-id="c8a9c-204">레이블에서 암호화를 적용한 경우, 이전에 보호된 콘텐츠가 계속 열려 있도록 기본 보호 서식 파일을 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-204">If the label applied encryption, the underlying protection template is archived so that previously protected content can still be opened.</span></span> <span data-ttu-id="c8a9c-205">보관된 보호 서식 파일로 인해, 새 레이블을 동일한 이름으로 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-205">Because of this archived protection template, you won't be able to create a new label with the same name.</span></span> <span data-ttu-id="c8a9c-206">[PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate)을 사용하여 보호 서식 파일을 삭제할 수 있는 경우에도, 보관된 서식 파일로 암호화된 콘텐츠를 열 필요가 없다고 확신이 들지 않으면 이 작업을 수행하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-206">Although it's possible to delete a protection template by using [PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate), don't do this unless you're sure you don't need to open content that was encrypted with the archived template.</span></span>

- <span data-ttu-id="c8a9c-207">데스크톱 앱의 경우: 메타데이터의 레이블 정보는 유지되지만, 레이블 ID와 이름 매핑은 더 이상 사용할 수 없기 때문에 사용자에게 적용된 레이블 이름이 표시되지 않으므로 사용자가 해당 콘텐츠에 레이블이 지정되지 않은 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-207">For desktop apps: The label information in the metadata remains, but because a label ID to name mapping is no longer possible, users don't see the applied label name displayed (for example, on the status bar) so users will assume the content isn't labeled.</span></span> <span data-ttu-id="c8a9c-208">레이블에서 암호화를 적용하는 경우, 암호화가 유지되며 콘텐츠를 여는 경우 사용자에게 지금 보관된 보호 서식 파일의 이름과 설명이 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-208">If the label applied encryption, the encryption remains and when the content is opened, uses still see the name and description of the now archived protection template.</span></span>

- <span data-ttu-id="c8a9c-209">웹용 Office의 경우: 사용자에게 상태 표시줄이나 **민감도** 열에 레이블 이름이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-209">For Office on the web: Users don't see the label name on status bar or in the **Sensitivity** column.</span></span> <span data-ttu-id="c8a9c-210">해당 레이블에 암호화가 적용되지 않은 경우에만 메타데이터의 레이블 정보가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-210">The label information in the metadata remains only if the label didn't apply encryption.</span></span> <span data-ttu-id="c8a9c-211">레이블에서 암호화를 적용하고 [SharePoint 및 Onedrive에 민감도 레이블](sensitivity-labels-sharepoint-onedrive-files.md)을 사용하도록 설정한 경우, 메타데이터의 레이블 정보가 제거되고 암호화가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-211">If the label applied encryption, and you've enabled [sensitivity labels for SharePoint and Onedrive](sensitivity-labels-sharepoint-onedrive-files.md), the label information in the metadata is removed and the encryption is removed.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="c8a9c-212">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c8a9c-212">Next steps</span></span>

<span data-ttu-id="c8a9c-213">특정 시나리오에 대해 민감도 레이블을 구성하고 사용하려면 다음 문서를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-213">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="c8a9c-214">민감도 레이블에서 암호화를 사용하여 콘텐츠 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="c8a9c-214">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="c8a9c-215">민감도 레이블을 콘텐츠에 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="c8a9c-215">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="c8a9c-216">팀, 그룹 및 사이트와 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="c8a9c-216">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="c8a9c-217">SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="c8a9c-217">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="c8a9c-218">레이블이 사용되는 방식을 모니터링 하려면 [레이블 분석을 통한 레이블 사용량 보기](label-analytics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8a9c-218">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>

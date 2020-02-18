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
description: 조직의 문서 및 전자 메일을 분류하고 보호하는 데 필요한 민감도 레이블을 생성, 구성 및 게시하기 위한 지침입니다.
ms.openlocfilehash: 8018c18e976d0e6f9904923471bb07c8bb3cbc40
ms.sourcegitcommit: 7d07e7ec84390a8f05034d3639fa5db912809585
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42091301"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="83082-103">민감도 레이블과 해당 정책 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="83082-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="83082-104">[우편물 레이블을 만들고 게시하려면](sensitivity-labels.md), [Microsoft 365 준수 센터](https://compliance.microsoft.com/)와 같은 레이블 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-104">To create and publish your [sensitivity labels](sensitivity-labels.md), go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="83082-105">Microsoft 365 보안 센터나 Office 365 보안 및 준수 센터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-105">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="83082-106">먼저 Office 앱과 서비스에서 사용할 수 있게 하고자 하는 민감도 레이블을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-106">First, create and configure the sensitivity labels that you want to make available in Office apps and for services.</span></span> <span data-ttu-id="83082-107">그런 다음 구성한 레이블과 정책 설정을 포함하는 레이블 정책을 하나 이상 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83082-107">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="83082-108">이 정책은 선택된 사용자와 위치에 대한 레이블과 설정을 게시하는 레이블 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="83082-108">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a><span data-ttu-id="83082-109">민감도 레이블을 만들고 관리하는 데 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="83082-109">Permissions required to create and manage sensitivity labels</span></span>

<span data-ttu-id="83082-110">민감도 레이블을 생성할 규정 준수 팀의 구성원은 Microsoft 365 규정 준수 센터, Microsoft 365 보안 센터 또는 Office 365 보안 및 규정 준수 센터에 대한 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-110">Members of your compliance team who will create sensitivity labels need permissions to the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span> 

<span data-ttu-id="83082-111">기본적으로 테넌트 관리자는 이러한 관리 센터에 액세스할 수 있으며, 규정 준수 관리자와 기타 사용자에게 테넌트 관리자의 모든 사용 권한을 부여하지 않고도 액세스를 가능하게 할 수 있습니다. 이러한 위임된 제한적 관리 액세스를 부여하려면 이들 관리 센터 중 하나의 **사용 권한** 페이지로 이동한 다음 **규정 준수 데이터 관리자**, **규정 준수 관리자** 또는 **보안 관리자** 역할 그룹에 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-111">By default, your tenant admin has access to these admin centers and can give compliance officers and other people access, without giving them all of the permissions of a tenant admin. For this delegated limited admin access, go to the **Permissions** page of one of these admin centers, and then add members to the **Compliance Data Administrator**, **Compliance Administrator** or **Security Administrator** role group.</span></span>

<span data-ttu-id="83082-112">역할을 사용하는 대신 새 역할 그룹을 만들고 **민감도 레이블 관리자** 또는 **조직 구성**을 역할을 이 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-112">Alternatively to using roles, you can create a new role group and add either **Sensitivity Label Administrator** or **Organization Configuration** roles to this group.</span></span> <span data-ttu-id="83082-113">[사용자에게 Office 365 보안 및 준수 센터에 대한 액세스 권한 부여](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83082-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).</span></span>

<span data-ttu-id="83082-114">이러한 사용 권한은 민감도 레이블과 해당 레이블 정책을 만들고 구성하는 데만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-114">These permissions are required only to create and configure sensitivity labels and their label policies.</span></span> <span data-ttu-id="83082-115">앱이나 서비스에서 레이블을 적용하는 것은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-115">They are not required to apply the labels in apps or services.</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="83082-116">민감도 레이블 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="83082-116">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="83082-117">레이블 관리 센터에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-117">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="83082-118">Microsoft 365 규정 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="83082-118">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="83082-119">**솔루션** > **정보 보호**</span><span class="sxs-lookup"><span data-stu-id="83082-119">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="83082-120">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-120">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="83082-121">Microsoft 365 보안 센터:</span><span class="sxs-lookup"><span data-stu-id="83082-121">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="83082-122">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="83082-122">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="83082-123">Office 365 보안 및 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="83082-123">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="83082-124">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="83082-124">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="83082-125">**레이블** 탭에서 **+레이블 만들기**를 선택하 여 **새 민감도 레이블** 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-125">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="83082-126">레이블 설정에 대한 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="83082-126">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="83082-127">레이블 설정에 대한 자세한 정보는 개요 정보에서 [할 수 있는 민감도 레이블](sensitivity-labels.md#what-sensitivity-labels-can-do)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83082-127">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="83082-128">이 단계를 반복하여 레이블을 더 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83082-128">Repeat these steps to create more labels.</span></span> <span data-ttu-id="83082-129">그러나 하위 레이블을 만들고자 하는 경우 먼저 상위 레이블을 선택하고 **추가 작업**에서 **...** 을 선택한 다음 **하위 레이블 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-129">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="83082-130">필요한 레이블을 모두 만든 경우 해당 주문을 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-130">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="83082-131">레이블 순서를 변경하려면 **추가 작업**에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-131">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="83082-132">자세한 내용은 개요 정보에서 [레이블 우선 순위(순서가 중요함)](sensitivity-labels.md#label-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83082-132">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="83082-133">기존 레이블을 편집하려면 레이블을 선택하고 **레이블 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-133">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="83082-134">이렇게 하면 3단계에서 모든 레이블 설정을 변경할 수 있는 **민감도 레이블 편집** 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-134">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="83082-135">레이블 정책을 사용하여 이미 게시된 레이블을 편집하면 마법사를 완료할 때 추가 단계가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-135">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="83082-136">예를 들어 동일한 사용자가 변경 내용을 사용할 수 있도록 새 레이블 정책에 추가하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-136">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="83082-137">그러나 변경 사항이 사용자 및 서비스에 복제되려면 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-137">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="83082-138">레이블을 게시할 때까지 레이블을 앱이나 서비스에서 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-138">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="83082-139">레이블을 게시하려면 [레이블 정책에 추가](#publish-sensitivity-labels-by-creating-a-label-policy)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-139">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83082-140">이 **레이블** 탭에서, 새 레이블 정책을 만들어야 하는 경우가 아니면 **레이블 게시** 탭 (또는 레이블을 편집할 때 **레이블 게시** 단추)을 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="83082-140">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="83082-141">다른 레이블이나 다른 정책 설정이 필요한 경우에만 여러 레이블 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-141">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="83082-142">레이블 정책을 최대한 적게 보유하는 것이 좋습니다. 조직에 대한 레이블 정책을 하나만 보유하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="83082-142">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="83082-143">Office 365 보안 및 준수 센터 PowerShell를 이용한 추가 레이블 설정</span><span class="sxs-lookup"><span data-stu-id="83082-143">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="83082-144">추가 레이블 설정은 [Office 365 보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)에서 [레이블 설정](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-144">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="83082-145">사용자가 로컬 언어로 레이블 이름과 도구 설명을 확인하기 위한 다국적 배포에는 *LocaleSettings* 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-145">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="83082-146">예제 구성에 대한 자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83082-146">See the following section for an example configuration.</span></span> 

<span data-ttu-id="83082-147">이 cmdlet을 사용하여 Azure Information Protection 통합 레이블 클라이언트에 대한 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-147">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="83082-148">이 고급 설정에는 레이블 색상 설정이 포함되며, 레이블이 적용된 경우에는 사용자 지정 속성 적용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-148">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="83082-149">전체 목록을 확인하려면 [레이블 정책에 대해 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83082-149">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="83082-150">다양한 언어로 민감도 레이블을 구성하는 예제 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="83082-150">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="83082-151">다음 예제는 도구 설명에 대한 개체 틀 텍스트를 사용하 여 "Public" 이라는 레이블의 PowerShell 구성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="83082-151">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="83082-152">이 예제에서는 프랑스어, 이탈리아어, 독일어에 대한 레이블 이름 및 도구 설명 텍스트가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-152">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="83082-153">이 구성의 결과로 해당 표시 언어를 사용하는 Office 앱을 사용하는 사용자는 동일한 언어로 레이블 이름과 도구 설명을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-153">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="83082-154">마찬가지로, 파일 탐색기에서 파일을 레이블 지정하기 위해 Azure Information Protection 통합 레이블 클라이언트를 설치한 경우 해당 언어 버전의 Windows를 사용하는 사용자는 레이블 지정을 위해 마우스 오른쪽 단추 클릭 작업을 할 때 로컬 언어로 레이블 이름과 도구 설명을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-154">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="83082-155">지원해야 하는 언어의 경우에는 Office [언어 식별자](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers)(언어 태그라고도 함)를 사용하여 레이블 이름 및 도구 설명에 대한 고유한 번역을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-155">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="83082-156">PowerShell에서 명령을 실행하기 전에 먼저 [Office 365 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-156">Before you run the commands in PowerShell, you must first [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


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

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="83082-157">레이블 정책을 만들어 민감도 레이블 게시</span><span class="sxs-lookup"><span data-stu-id="83082-157">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="83082-158">레이블 관리 센터에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-158">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="83082-159">Microsoft 365 규정 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="83082-159">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="83082-160">**솔루션** > **정보 보호**</span><span class="sxs-lookup"><span data-stu-id="83082-160">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="83082-161">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-161">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="83082-162">Microsoft 365 보안 센터:</span><span class="sxs-lookup"><span data-stu-id="83082-162">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="83082-163">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="83082-163">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="83082-164">Office 365 보안 및 준수 센터:</span><span class="sxs-lookup"><span data-stu-id="83082-164">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="83082-165">**분류** > **민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="83082-165">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="83082-166">**레이블 정책** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-166">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="83082-167">**레이블 게시**를 선택하여 **정책 만들기 마법사**를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-167">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="83082-168">**민감도 레이블을 선택하여 게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-168">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="83082-169">앱과 서비스에서 사용할 수 있도록 설정할 레이블을 선택한 다음 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-169">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="83082-170">선택한 레이블을 검토하 고 내용을 변경하려면 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-170">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="83082-171">그렇지 않으면 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-171">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="83082-172">화면에 나타나는 메시지에 따라 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-172">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="83082-173">설정에 대한 자세한 정보는 개요 정보에서 [할 수 있는 레이블 정책](sensitivity-labels.md#what-label-policies-can-do)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83082-173">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="83082-174">여러 사용자나 위치에 대해 서로 다른 정책 설정이 필요한 경우에는 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-174">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="83082-175">예를 들어 사용자 그룹에 대한 추가 레이블이나 사용자 하위 집합에 대해 다른 기본 레이블을 원하는 경우가 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-175">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="83082-176">사용자 또는 위치에 충돌이 발생할 수 있는 레이블 정책을 여러 개 만드는 경우에는 정책 순서를 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-176">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="83082-177">레이블 정책 순서를 변경하려면 **추가 작업**에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-177">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="83082-178">자세한 내용은 개요 정보에서 [레이블 정책 우선 순위(순서가 중요함)](sensitivity-labels.md#label-policy-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83082-178">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="83082-179">마법사를 완료하면 자동으로 레이블 정책이 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-179">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="83082-180">게시된 정책을 변경하려면 정책을 편집하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-180">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="83082-181">사용자가 선택할 특정 게시 또는 재게시 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-181">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="83082-182">기존 레이블 정책을 편집하려면 레이블을 선택하고 **정책 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-182">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="83082-183">이렇게 하면 포함할 레이블과 레이블 설정을 편집할 수 있는 **정책 만들기** 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-183">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="83082-184">마법사를 완료하면 변경 내용이 선택된 사용자 및 서비스로 자동 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-184">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="83082-185">일반적으로 사용자에게 몇 시간 내 Office 앱의 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-185">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="83082-186">그러나 레이블 정책 및 변경 사항이 모든 사용자 및 서비스에 복제될 때까지 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="83082-186">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="83082-187">Office 365 보안 및 준수 센터 PowerShell를 이용한 추가 레이블 정책 설정</span><span class="sxs-lookup"><span data-stu-id="83082-187">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="83082-188">추가 레이블 정책 설정은 [Office 365 보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)에서 [레이블 설정](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-188">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="83082-189">이 cmdlet을 사용하여 Azure Information Protection 통합 레이블 클라이언트에 대한 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-189">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="83082-190">이 고급 설정에는 Outlook에 다른 기본 레이블 설정이 포함되어 있으며, Outlook에서 보내는 전자 메일에 대해 경고, 정렬 또는 차단하는 팝업 메시지를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="83082-190">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="83082-191">전체 목록을 확인하려면 [레이블에 대해 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83082-191">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="83082-192">이 cmdlet을 사용하여 레이블 정책에서 레이블을 추가하거나 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83082-192">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="83082-193">다음 단계</span><span class="sxs-lookup"><span data-stu-id="83082-193">Next steps</span></span>

<span data-ttu-id="83082-194">특정 시나리오에 대해 민감도 레이블을 구성하고 사용하려면 다음 문서를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="83082-194">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="83082-195">민감도 레이블에서 암호화를 사용하여 콘텐츠 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="83082-195">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="83082-196">민감도 레이블을 콘텐츠에 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="83082-196">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="83082-197">팀, 그룹 및 사이트와 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="83082-197">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="83082-198">SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="83082-198">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="83082-199">레이블이 사용되는 방식을 모니터링 하려면 [레이블 분석을 통한 레이블 사용량 보기](label-analytics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83082-199">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>

---
title: PowerShell을 통해 Microsoft 365 라이선스 및 서비스 보기
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: PowerShell을 사용하여 Microsoft 365 조직에서 사용할 수 있는 라이선스 계획, 서비스 및 라이선스에 대한 정보를 보는 방법에 대해 설명
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924639"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="3fd39-103">PowerShell을 통해 Microsoft 365 라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="3fd39-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="3fd39-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="3fd39-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3fd39-105">모든 Microsoft 365 구독은 다음 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="3fd39-106">**라이선스 계획** 이러한 계획을 라이선스 요금제 또는 Microsoft 365 요금제라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="3fd39-107">라이선스 계획은 사용자가 사용할 수 있는 Microsoft 365 서비스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="3fd39-108">Microsoft 365 구독에 여러 라이선스 요금제가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="3fd39-109">라이선스 계획의 예로는 Microsoft 365 E3가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="3fd39-110">**서비스** 이러한 계획을 서비스 계획라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="3fd39-111">서비스는 Exchange Online 및 엔터프라이즈용 Microsoft 365 앱(이전 명명된 Office 365 ProPlus)과 같은 각 라이선싱 계획에서 사용할 수 있는 Microsoft 365 제품, 기능 및 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="3fd39-112">사용자는 다양 한 서비스에 대 한 액세스 권한을 부여 하는 다른 라이센스 계획에서 할당 된 여러 개의 라이센스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="3fd39-113">**라이선스** 각 라이선스 계획에는 구입한 라이선스 수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="3fd39-114">라이선스 계획에 정의된 Microsoft 365 서비스를 사용할 수 있도록 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="3fd39-115">모든 사용자 계정에는 Microsoft 365에 로그온하고 서비스를 사용할 수 있도록 라이선스 계획 하나에서 하나 이상의 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="3fd39-116">Microsoft 365용 PowerShell을 사용하여 Microsoft 365 조직의 사용 가능한 라이선스 계획, 라이선스 및 서비스에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="3fd39-117">다른 Office 365 구독에서 사용할 수 있는 제품, 기능 및 서비스에 대한 자세한 내용은 [Office 365 계획 옵션을 참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</span><span class="sxs-lookup"><span data-stu-id="3fd39-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3fd39-118">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="3fd39-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3fd39-119">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="3fd39-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="3fd39-120">현재 라이선스 계획 및 각 계획에 대해 사용 가능한 라이선스에 대한 요약 정보를 확인한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="3fd39-121">결과에는 다음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-121">The results contain:</span></span>
  
- <span data-ttu-id="3fd39-122">**SkuPartNumber:** 조직에 사용할 수 있는 라이선스 계획을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="3fd39-123">예를 들어 `ENTERPRISEPACK` Office 365 Enterprise E3의 라이선스 계획 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="3fd39-124">**사용:** 특정 라이선스 계획에 대해 구입한 라이선스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="3fd39-125">**ConsumedUnits:** 특정 라이선스 계획에서 사용자에게 할당한 라이선스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="3fd39-126">모든 라이선스 계획에서 사용할 수 있는 Microsoft 365 서비스에 대한 세부 정보를 확인하기 위해 먼저 라이선스 계획 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="3fd39-127">그런 다음 라이선스 계획 정보를 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="3fd39-128">그런 다음 특정 라이선스 계획에 서비스를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="3fd39-129">\<index> 은 명령 표시에서 라이선스 계획의 행 번호를 지정하는 `Get-AzureADSubscribedSku | Select SkuPartNumber` 정수(1)입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="3fd39-130">예를 들어 명령 표시가 다음과 `Get-AzureADSubscribedSku | Select SkuPartNumber` 같은 경우</span><span class="sxs-lookup"><span data-stu-id="3fd39-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="3fd39-131">그런 다음 ENTERPRISEPREMIUM 라이선스 계획에 대한 서비스를 표시하는 명령은 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="3fd39-132">ENTERPRISEPREMIUM은 세 번째 행입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="3fd39-133">따라서 인덱스 값은 (3 - 1) 또는 2입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="3fd39-134">라이선스 계획(제품 이름), 포함된 서비스 계획 및 해당 식별 이름의 전체 목록은 라이선스에 대한 제품 이름 및 서비스 계획 [식별자를 참조하세요.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="3fd39-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="3fd39-135">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="3fd39-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="3fd39-136">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="3fd39-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="3fd39-137">이 항목에서 설명하는 절차를 자동화하는 PowerShell 스크립트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="3fd39-138">특히 이 스크립트를 사용하면 Sway를 포함하여 Microsoft 365 조직의 서비스를 보고 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="3fd39-139">자세한 내용은 [PowerShell을 통해 Sway에 대한 액세스 사용 안 을 참조하세요.](disable-access-to-sway-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="3fd39-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="3fd39-140">현재 라이선스 계획 및 각 계획에 대해 사용 가능한 라이선스에 대한 요약 정보를 확인한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="3fd39-141">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="3fd39-142">이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="3fd39-143">결과에는 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="3fd39-144">**AccountSkuId:** 구문을 사용하여 조직에 사용할 수 있는 라이선스 계획을 보여 주면 `<CompanyName>:<LicensingPlan>` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="3fd39-145">_\<CompanyName>_ 는 Microsoft 365에 등록할 때 제공한 값으로, 조직에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="3fd39-146">값은 _\<LicensingPlan>_ 모든 사람에 대해 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="3fd39-147">예를 들어 값 에서 회사 이름은 입니다. 및 라이선스 계획 이름 은 `litwareinc:ENTERPRISEPACK`  `litwareinc` Office  `ENTERPRISEPACK` 365 Enterprise E3의 시스템 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="3fd39-148">**ActiveUnits:** 특정 라이선스 계획에 대해 구입한 라이선스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="3fd39-149">**WarningUnits:** 라이선스 계획에서 갱신하지 않은 라이선스 수로, 30일 유예 기간이 경과하면 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="3fd39-150">**ConsumedUnits:** 특정 라이선스 계획에서 사용자에게 할당한 라이선스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="3fd39-151">모든 라이선스 계획에서 사용할 수 있는 Microsoft 365 서비스에 대한 세부 정보를 확인한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="3fd39-152">다음 표에는 Microsoft 365 서비스 계획과 가장 일반적인 서비스에 대한 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="3fd39-153">서비스 계획 목록이 다를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="3fd39-154">**서비스 계획**</span><span class="sxs-lookup"><span data-stu-id="3fd39-154">**Service plan**</span></span>|<span data-ttu-id="3fd39-155">**설명**</span><span class="sxs-lookup"><span data-stu-id="3fd39-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="3fd39-156">Sway</span><span class="sxs-lookup"><span data-stu-id="3fd39-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="3fd39-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fd39-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="3fd39-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="3fd39-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="3fd39-159">RMS(Azure 권한 관리)</span><span class="sxs-lookup"><span data-stu-id="3fd39-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="3fd39-160">엔터프라이즈용 Microsoft 365 *앱(이전 명명된 Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="3fd39-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="3fd39-161">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="3fd39-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="3fd39-162">사무실</span><span class="sxs-lookup"><span data-stu-id="3fd39-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="3fd39-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3fd39-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="3fd39-164">Exchange Online 계획 2</span><span class="sxs-lookup"><span data-stu-id="3fd39-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="3fd39-165">라이선스 계획(제품 이름), 포함된 서비스 계획 및 해당 식별 이름의 전체 목록은 라이선스에 대한 제품 이름 및 서비스 계획 [식별자를 참조하세요.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="3fd39-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="3fd39-166">특정 라이선싱 계획에서 사용할 수 있는 Microsoft 365 서비스에 대한 세부 정보를 확인하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="3fd39-167">이 예에서는 litwareinc:ENTERPRISEPACK(Office 365 Enterprise E3) 라이선싱 계획에서 사용할 수 있는 서비스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3fd39-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="3fd39-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fd39-168">See also</span></span>

[<span data-ttu-id="3fd39-169">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="3fd39-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3fd39-170">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="3fd39-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3fd39-171">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="3fd39-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
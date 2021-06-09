---
title: 그룹을 만들 때 사용할 도메인 Microsoft 365 선택
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
recommendations: false
description: PowerShell을 사용하여 전자 메일 주소 정책을 구성하여 Microsoft 365 그룹을 만들 때 사용할 도메인을 선택하는 방법을 학습합니다.
ms.openlocfilehash: 4d620c3344f83f56afd05c00d78615331dd413ed
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583151"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="8a8f4-103">그룹을 만들 때 사용할 도메인 Microsoft 365 선택</span><span class="sxs-lookup"><span data-stu-id="8a8f4-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="8a8f4-104">일부 조직에서는 별도의 전자 메일 도메인을 사용하여 비즈니스의 여러 부분을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="8a8f4-105">사용자가 그룹을 만들 때 사용할 도메인을 지정할 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="8a8f4-106">조직에서 사용자가 비즈니스의 기본 허용 도메인이 다른 도메인에서 그룹을 만들어야 하는 경우 PowerShell을 사용하여 EAP(전자 메일 주소 정책)를 구성하여 이를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="8a8f4-107">PowerShell cmdlet을 실행하려면 먼저 조직과 대화할 수 있는 모듈을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="8a8f4-108">원격 [PowerShell을 커넥트 Exchange Online 확인을 확인 합니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8a8f4-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="8a8f4-109">예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="8a8f4-109">Example scenarios</span></span>

<span data-ttu-id="8a8f4-110">비즈니스의 주 도메인이 Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="8a8f4-111">그러나 조직의 기본 허용 도메인은 service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="8a8f4-112">즉, 그룹이 service.contoso.com(예: jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8a8f4-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="8a8f4-113">조직에 하위 도메인도 구성했다고 하자.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="8a8f4-114">이러한 도메인에 그룹도 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="8a8f4-115">students.contoso.com 위한 지원</span><span class="sxs-lookup"><span data-stu-id="8a8f4-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="8a8f4-116">faculty.contoso.com 교직원용 지원</span><span class="sxs-lookup"><span data-stu-id="8a8f4-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="8a8f4-117">다음 두 시나리오에서는 이 작업을 수행할 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="8a8f4-118">MULITPLEEAP가 있는 경우 우선 순위 순서로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="8a8f4-119">값이 1이면 우선 순위가 가장 높다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="8a8f4-120">EAP가 일치하면 더 이상 EAP가 평가되는 것이 아니며 그룹에서 스탬프가 매칭되는 주소는 일치하는 EAP에 따라 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="8a8f4-121">> 조건과 일치하는EAP가 없는 경우 조직의 기본 허용 도메인에 그룹이 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="8a8f4-122">허용 [도메인을 추가하는 Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 자세한 내용은 Manage accepted domains in Exchange Online(허용 도메인 관리)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="8a8f4-123">시나리오 1</span><span class="sxs-lookup"><span data-stu-id="8a8f4-123">Scenario 1</span></span>

<span data-ttu-id="8a8f4-124">다음 예에서는 조직의 모든 Microsoft 365 도메인에 있는 모든 groups.contoso.com 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="8a8f4-125">시나리오 2</span><span class="sxs-lookup"><span data-stu-id="8a8f4-125">Scenario 2</span></span>

<span data-ttu-id="8a8f4-126">그룹을 만들 하위 도메인을 제어하려는 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="8a8f4-127">당신은 원합니다:</span><span class="sxs-lookup"><span data-stu-id="8a8f4-127">You want:</span></span>
  
- <span data-ttu-id="8a8f4-128">그룹 도메인에서 학생(부서가 학생으로 설정된 사용자)이 students.groups.contoso.com 그룹입니다.  </span><span class="sxs-lookup"><span data-stu-id="8a8f4-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="8a8f4-129">다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="8a8f4-130">교직원이 만든 그룹(부서가 교직원 또는 전자 메일 주소로 설정된 사용자)은 **faculty.contoso.com)** 도메인에서 faculty.groups.contoso.com 합니다. </span><span class="sxs-lookup"><span data-stu-id="8a8f4-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="8a8f4-131">다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="8a8f4-132">다른 사용자가 만든 그룹은 groups.contoso.com 도메인에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="8a8f4-133">다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="8a8f4-134">전자 메일 주소 정책 변경</span><span class="sxs-lookup"><span data-stu-id="8a8f4-134">Change email address policies</span></span>

<span data-ttu-id="8a8f4-135">기존 EAP의 우선 순위 또는 전자 메일 주소 템플릿을 변경하기 위해 Set-EmailAddressPolicy cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="8a8f4-136">EAP를 변경하는 경우 이미 프로비전된 그룹에는 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="8a8f4-137">전자 메일 주소 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="8a8f4-137">Delete email address policies</span></span>

<span data-ttu-id="8a8f4-138">EAP를 삭제하려면 Remove-EmailAddressPolicy cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="8a8f4-139">EAP를 변경하는 경우 이미 프로비전된 그룹에는 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="8a8f4-140">하이브리드 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a8f4-140">Hybrid requirements</span></span>

<span data-ttu-id="8a8f4-141">조직이 하이브리드 시나리오에서 구성된 경우 Configure [Microsoft 365 groups with on-premises Exchange hybrid을](/exchange/hybrid-deployment/set-up-microsoft-365-groups) 확인하여 조직이 Microsoft 365 그룹을 만들기 위한 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="8a8f4-142">전자 메일 주소 정책 그룹 사용에 대한 추가 정보:</span><span class="sxs-lookup"><span data-stu-id="8a8f4-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="8a8f4-143">알아야 할 몇 가지 추가 사항들이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="8a8f4-144">그룹이 만들어지는 속도는 조직에 구성된EAP 수에 따라 달라 졌습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="8a8f4-145">관리자와 사용자는 그룹을 만들 때 도메인을 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="8a8f4-146">사용자 그룹은 이미 사용 가능한 표준 쿼리(사용자 속성)를 사용하여 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="8a8f4-147">지원되는 필터링할 수 있는 [속성에 대한 -RecipientFilter](/powershell/exchange/recipientfilter-properties) 매개 변수의 필터링할 수 있는 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-147">Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="8a8f4-148">그룹에 대해 EAP를 구성하지 않은 경우 그룹 만들기를 위해 기본 허용 도메인이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="8a8f4-149">허용 도메인을 제거하면 먼저 EAP를 업데이트해야 합니다. 그렇지 않으면 그룹 프로비전에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="8a8f4-150">조직에 대해 최대 100개 전자 메일 주소 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8f4-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-content"></a><span data-ttu-id="8a8f4-151">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="8a8f4-151">Related content</span></span>

<span data-ttu-id="8a8f4-152">[공동 작업 거버넌스 계획](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) 단계별(문서)</span><span class="sxs-lookup"><span data-stu-id="8a8f4-152">[Collaboration governance planning step-by-step](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (article)</span></span>

<span data-ttu-id="8a8f4-153">[공동 작업 거버넌스 계획](collaboration-governance-first.md) 만들기(문서)</span><span class="sxs-lookup"><span data-stu-id="8a8f4-153">[Create your collaboration governance plan](collaboration-governance-first.md) (article)</span></span>

<span data-ttu-id="8a8f4-154">[관리 Microsoft 365 그룹](../admin/create-groups/create-groups.md) 만들기(문서)</span><span class="sxs-lookup"><span data-stu-id="8a8f4-154">[Create an Microsoft 365 group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>
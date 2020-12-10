---
title: Microsoft 365 그룹을 만들 때 사용할 도메인 선택
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
description: PowerShell을 사용하여 전자 메일 주소 정책을 구성하여 Microsoft 365 그룹을 만들 때 사용할 도메인을 선택하는 방법을 학습합니다.
ms.openlocfilehash: 1e56268c3994b1ac822869d154be826326039bfc
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612943"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="6ef28-103">Microsoft 365 그룹을 만들 때 사용할 도메인 선택</span><span class="sxs-lookup"><span data-stu-id="6ef28-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="6ef28-104">일부 조직에서는 별도의 전자 메일 도메인을 사용하여 비즈니스의 여러 부분을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="6ef28-105">사용자가 Microsoft 365 그룹을 만들 때 사용할 도메인을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="6ef28-106">조직에서 사용자가 비즈니스의 기본 허용 도메인이 다른 도메인에 그룹을 만들어야 하는 경우 PowerShell을 사용하여 EAP(전자 메일 주소 정책)를 구성하여 이를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="6ef28-107">PowerShell cmdlet을 실행하려면 먼저 조직과 대화할 수 있는 모듈을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="6ef28-108">원격 [PowerShell을 사용하여 Exchange Online에 연결합니다.](https://go.microsoft.com/fwlink/p/?LinkId=785881)</span><span class="sxs-lookup"><span data-stu-id="6ef28-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="6ef28-109">예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="6ef28-109">Example scenarios</span></span>

<span data-ttu-id="6ef28-110">비즈니스의 주 도메인이 기본 도메인으로 설정되어 있는 경우를 Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6ef28-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="6ef28-111">그러나 조직의 기본 허용 도메인은 service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6ef28-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="6ef28-112">즉, 그룹이 service.contoso.com(예: jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6ef28-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="6ef28-113">조직에 하위 도메인도 구성했다고 하자.</span><span class="sxs-lookup"><span data-stu-id="6ef28-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="6ef28-114">이러한 도메인에서 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="6ef28-115">students.contoso.com 위한 지원</span><span class="sxs-lookup"><span data-stu-id="6ef28-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="6ef28-116">faculty.contoso.com 구성원용 관리</span><span class="sxs-lookup"><span data-stu-id="6ef28-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="6ef28-117">다음 두 시나리오에서는 이 작업을 어떻게 수행할지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="6ef28-118">MULITPLEEAP가 있는 경우 우선 순위 순서대로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="6ef28-119">값이 1이면 우선 순위가 가장 높은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="6ef28-120">EAP가 일치하면 더 이상 EAP가 평가되는 것이 아니며 그룹에서 스탬프가 매칭되는 주소는 일치하는 EAP에 따라 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="6ef28-121">> 조건과 일치하는EAP가 없는 경우 조직의 기본 허용 도메인에서 그룹이 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="6ef28-122">허용 [도메인을](https://go.microsoft.com/fwlink/p/?LinkId=785428) 추가하는 방법에 대한 자세한 내용은 Exchange Online에서 허용 도메인 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ef28-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="6ef28-123">시나리오 1</span><span class="sxs-lookup"><span data-stu-id="6ef28-123">Scenario 1</span></span>

<span data-ttu-id="6ef28-124">다음 예에서는 조직의 모든 Microsoft 365 그룹을 조직 도메인에 프로비전하는 groups.contoso.com 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="6ef28-125">시나리오 2</span><span class="sxs-lookup"><span data-stu-id="6ef28-125">Scenario 2</span></span>

<span data-ttu-id="6ef28-126">Microsoft 365 그룹이 생성되는 하위 도메인을 제어하려는 경우를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="6ef28-127">당신은 원합니다:</span><span class="sxs-lookup"><span data-stu-id="6ef28-127">You want:</span></span>
  
- <span data-ttu-id="6ef28-128">학생(Department가 학생으로  설정된 사용자)이 students.groups.contoso.com 그룹입니다. </span><span class="sxs-lookup"><span data-stu-id="6ef28-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="6ef28-129">다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6ef28-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="6ef28-130">교직원 도메인에서 교직원(부서가 교직원으로 설정되어 있는 사용자 또는 전자 메일 주소에 **faculty.contoso.com)에** 의해 faculty.groups.contoso.com 그룹입니다. </span><span class="sxs-lookup"><span data-stu-id="6ef28-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="6ef28-131">다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6ef28-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="6ef28-132">다른 사용자가 만든 그룹은 groups.contoso.com 도메인에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="6ef28-133">다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6ef28-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="6ef28-134">전자 메일 주소 정책 변경</span><span class="sxs-lookup"><span data-stu-id="6ef28-134">Change email address policies</span></span>

<span data-ttu-id="6ef28-135">기존 EAP의 우선 순위 또는 전자 메일 주소 템플릿을 변경하기 위해 Set-EmailAddressPolicy cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6ef28-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="6ef28-136">EAP를 변경하는 경우 이미 프로비전된 그룹에는 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="6ef28-137">전자 메일 주소 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="6ef28-137">Delete email address policies</span></span>

<span data-ttu-id="6ef28-138">EAP를 삭제하려면 Remove-EmailAddressPolicy cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="6ef28-139">EAP를 변경하는 경우 이미 프로비전된 그룹에는 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="6ef28-140">하이브리드 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ef28-140">Hybrid requirements</span></span>

<span data-ttu-id="6ef28-141">조직이 하이브리드 시나리오에서 구성된 경우 조직이 [Microsoft 365](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) 그룹을 만들기 위한 요구 사항을 충족하는지 확인하도록 Microsoft 365 그룹 구성을(를) 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="6ef28-142">전자 메일 주소 정책 그룹 사용에 대한 추가 정보:</span><span class="sxs-lookup"><span data-stu-id="6ef28-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="6ef28-143">알아야 할 몇 가지 사항도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="6ef28-144">그룹이 만들어지는 속도는 조직에 구성된EAP 수에 따라 달라 졌습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="6ef28-145">관리자와 사용자는 그룹을 만들 때 도메인을 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="6ef28-146">사용자 그룹은 이미 사용 가능한 표준 쿼리(사용자 속성)를 사용하여 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="6ef28-147">지원되는 필터링 가능한 속성에 [대해 -RecipientFilter 매개](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) 변수에 대해 필터링할 수 있는 속성을 체크 아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-147">Check out [Filterable properties for the -RecipientFilter parameter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="6ef28-148">그룹에 대해 EAP를 구성하지 않은 경우 그룹 만들기를 위해 기본 허용 도메인이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="6ef28-149">허용 도메인을 제거하면 먼저 EAP를 업데이트해야 합니다. 그렇지 않으면 그룹 프로비전이 영향을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="6ef28-150">조직에 대해 최대 100개 전자 메일 주소 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef28-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="6ef28-151">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6ef28-151">Related articles</span></span>

[<span data-ttu-id="6ef28-152">공동 작업 거버넌스 계획 단계별</span><span class="sxs-lookup"><span data-stu-id="6ef28-152">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="6ef28-153">공동 작업 거버넌스 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="6ef28-153">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="6ef28-154">관리 센터에서 Microsoft 365 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="6ef28-154">Create an Microsoft 365 group in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)

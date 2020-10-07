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
description: PowerShell을 사용 하 여 전자 메일 주소 정책을 구성 하 여 Microsoft 365 그룹을 만들 때 사용할 도메인을 선택 하는 방법을 알아봅니다.
ms.openlocfilehash: bb6137a3dfce17bc9c94648e5ea9e12ec2776195
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377440"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="66267-103">Microsoft 365 그룹을 만들 때 사용할 도메인 선택</span><span class="sxs-lookup"><span data-stu-id="66267-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="66267-104">일부 조직에서는 별도의 전자 메일 도메인을 사용하여 비즈니스의 여러 부분을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="66267-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="66267-105">사용자가 Microsoft 365 그룹을 만들 때 사용 해야 할 도메인을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="66267-106">조직에서 사용자가 회사의 기본 허용 도메인이 아닌 다른 도메인에서 그룹을 만들어야 하는 경우 PowerShell을 사용 하 여 EAPs (전자 메일 주소 정책)를 구성 하 여이를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="66267-107">PowerShell cmdlet을 실행 하기 전에 조직에 대 한 의견을 받을 수 있는 모듈을 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="66267-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="66267-108">[원격 PowerShell을 사용 하 여 Exchange Online에 연결을](https://go.microsoft.com/fwlink/p/?LinkId=785881)확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66267-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="66267-109">예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="66267-109">Example scenarios</span></span>

<span data-ttu-id="66267-110">회사의 기본 도메인을 Contoso.com 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="66267-111">그러나 조직의 기본 허용 도메인은 service.contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="66267-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="66267-112">즉, 그룹은 service.contoso.com (예: jimsteam@service.contoso.com)에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66267-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="66267-113">조직에 하위 도메인도 구성 되어 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="66267-114">이러한 도메인에서 그룹을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="66267-115">학생용 students.contoso.com</span><span class="sxs-lookup"><span data-stu-id="66267-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="66267-116">교직원 용 faculty.contoso.com 구성원</span><span class="sxs-lookup"><span data-stu-id="66267-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="66267-117">다음 두 시나리오에서는이 작업을 수행 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="66267-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="66267-118">EAPs가 여러 개 있는 경우 우선 순위에 관계 없이 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66267-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="66267-119">값이 1 이면 가장 높은 우선 순위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66267-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="66267-120">EAP가 일치 하면 더 이상 EAP가 평가 되지 않으며, 일치 하는 EAP에 따라 그룹에 스탬프 처리 되는 주소가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="66267-121">> 지정 된 기준과 일치 하는 EAPs가 없는 경우 조직의 기본 허용 도메인에 그룹이 프로 비전 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66267-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="66267-122">허용 도메인을 추가 하는 방법에 대 한 자세한 내용은 [Exchange Online에서 허용 도메인 관리](https://go.microsoft.com/fwlink/p/?LinkId=785428) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66267-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="66267-123">시나리오 1</span><span class="sxs-lookup"><span data-stu-id="66267-123">Scenario 1</span></span>

<span data-ttu-id="66267-124">다음 예에서는 groups.contoso.com 도메인에서 조직의 모든 Microsoft 365 그룹을 구축 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66267-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="66267-125">시나리오 2</span><span class="sxs-lookup"><span data-stu-id="66267-125">Scenario 2</span></span>

<span data-ttu-id="66267-126">Microsoft 365 그룹을 만드는 하위 도메인을 제어 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="66267-127">당신은 원합니다:</span><span class="sxs-lookup"><span data-stu-id="66267-127">You want:</span></span>
  
- <span data-ttu-id="66267-128">Students.groups.contoso.com 도메인에서 학생이 만든 그룹 ( **부서가** **학생**에 게 설정 된 사용자)</span><span class="sxs-lookup"><span data-stu-id="66267-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="66267-129">다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="66267-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="66267-130">Faculty.groups.contoso.com 도메인에서 교사 구성원 (부서나 **전자 메일 주소로**설정 된 **부서** )에 의해 만들어진 그룹에 대 한 faculty.contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="66267-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="66267-131">다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="66267-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="66267-132">다른 사용자가 만든 그룹은 groups.contoso.com 도메인에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66267-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="66267-133">다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="66267-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="66267-134">전자 메일 주소 정책 변경</span><span class="sxs-lookup"><span data-stu-id="66267-134">Change email address policies</span></span>

<span data-ttu-id="66267-135">기존 EAP에 대 한 우선 순위 또는 전자 메일 주소 템플릿을 변경 하려면 Set-EmailAddressPolicy cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="66267-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="66267-136">EAP를 변경 해도 이미 프로 비전 된 그룹에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="66267-137">전자 메일 주소 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="66267-137">Delete email address policies</span></span>

<span data-ttu-id="66267-138">EAP를 삭제 하려면 Remove-EmailAddressPolicy cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="66267-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="66267-139">EAP를 변경 해도 이미 프로 비전 된 그룹에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="66267-140">하이브리드 요구 사항</span><span class="sxs-lookup"><span data-stu-id="66267-140">Hybrid requirements</span></span>

<span data-ttu-id="66267-141">조직이 하이브리드 시나리오에서 구성 된 경우 [에는 온-프레미스 Exchange 하이브리드를 사용 하 여 microsoft 365 그룹 구성을](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) 확인 하 여 조직이 microsoft 365 그룹을 만드는 데 필요한 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66267-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="66267-142">전자 메일 주소 정책 그룹 사용에 대 한 추가 정보:</span><span class="sxs-lookup"><span data-stu-id="66267-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="66267-143">알아야 할 몇 가지 추가 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="66267-144">그룹을 만드는 속도는 조직에서 구성 된 EAPs의 수에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="66267-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="66267-145">관리자 및 사용자는 그룹을 만들 때 도메인을 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="66267-146">사용자 그룹은 이미 사용 가능한 표준 쿼리 (사용자 속성)를 사용 하 여 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66267-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="66267-147">지원 되는 필터링 할 수 있는 속성에 대 한 [-RecipientFilter 매개 변수의 필터링 된 속성](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) 을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66267-147">Check out [Filterable properties for the -RecipientFilter parameter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="66267-148">그룹에 대해 EAPs를 구성 하지 않으면 그룹을 만들 때 사용할 수 있는 기본 허용 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66267-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="66267-149">허용 도메인을 제거 하는 경우 먼저 EAPs를 업데이트 해야 하며, 그렇지 않으면 그룹 프로 비전이 영향을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66267-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="66267-150">조직에 대해 최대 100 전자 메일 주소 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66267-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="66267-151">관련 문서</span><span class="sxs-lookup"><span data-stu-id="66267-151">Related articles</span></span>

[<span data-ttu-id="66267-152">관리 센터에서 Microsoft 365 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="66267-152">Create an Microsoft 365 group in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)

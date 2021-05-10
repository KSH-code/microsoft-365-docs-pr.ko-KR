---
title: 데이터 손실 방지 참조
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 데이터 손실 방지 참조 자료
ms.openlocfilehash: a039b8d99bd92be0040f6207803981e8a2937c6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296771"
---
# <a name="data-loss-prevention-reference"></a><span data-ttu-id="0bd43-103">데이터 손실 방지 참조</span><span class="sxs-lookup"><span data-stu-id="0bd43-103">Data loss prevention reference</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="0bd43-104">이 참조 항목은 더 이상 DLP(데이터 손실 방지) 정보의 기본 Microsoft 365 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-104">This is reference topic is no longer the main resource for Microsoft 365 data loss prevention (DLP) information.</span></span> <span data-ttu-id="0bd43-105">DLP 콘텐츠 집합이 업데이트 및 재구성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-105">The DLP content set is being updated and restructured.</span></span> <span data-ttu-id="0bd43-106">이 문서에서 다루는 항목은 업데이트된 새로운 문서로 이동될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-106">The topics covered in this article will be moving to new, updated articles.</span></span> <span data-ttu-id="0bd43-107">DLP에 대한 자세한 내용은 데이터 손실 [방지에 대한 자세한 정보를 참조하세요.](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="0bd43-107">For more information about DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> <span data-ttu-id="0bd43-108">데이터 손실 방지 기능은 최근 Office 365 Advanced Compliance 라이선스 사용자에 대한 Microsoft Teams 채팅 및 채널 메시지에 추가되었으며, 이는 독립 실행형 옵션으로 제공되며 Office 365 E5 및 Microsoft 365 E5 규정 준수에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-108">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="0bd43-109">라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bd43-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a><span data-ttu-id="0bd43-110">DLP 정책 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="0bd43-110">Create and manage DLP policies</span></span>

<span data-ttu-id="0bd43-111">Microsoft 365 준수 센터의 데이터 손실 방지 페이지에서 DLP 정책을 생성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-111">You create and manage DLP policies on the Data loss prevention page in the Microsoft 365 Compliance center.</span></span>
  
![Office 365 보안 &amp; 준수 센터의 데이터 손실 방지 페이지](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
<span data-ttu-id="0bd43-113">규칙을 사용하여 특정 보호 요구 사항을 충족한 다음, DLP 정책을 사용하여 특정 규정을 준수하는 데 필요한 모든 규칙과 같은 일반적인 보호 요구 사항을 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-113">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="0bd43-114">예를 들어 HIPAA(Health Insurance Portability and Accountability Act)가 적용되는 정보의 현재 상태를 확인하는 데 도움이 되는 DLP 정책이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-114">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="0bd43-115">해당 DLP 정책은 조직 외부의 사용자와 공유(조건)하는 중요한 정보가 포함된 모든 문서를 찾고 문서에 대한 액세스 차단 및 알림을 전송하여(작업) 모든 SharePoint Online 사이트 및 모든 비즈니스용 OneDrive 사이트(위치)에서 HIPAA 데이터(대상)를 보호하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-115">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="0bd43-116">해당 요구 사항은 개별 규칙으로 저장되며 관리 및 보고를 간소화하기 위해 DLP 정책으로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-116">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![위치 및 규칙을 포함한 DLP 정책을 보여주는 다이어그램](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

<span data-ttu-id="0bd43-118">Exchange에서 특정 메일 그룹을 포함하도록 선택하는 경우 DLP 정책은 해당 그룹의 구성원으로만 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-118">If you choose to include specific distribution groups in Exchange, the DLP policy will be scoped only to the members of that group.</span></span> <span data-ttu-id="0bd43-119">마찬가지로 메일 그룹을 제외하면 해당 메일 그룹의 모든 구성원이 정책 평가에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-119">Similarly excluding a distribution group will exclude all the members of that distribution group from policy evaluation.</span></span> <span data-ttu-id="0bd43-120">메일 그룹의 구성원, 동적 메일 그룹, 보안 그룹에 대한 정책의 범위를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-120">You can choose to scope a policy to the members of distribution lists, dynamic distribution groups, and security groups.</span></span> <span data-ttu-id="0bd43-121">DLP 정책에는 50개 이하의 이러한 포함 및 제외가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-121">A DLP policy can contain no more than 50 such inclusions and exclusions.</span></span>

<span data-ttu-id="0bd43-122">특정 SharePoint 사이트를 포함하거나 제외하도록 선택하는 경우 DLP 정책은 이러한 포함 항목 및 제외 항목을 100개까지 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-122">If you choose to include or exclude specific SharePoint sites, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="0bd43-123">해당 제한 사항에도 불구하고 조직 전체의 정책이나 전체 위치에 적용되는 정책을 적용하여 해당 제한 사항을 극복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-123">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>

<span data-ttu-id="0bd43-124">특정 OneDrive 계정 또는 그룹을 포함하거나 제외하도록 선택하는 경우 DLP 정책에는 100개 이상의 사용자 계정 또는 50개 그룹을 포함하거나 제외로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-124">If you choose to include or exclude specific OneDrive accounts or groups, a DLP policy can contain no more than 100 user accounts or 50 groups as inclusion or exclusion.</span></span>

> [!NOTE]
> <span data-ttu-id="0bd43-125">계정 또는 그룹을 사용한 비즈니스 정책 범위 지정용 OneDrive는 공개 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-125">OneDrive for business policy scoping using accounts or groups is in public preview.</span></span> <span data-ttu-id="0bd43-126">이 단계가 진행되는 동안 사용자 계정 및 그룹을 DLP 정책의 일부로 포함하거나 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-126">During this phase, you can either include or exclude user accounts and groups as part of a DLP policy.</span></span> <span data-ttu-id="0bd43-127">동일한 정책의 일부로 포함 및 제외는 모두 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-127">Both inclusion and exclusion as part of the same policy is not supported.</span></span>
  
### <a name="rules"></a><span data-ttu-id="0bd43-128">규칙</span><span class="sxs-lookup"><span data-stu-id="0bd43-128">Rules</span></span>

> [!NOTE]
> <span data-ttu-id="0bd43-129">알림을 구성하지 않은 경우 DLP 정책에 대한 기본 동작은 알림을 보내거나 트리거하는 게 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-129">The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger.</span></span> <span data-ttu-id="0bd43-130">이는 기본 정보 유형에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-130">This applies only to default information types.</span></span> <span data-ttu-id="0bd43-131">사용자 지정 정보 유형의 경우에는 정책에 정의된 작업이 없는 경우에도 시스템이 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-131">For custom information types, the system will alert even if there is no action defined in the policy.</span></span>

<span data-ttu-id="0bd43-132">규칙은 조직의 콘텐츠에 비즈니스 요구사항을 적용한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-132">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="0bd43-133">정책은 하나 이상의 규칙을 포함하고 각 규칙은 조건 및 작업을 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-133">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="0bd43-134">각 규칙에 대해 조건이 충족되면 작업이 자동으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-134">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="0bd43-135">규칙은 각 정책에서 가장 우선순위가 높은 규칙부터 순차적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-135">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="0bd43-136">또한 규칙은 사용자(정책 팁 및 전자메일 알림 포함) 및 관리자(전자메일 사고 보고서 포함)에게 콘텐츠가 규칙과 일치함을 알리는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-136">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="0bd43-137">다음과 같이 규칙의 구성요소 및 각각에 대한 설명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-137">Here are the components of a rule, each explained below.</span></span>
  
![DLP 규칙 편집기에 대한 장](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="0bd43-139">조건</span><span class="sxs-lookup"><span data-stu-id="0bd43-139">Conditions</span></span>

<span data-ttu-id="0bd43-140">조건은 사용자가 찾고 있는 정보의 유형과 수행하는 시기를 결정하므로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-140">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="0bd43-141">예를 들어 콘텐츠에 10보다 큰 숫자를 포함하지 않고 콘텐츠가 조직 외부의 사용자와 공유되지 않는 경우에는 여권 번호를 포함하는 콘텐츠를 무시하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-141">For example, you might choose to ignore content containing passport numbers unless the content contains more than 10 such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="0bd43-142">조건은 사용자가 찾고 있는 중요한 정보의 유형이 무엇인지와 같은 **콘텐츠** 에 중점을 두고 있습니다. 또한 문서를 공유하는 대상이 누구인지와 같은 **컨텍스트** 에 중점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-142">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="0bd43-143">조건을 사용하여 위험 수준마다 다른 작업을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-143">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="0bd43-144">예를 들어 내부적으로 공유하는 중요한 콘텐츠는 조직 외부의 사용자와 공유되는 중요한 콘텐츠 보다 위험성이 더 낮고 더 적은 작업이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-144">For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![사용 가능한 DLP 조건을 표시하는 목록](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="0bd43-146">이제 사용 가능한 조건을 통해 다음 사항의 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-146">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="0bd43-147">콘텐츠가 중요한 정보 유형을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-147">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="0bd43-148">콘텐츠가 레이블을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-148">Content contains a label.</span></span> <span data-ttu-id="0bd43-149">더 자세한 내용은 아래의 [DLP 정책에서 보존 레이블을 조건으로 사용하기](#using-a-retention-label-as-a-condition-in-a-dlp-policy) 장을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bd43-149">For more information, see the below section [Using a retention label as a condition in a DLP policy](#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="0bd43-150">콘텐츠를 조직 내부 또는 외부 사용자와 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-150">Content is shared with people outside or inside your organization.</span></span>

  > [!NOTE]
  > <span data-ttu-id="0bd43-151">호스트 조직의 Active Directory 또는 Azure Active Directory 테넌트에 게스트가 아닌 계정을 보유하고 있는 사용자는 조직 내부의 사용자로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-151">Users who have non-guest accounts in a host organization's Active Directory or Azure Active Directory tenant are considered as people inside the organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="0bd43-152">중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="0bd43-152">Types of sensitive information</span></span>

<span data-ttu-id="0bd43-153">DLP 정책은 **중요한 정보 유형** 으로 정의되어 있는 중요한 정보를 보호하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-153">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="0bd43-154">Microsoft 365에는 신용 카드 번호, 은행 계좌 번호, 국가 ID 번호 및 여권 번호 등 사용할 준비가 된 여러 다른 영역에 대한 일반적인 여러 중요 정보 유형에 대한 정의가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-154">Microsoft 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![사용가능한 중요한 정보 유형의 목록](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="0bd43-156">DLP 정책이 신용 카드 번호와 같은 중요한 정보 유형을 찾을 때 단순히 16자리 숫자만 찾는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-156">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="0bd43-157">중요한 각 정보 유형은 다음의 조합을 사용해서 정의되고 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-157">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="0bd43-158">키워드.</span><span class="sxs-lookup"><span data-stu-id="0bd43-158">Keywords.</span></span>
    
- <span data-ttu-id="0bd43-159">체크섬 또는 구성의 유효성을 검사하기 위한 내부 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-159">Internal functions to validate checksums or composition.</span></span>
    
- <span data-ttu-id="0bd43-160">패턴 일치를 찾기 위한 정규식의 평가입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-160">Evaluation of regular expressions to find pattern matches.</span></span>
    
- <span data-ttu-id="0bd43-161">기타 콘텐츠 검사.</span><span class="sxs-lookup"><span data-stu-id="0bd43-161">Other content examination.</span></span>
    
<span data-ttu-id="0bd43-162">성러한 정책은 사용자 작업을 중단시킬 수 있는 가양성의 수를 줄이는 동시에 DLP 검색 시 높은 수준의 정확도를 얻을 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-162">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="0bd43-163">작업</span><span class="sxs-lookup"><span data-stu-id="0bd43-163">Actions</span></span>

<span data-ttu-id="0bd43-164">콘텐츠가 규칙에서 조건과 일치하는 경우 자동으로 콘텐츠를 보호하기 위한 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-164">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![사용 가능한 DLP 작업 목록](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="0bd43-166">현재 사용할 수 있는 작업으로 다음과 같은 작업을 수행할 수 있습니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-166">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="0bd43-167">**콘텐츠에 대한 액세스 제한** 필요에 따라 다음 세 가지 방법으로 콘텐츠에 대한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-167">**Restrict access to the content** Depending on your need, you can restrict access to content in three ways:</span></span>

  1. <span data-ttu-id="0bd43-168">모든 사용자의 콘텐츠에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-168">Restrict access to content for everyone.</span></span>
  2. <span data-ttu-id="0bd43-169">조직 외부 사용자의 콘텐츠에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-169">Restrict access to content for people outside the organization.</span></span>
  3. <span data-ttu-id="0bd43-170">"링크가 있는 모든 사용자"의 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-170">Restrict access to "Anyone with the link."</span></span>

  <span data-ttu-id="0bd43-171">사이트 콘텐츠의 경우, 이는 문서에 대한 사용 권한이 주 사이트 컬렉션 관리자, 문서 소유자 및 문서를 마지막에 수정한 사용자를 제외한 모든 사람들에게 제한되어 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-171">For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="0bd43-172">해당 사용자는 문서에서 중요한 정보를 제거하거나 다른 해결 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-172">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="0bd43-173">문서가 규정을 준수하는 경우 원래의 사용 권한은 자동으로 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-173">When the document is in compliance, the original permissions are automatically restored.</span></span> <span data-ttu-id="0bd43-174">문서에 대한 액세스가 차단되면 해당 문서가 사이트 라이브러리에서 특수한 정책 팁 아이콘과 함께 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-174">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
  ![문서에 액세스를 표시하는 정책 팁이 차단됩니다.](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  <span data-ttu-id="0bd43-176">전자 메일 콘텐츠의 경우 이 작업은 메시지가 발송되지 않도록 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-176">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="0bd43-177">DLP 규칙이 구성된 방식에 따라 발신자는 NDR 또는 (규칙이 알림을 사용하는 경우) 정책 팁 및/또는 전자 메일 알림을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-177">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
  ![메시지에서 인증되지 않은 수신자를 제거해야 한다는 경고](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="0bd43-179">사용자 알림 및 사용자 재정의</span><span class="sxs-lookup"><span data-stu-id="0bd43-179">User notifications and user overrides</span></span>

<span data-ttu-id="0bd43-180">알림 및 재정의를 사용하여 사용자에 DLP 정책에 대해 교육하고 작업을 차단하지 않고도 규정을 준수할 수 있도록 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-180">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="0bd43-181">예를 들어 사용자가 중요한 정보를 포함하는 문서를 공유하려고 하면 DLP 정책은 전자 메일 알림을 보내고, 업무 정당성이 있을 경우 이 정책을 재정의할 수 있는 문서 라이브러리의 컨텍스트에서 정책 팁을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-181">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![DLP 규칙 편집기의 사용자 알림 및 사용자 재정의](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="0bd43-183">전자 메일의 경우 콘텐츠를 발송한 사람. 공유한 사람 또는 마지막으로 수정한 사람을 알릴 수 있으며, 사이트 콘텐츠의 경우 주 사이트 컬렉션 관리자 및 문서 소유자를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-183">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="0bd43-184">또한 전자 메일 알림에서 원하는 사람을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-184">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="0bd43-185">전자 메일 알림을 발송하는 것 외에도 사용자 알림에는 다음과 같은 정책 팁이 표시됩니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-185">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="0bd43-186">Outlook 및 웹 상의 Outlook</span><span class="sxs-lookup"><span data-stu-id="0bd43-186">In Outlook and Outlook on the web.</span></span>
    
- <span data-ttu-id="0bd43-187">SharePoint Online 또는 비즈니스용 OneDrive 사이트에 대한 문서의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-187">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="0bd43-188">Excel, PowerPoint 및 Word에서 DLP 정책에 포함된 사이트에 문서가 저장되는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-188">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="0bd43-189">전자 메일 알림 및 정책 팁은 콘텐츠가 DLP 정책과 충돌하는 이유를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-189">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="0bd43-190">해당 항목을 선택하면 전자 메일 알림 및 정책 팁은 가양성을 보고하거나 업무 정당성을 제공하여 사용자가 규칙을 재정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-190">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="0bd43-191">이를 통해 사용자에게 DLP 정책을 교육하고, 사람들이 해당 작업을 수행하지 못하도록 하는 방식으로 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-191">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="0bd43-192">재정의 및 가양성에 대한 정보는 보고를 위해 기록되고(DLP 보고서에 대해서는 아래 참조) 사고 보고서(다음 섹션 참조)에 포함되므로 규정 준수 책임자는 정기적으로 이 정보를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-192">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="0bd43-193">다음은 비즈니스용 OneDrive 계정에서 보여지는 정책 팁의 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-193">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![OneDrive 계정의 문서에 대한 정책 팁](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 <span data-ttu-id="0bd43-195">DLP 정책의 사용자 알림과 정책 팁에 대한 자세한 내용은 [알림 및 정책 팁 사용](use-notifications-and-policy-tips.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd43-195">To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).</span></span>

#### <a name="alerts-and-incident-reports"></a><span data-ttu-id="0bd43-196">경고 및 인시던트 보고서</span><span class="sxs-lookup"><span data-stu-id="0bd43-196">Alerts and Incident reports</span></span>

<span data-ttu-id="0bd43-197">규칙이 일치하면 규정 준수 책임자(또는 선택한 다른 사람)에게 세부 정보와 함께 경고 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-197">When a rule is matched, you can send an alert email to your compliance officer ( or any person(s) you choose) with details of the alert.</span></span> <span data-ttu-id="0bd43-198">이 경고 전자 메일에는 규정 준수 책임자가 경고 및 이벤트의 세부 정보를 볼 수 있도록 [DLP 경고 관리 대시보드](dlp-configure-view-alerts-policies.md)의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-198">This alert email will carry a link of the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) which the compliance officer can go to view the details of alert and events.</span></span> <span data-ttu-id="0bd43-199">대시보드에는 DLP 정책과 일치하는 세부 정보 및 검색된 중요한 콘텐츠와 함께 경고를 트리거한 이벤트의 세부 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-199">The dashboard contains details of the event that triggered the alert along with details of the DLP policy matched and the sensitive content detected.</span></span>

<span data-ttu-id="0bd43-200">또한 이벤트 세부 정보가 포함된 인시던트 보고서를 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-200">In addition, you can also send an incident report with details of the event.</span></span> <span data-ttu-id="0bd43-201">이 보고서에는 일치된 항목에 관한 정보, 규칙과 일치한 실제 콘텐츠, 해당 콘텐츠를 마지막으로 수정한 사람이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-201">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="0bd43-202">전자 메일 메시지의 경우 보고서에는 DLP 정책과 일치하는 원본 메시지가 첨부 파일로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-202">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0bd43-203">![사고 보고서를 구성하기 위한 페이지](../media/Alerts-and-incident-report.png)</span><span class="sxs-lookup"><span data-stu-id="0bd43-203">![Page for configuring incident reports](../media/Alerts-and-incident-report.png)</span></span>

<span data-ttu-id="0bd43-204">DLP는 SharePoint Online 또는 비즈니스용 OneDrive의 항목과는 다른 방식으로 전자 메일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-204">DLP scans email differently from items in SharePoint Online or OneDrive for Business.</span></span> <span data-ttu-id="0bd43-205">SharePoint Online 및 비즈니스용 OneDrive에서 DLP는 기존 항목을 비롯하여 새 항목을 검사하고 일치하는 항목이 발견될 때마다 경고 및 인시던트 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-205">In SharePoint Online and OneDrive for Business, DLP scans existing items as well as new ones and generates an alert and incident report whenever a match is found.</span></span> <span data-ttu-id="0bd43-206">Exchange Online에서 DLP는 새 전자 메일 메시지만 검사하고 정책 일치 항목이 있는 경우에 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-206">In Exchange Online, DLP only scans new email messages and generates a report if there is a policy match.</span></span> <span data-ttu-id="0bd43-207">DLP는 사서함이나 보관함에 저장된 기존 전자 메일 항목을 검색하거나 일치시키지 ***않습니다.***</span><span class="sxs-lookup"><span data-stu-id="0bd43-207">DLP ***does not*** scan or match previously existing email items that are stored in a mailbox or archive.</span></span>
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="0bd43-208">그룹화 및 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="0bd43-208">Grouping and logical operators</span></span>

<span data-ttu-id="0bd43-209">일반적으로 DLP 정책에는 미국의 주민등록번호를 포함하는 모든 콘텐츠를 식별하는 것과 같은 간단한 요구사항을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-209">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="0bd43-210">하지만 다른 시나리오에서는 DLP 정책이 좀 더 느슨하게 정의된 데이터를 식별해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-210">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="0bd43-211">예를 들어 미국 HIPAA(Health Insurance Portability and Accountability Act)를 적용받는 콘텐츠를 식별하려면 다음과 같은 정보를 찾아야 합니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-211">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="0bd43-212">미국 사회보장번호 또는 DEA(마약단속국) 번호와 같은 특정 유형의 중요한 정보를 포함하는 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="0bd43-212">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="0bd43-213">그리고</span><span class="sxs-lookup"><span data-stu-id="0bd43-213">AND</span></span>
    
- <span data-ttu-id="0bd43-214">환자의 병력에 관한 커뮤니케이션 또는 환자에게 제공된 의료 서비스에 대한 설명과 같이 식별하기 더 어려운 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="0bd43-214">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="0bd43-215">해당 콘텐츠를 식별하려면 국제질병분류(ICD-9-CM 또는 ICD-10-CM)처럼 아주 방대한 키워드 목록에서 일치하는 키워드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-215">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="0bd43-216">이렇게 느슨하게 정의된 데이터는 그룹화 및 논리 연산자(AND, OR)를 사용하여 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-216">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="0bd43-217">DLP 정책을 만들 때는</span><span class="sxs-lookup"><span data-stu-id="0bd43-217">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="0bd43-218">중요한 정보 유형을 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-218">Group sensitive information types.</span></span>
    
- <span data-ttu-id="0bd43-219">그룹에 포함된 중요한 정보 사이에 사용할 논리 연산자와 각 그룹 사이에 사용할 논리 연산자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-219">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="0bd43-220">그룹 내의 연산자 선택</span><span class="sxs-lookup"><span data-stu-id="0bd43-220">Choosing the operator within a group</span></span>

<span data-ttu-id="0bd43-221">그룹 내에서 콘텐츠가 규칙에 일치하려면 해당 그룹의 조건을 모두 충족해야 하는지 또는 하나라도 충족하면 되는지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-221">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![그룹 내의 연산자가 표시된 그룹](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="0bd43-223">그룹 추가</span><span class="sxs-lookup"><span data-stu-id="0bd43-223">Adding a group</span></span>

<span data-ttu-id="0bd43-224">그룹을 빠르게 추가할 수 있습니다. 그룹은 자체적인 조건과 연산자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-224">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![그룹 단추 추가](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="0bd43-226">그룹 사이의 연산자 선택</span><span class="sxs-lookup"><span data-stu-id="0bd43-226">Choosing the operator between groups</span></span>

<span data-ttu-id="0bd43-227">각 그룹 사이에서 콘텐츠가 규칙에 매칭되려면 그룹 하나의 조건만 충족해야 하는지 또는 모든 그룹의 조건을 충족해야 하는지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-227">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="0bd43-228">예를 들어 기본 제공되는 **미국 HIPAA** 정책에는 그룹 사이에서 **AND** 연산자를 사용하여 다음과 같은 정보가 포함된 콘텐츠를 식별하는 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-228">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="0bd43-229">그룹 **PII 식별자** 에서(하나 이상의 SSN 번호 **또는** DEA 번호)</span><span class="sxs-lookup"><span data-stu-id="0bd43-229">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="0bd43-230">**AND**</span><span class="sxs-lookup"><span data-stu-id="0bd43-230">**AND**</span></span>
    
- <span data-ttu-id="0bd43-231">그룹 **의료 조건** 에서(하나 이상의 ICD-9-CM 키워드 **또는** ICD-10-CM 키워드)</span><span class="sxs-lookup"><span data-stu-id="0bd43-231">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![각 그룹 사이의 연산자가 표시된 그룹](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="0bd43-233">규칙이 처리되는 우선 순위</span><span class="sxs-lookup"><span data-stu-id="0bd43-233">The priority by which rules are processed</span></span>

<span data-ttu-id="0bd43-234">정책의 규칙을 만들 때는 각 규칙에 만들어진 순서대로 우선 순위가 할당됩니다. 즉, 처음 만들어진 규칙에는 첫 번째 우선 순위가 할당되고 두 번째 만들어진 규칙에는 두 번째 우선 순위가 할당되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-234">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0bd43-235">![우선 순위의 규칙](../media/dlp-rules-in-priority-order.png)</span><span class="sxs-lookup"><span data-stu-id="0bd43-235">![Rules in priority order](../media/dlp-rules-in-priority-order.png)</span></span>
  
<span data-ttu-id="0bd43-236">둘 이상의 DLP 정책을 설정한 후에는 하나 이상의 정책에 대해 우선 순위를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-236">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="0bd43-237">그러기 위해서는 정책을 선택하고 **정책 편집** 을 선택한 다음 **우선 순위** 목록을 사용하여 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-237">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0bd43-238">![정책에 대한 우선 순위 설정](../media/dlp-set-policy-priority.png)</span><span class="sxs-lookup"><span data-stu-id="0bd43-238">![Set priority for a policy](../media/dlp-set-policy-priority.png)</span></span>

<span data-ttu-id="0bd43-239">콘텐츠를 규칙에 대해 평가할 때 규칙은 우선 순위대로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-239">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="0bd43-240">콘텐츠가 여러 규칙과 일치하는 경우 규칙은 우선 순위대로 처리되고 가장 제한적인 작업이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-240">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="0bd43-241">예를 들어 콘텐츠가 다음과 같은 규칙과 모두 일치하는 경우 우선 순위가 가장 높고 가장 제한적인 규칙 3이 적용됩니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-241">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="0bd43-242">규칙 1: 사용자에게 알리기만 함</span><span class="sxs-lookup"><span data-stu-id="0bd43-242">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="0bd43-243">규칙 2: 사용자에게 알리고, 액세스를 제한하고, 사용자 재정의를 허용함</span><span class="sxs-lookup"><span data-stu-id="0bd43-243">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="0bd43-244">규칙 3: 사용자에게 알리고, 액세스를 제한하고, 사용자 재정의를 허용하지 않음</span><span class="sxs-lookup"><span data-stu-id="0bd43-244">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="0bd43-245">규칙 4: 사용자에게 알리기만 함</span><span class="sxs-lookup"><span data-stu-id="0bd43-245">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="0bd43-246">규칙 5: 액세스를 제한함</span><span class="sxs-lookup"><span data-stu-id="0bd43-246">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="0bd43-247">규칙 6: 사용자에게 알리고, 액세스를 제한하고, 사용자 재정의를 허용하지 않음</span><span class="sxs-lookup"><span data-stu-id="0bd43-247">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="0bd43-248">이 예시에서 가장 제한적인 규칙만 적용되더라도 모든 규칙에 대한 일치 항목이 감사 로그에 기록되고 DLP 보고서에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-248">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="0bd43-249">정책 팁에 대한 자세한 내용은 다음을 참고하십시오:</span><span class="sxs-lookup"><span data-stu-id="0bd43-249">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="0bd43-250">가장 높은 우선 순위와 가장 제한적인 규칙의 정책 팁만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-250">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="0bd43-251">예를 들어 알림을 콘텐츠 액세스를 차단하는 규칙의 정책 팁은 단순히 알림을 보내는 규칙의 정책 팁보다 우선적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-251">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="0bd43-252">따라서 정책 팁이 단계별로 표시되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-252">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="0bd43-253">가장 제한적인 규칙의 정책 팁이 사용자의 규칙 재정의를 허용할 경우 이 규칙을 재정의하면 해당 콘텐츠가 일치하는 다른 모든 규칙이 함께 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-253">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="0bd43-254">더 쉽게 또는 더 어렵게 일치하도록 규칙 조정</span><span class="sxs-lookup"><span data-stu-id="0bd43-254">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="0bd43-255">DLP 정책을 만들고 설정한 후에 다음과 같은 문제가 발생하기도 합니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-255">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="0bd43-256">중요한 정보가 **아닌** 콘텐츠가 규칙과 너무 많이 일치합니다. 즉, 가양성이 너무 많습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-256">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="0bd43-257">중요한 정보가 **있는** 콘텐츠 중 규칙과 일치하는 콘텐츠가 너무 적습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-257">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="0bd43-258">즉, 중요한 정보에 대한 보호 조치가 적용되고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-258">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="0bd43-259">이러한 문제를 해결하려면 콘텐츠가 규칙과 더 어렵게 또는 더 쉽게 일치하도록 인스턴스 수와 일치 정확도를 조정하여 규칙을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-259">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="0bd43-260">규칙에 사용되는 각 중요한 정보 유형에는 인스턴스 수와 일치 정확도가 둘 다 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-260">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="0bd43-261">인스턴스 수</span><span class="sxs-lookup"><span data-stu-id="0bd43-261">Instance count</span></span>

<span data-ttu-id="0bd43-262">인스턴스 수는 콘텐츠가 규칙과 일치하기 위해 있어야 하는 특정 중요한 정보 유형의 발생 횟수를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-262">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="0bd43-263">예를 들어, 다음의 경우에 아래와 같이 콘텐츠가 규칙에 일치합니다. 콘텐츠가 1에서 9사이의 고유한 미국 또는 영국의</span><span class="sxs-lookup"><span data-stu-id="0bd43-263">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="0bd43-264">여권 번호를 식별하는 경우.</span><span class="sxs-lookup"><span data-stu-id="0bd43-264">passport numbers are identified.</span></span>

> [!NOTE]
> <span data-ttu-id="0bd43-265">인스턴스 수에는 중요한 정보 유형 및 키워드에 대해 **고유한** 일치 항목만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-265">The instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="0bd43-266">예를 들어 전자 메일에 동일한 신용 카드 번호가 10번 포함되는 경우 해당 10번은 신용 카드 번호의 단일 인스턴스로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-266">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span>
  
<span data-ttu-id="0bd43-267">인스턴스 수를 사용하여 규칙을 조정하려는 경우 지침은 다음과 같이 간단합니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-267">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="0bd43-268">규칙이 더 쉽게 일치하도록 하려면 **최소** 개수를 줄이고(줄이거나) **최대** 개수를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-268">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="0bd43-269">숫자 값을 삭제하여 **최대** 를 **모두** 로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-269">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="0bd43-270">규칙이 더 어렵게 일치하도록 하려면 **최소** 개수를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-270">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="0bd43-271">일반적으로 인스턴스 수가 낮은(예: 1-9) 규칙에서는 덜 제한적인 작업(예: 사용자 알림 보내기)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-271">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="0bd43-272">또한 인스턴스 수가 높은(예: 10-모두) 규칙에서는 더 제한적인 작업(예: 사용자 재정의를 허용하지 않고 콘텐츠에 대한 액세스 제한)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-272">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![규칙 편집기의 인스턴스 수](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="0bd43-274">일치 정확도</span><span class="sxs-lookup"><span data-stu-id="0bd43-274">Match accuracy</span></span>

<span data-ttu-id="0bd43-275">위에서 설명한 것처럼, 중요한 정보 유형은 다양한 유형의 증거 결합을 통해 정의되고 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-275">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="0bd43-276">일반적으로 중요한 정보 유형은 패턴이라는 이러한 여러 결합으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-276">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="0bd43-277">증거가 덜 필요한 패턴은 일치 정확도(또는 신뢰 수준)가 낮은 데 반해 증거가 더 필요한 패턴은 일치 정확도(또는 신뢰 수준)가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-277">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="0bd43-278">모든 중요한 정보 유형에서 사용되는 실제 패턴 및 신뢰 수준에 대해 자세히 알아보려면 [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd43-278">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>
  
<span data-ttu-id="0bd43-279">예를 들어 신용 카드 번호라는 중요한 정보 유형은 다음과 같은 두 개의 패턴으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-279">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="0bd43-280">다음이 필요한 65% 신뢰의 패턴:</span><span class="sxs-lookup"><span data-stu-id="0bd43-280">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="0bd43-281">신용 카드 번호 형식의 숫자</span><span class="sxs-lookup"><span data-stu-id="0bd43-281">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="0bd43-282">체크섬을 전달하는 숫자</span><span class="sxs-lookup"><span data-stu-id="0bd43-282">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="0bd43-283">다음이 필요한 85% 신뢰의 패턴:</span><span class="sxs-lookup"><span data-stu-id="0bd43-283">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="0bd43-284">신용 카드 번호 형식의 숫자</span><span class="sxs-lookup"><span data-stu-id="0bd43-284">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="0bd43-285">체크섬을 전달하는 숫자</span><span class="sxs-lookup"><span data-stu-id="0bd43-285">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="0bd43-286">올바른 형식의 키워드 또는 만료 날짜</span><span class="sxs-lookup"><span data-stu-id="0bd43-286">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="0bd43-287">규칙에서 이러한 신뢰 수준(또는 일치 정확도)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-287">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="0bd43-288">일반적으로 일치 정확도가 낮은 규칙에서는 덜 제한적인 작업(예: 사용자 알림 보내기)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-288">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="0bd43-289">또한 일치 정확도가 높은 규칙에서는 더 제한적인 작업(예: 사용자 재정의를 허용하지 않고 콘텐츠에 대한 액세스 제한)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-289">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="0bd43-290">콘텐츠에서 특정 중요한 정보 유형(예: 신용 카드 번호)이 식별되면 하나의 신뢰 수준만 반환된다는 사실을 이해해야 합니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-290">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="0bd43-291">모든 일치 항목이 단일 패턴인 경우 해당 패턴의 신뢰 수준이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-291">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="0bd43-292">두 개 이상의 패턴에 대한 일치 항목이 있는 경우(즉, 서로 다른 두 가지 신뢰 수준의 일치 항목이 있는 경우) 모든 단일 패턴보다 높은 신뢰 수준만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-292">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="0bd43-293">이는 까다로운 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-293">This is the tricky part.</span></span> <span data-ttu-id="0bd43-294">예를 들어 신용 카드의 경우 65% 패턴과 85% 패턴이 둘 다 일치하면 더 많은 증거가 더 높은 신뢰를 의미하므로 해당 중요한 정보 유형에 대해 반환되는 신뢰 수준은 90%보다 높습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-294">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="0bd43-295">따라서 신용 카드에 대한 상호 배타적인 두 가지 규칙(65% 일치 정확도에 대한 규칙 하나와 85% 일치 정확도에 대한 규칙 하나)을 만들려는 경우 일치 정확도의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-295">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="0bd43-296">첫 번째 규칙에서는 65% 패턴의 일치 항목만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-296">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="0bd43-297">두 번째 규칙에서는 **하나 이상의** 85% 일치 항목을 선택하며 다른 낮은 신뢰의 일치 항목이 **잠재적으로 있을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0bd43-297">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![일치 정확도에 대한 서로 다른 범위가 포함된 두 개의 규칙](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="0bd43-299">해당 이유로 서로 다른 일치 정확도가 있는 규칙을 만들 때의 지침은 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-299">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="0bd43-300">일반적으로 가장 낮은 신뢰 수준에서는 **최소** 와 **최대**(범위 아님)에 같은 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-300">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="0bd43-301">일반적으로 가장 높은 신뢰 수준은 낮은 신뢰 수준 바로 위에서 100까지의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-301">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="0bd43-302">일반적으로 그 사이에 있는 모든 신뢰 수준은 낮은 신뢰 수준 바로 위에서 높은 신뢰 수준 바로 아래까지의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-302">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="0bd43-303">보존 레이블을 DLP 정책의 조건으로 사용</span><span class="sxs-lookup"><span data-stu-id="0bd43-303">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="0bd43-304">DLP 정책에서 이전에 생성 및 게시 된 [보존 레이블](retention.md#retention-labels)을 조건으로 사용하는 경우 다음 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-304">When you use a previously created and published [retention label](retention.md#retention-labels) as a condition in a DLP policy, there are some things to be aware of:</span></span>

- <span data-ttu-id="0bd43-305">DLP 정책의 조건으로 사용하기 전 미리 보존 레이블을 작성 및 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-305">The retention label must be created and published before you attempt to use it as a condition in a DLP policy.</span></span>
- <span data-ttu-id="0bd43-306">게시한 보존 레이블이 동기화되기까지 1일에서 7일까지 걸릴 수 있습니다. 자세한 내용은 보존 정책 형태로 게시되는 보존 레이블에 대한 [보존 레이블을 적용할 수 있게 되는 때](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) 및 자동 게시되는 보존 레이블에 대한 [보존 레이블이 유효해지는 데 걸리는 시간](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd43-306">Published retention labels can take from one to seven days to sync. For more information, see [When retention labels become available to apply](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) for retention labels published in a retention policy, and [How long it takes for retention labels to take effect](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) for retention labels that are auto-published.</span></span>
- <span data-ttu-id="0bd43-307">정책\*\* 형태로 보존 레이블 사용하기는 SharePoint 및 OneDrive\*\*\*의 항목에 한해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-307">Using a retention label in a policy \*\*is only supported for items in SharePoint and OneDrive\*\*\*.</span></span>

  ![조건으로서의 레이블](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  <span data-ttu-id="0bd43-309">보존 및 처리 중인 항목이 있고 다른 컨트롤을 적용하려는 경우 DLP 정책에 보존 레이블을 사용할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-309">You might want to use a retention label in a DLP policy if you have items that are under retention and disposition, and you also want to apply other controls to them, for example:</span></span>

  - <span data-ttu-id="0bd43-310">**과세 연도 2018** 이라는 보존 레이블을 게시했으며, 2018년에 과세 문서에 적용할 때 SharePoint에 저장된 10년 동안 보관한 다음 폐기합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-310">You published a retention label named **tax year 2018**, which when applied to tax documents from 2018 that are stored in SharePoint retains them for 10 years then disposes of them.</span></span> <span data-ttu-id="0bd43-311">또한 DLP 정책으로 수행할 수 있는 항목을 조직 외부에서 공유하고 싶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-311">You also don't want those items being shared outside your organization, which you can do with a DLP policy.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="0bd43-312">DLP 정책에서 보존 레이블을 조건으로 지정하고 Exchange 및/또는 Teams를 위치로 포함하면 이 오류가 발생합니다. **"전자 메일 및 팀 메시지에서 레이블이 지정된 콘텐츠를 보호할 수 없습니다. 아래의 레이블을 제거하거나 Exchange 및 Teams를 위치로 사용하는 것을 중지하세요."**</span><span class="sxs-lookup"><span data-stu-id="0bd43-312">You'll get this error if you specify a retention label as a condition in a DLP policy and you also include Exchange and/or Teams as a location: **"Protecting labeled content in email and teams messages isn't supported. Either remove the label below or turn off Exchange and Teams as a location."**</span></span> <span data-ttu-id="0bd43-313">이는 Exchange 전송에서 메시지 제출 및 배달이 진행되는 동안 레이블 메타 데이터를 평가하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-313">This is because Exchange transport does not evaluate the label metadata during message submission and delivery.</span></span> 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="0bd43-314">민감도 레이블을 DLP 정책의 조건으로 사용</span><span class="sxs-lookup"><span data-stu-id="0bd43-314">Using a sensitivity label as a condition in a DLP policy</span></span>

<span data-ttu-id="0bd43-315">[DLP 정책에서](./dlp-sensitivity-label-as-condition.md) 민감도 레이블을 조건으로 사용하는 방법을 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-315">[Learn more](./dlp-sensitivity-label-as-condition.md) about using Sensitivity label as a condition in DLP policies.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="0bd43-316">해당 기능이 다른 기능과 관련되는 방식</span><span class="sxs-lookup"><span data-stu-id="0bd43-316">How this feature relates to other features</span></span>

<span data-ttu-id="0bd43-317">중요한 정보를 포함하는 콘텐츠에 다음과 같은 몇 가지 기능을 적용할 수 있습니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-317">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="0bd43-318">[보존 레이블 및 보존 정책](retention.md) 모두 해당 콘텐츠에서 **보존** 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-318">A [retention label and a retention policy](retention.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="0bd43-319">DLP 정책은 해당 콘텐츠에 **보호** 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-319">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="0bd43-320">또한 이러한 작업을 적용하기 전에 DLP 정책은 레이블을 포함하는 콘텐츠 외에 다른 조건이 충족되도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-320">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![중요한 정보에 적용할 수 있는 기능의 다이어그램](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="0bd43-322">DLP 정책은 중요한 정보에 적용된 레이블 또는 보존 정책보다 풍부한 검색 기능을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-322">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="0bd43-323">DLP 정책은 중요한 정보를 포함하는 콘텐츠에 보호 작업을 적용할 수 있으며, 콘텐츠에서 중요한 정보가 제거되면 다음에 콘텐츠가 검색될 때 해당 보호 작업이 실행 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-323">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="0bd43-324">그러나 중요한 정보를 포함하는 콘텐츠에 보존 정책 또는 레이블이 적용되면, 해당 적용은 중요한 정보가 제거되더라도 실행 취소되지 않는 일회성 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-324">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="0bd43-325">레이블을 DLP 정책에서 조건으로 사용하여 해당 레이블이 있는 콘텐츠에 보존 작업과 보호 작업을 둘 다 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-325">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="0bd43-326">레이블을 포함하는 콘텐츠를 중요한 정보를 포함하는 콘텐츠와 정확히 같은 것으로 생각할 수 있습니다. 레이블 및 중요한 정보 유형은 콘텐츠에 작업을 적용할 수 있도록 해당 콘텐츠를 분류하는 데 사용되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-326">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![레이블을 조건으로 사용하는 DLP 정책의 다이어그램](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="0bd43-328">간단한 설정과 고급 설정</span><span class="sxs-lookup"><span data-stu-id="0bd43-328">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="0bd43-329">DLP 정책을 생성할 때 간단한 설정과 고급 설정 중 하나를 선택하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-329">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="0bd43-330">**간단한 설정** 을 사용하면 규칙 편집기를 사용하여 규칙을 만들거나 수정하지 않고도 대부분의 일반적인 유형의 DLP 정책을 손쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-330">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="0bd43-331">**고급 설정** 을 사용하면 규칙 편집기로 DLP 정책의 모든 설정을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-331">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="0bd43-332">걱정할 필요 없습니다. 간단한 설정과 고급 설정은 조건과 작업으로 구성된 규칙을 적용한다는 점에서 동일합니다. 간단한 설정에서는 규칙 편집기를 볼 수 없다는 점이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-332">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions—only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="0bd43-333">간단한 설정을 사용하면 빠르고 간편하게 DLP 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-333">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="0bd43-334">간단한 설정</span><span class="sxs-lookup"><span data-stu-id="0bd43-334">Simple settings</span></span>

<span data-ttu-id="0bd43-335">가장 일반적인 DLP 시나리오는 중요한 정보가 포함된 콘텐츠가 조직 밖의 사용자와 공유되지 않도록 보호하고, 콘텐츠에 액세스할 수 있는 사용자를 제한하거나, 최종 사용자 또는 관리자 알림을 발송하거나, 향후 조사를 위해 이벤트 감사를 수행하는 등의 자동 시정 조치를 취하는 정책을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-335">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remediating action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="0bd43-336">DLP는 중요한 정보가 우발적으로 공개되지 않도록 방지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-336">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="0bd43-337">DLP 정책을 만들 때 **간단한 설정 사용** 을 선택하면 이러한 목적을 간편하게 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-337">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="0bd43-338">간단한 설정에서는 규칙 편집기를 사용하지 않고도 대부분의 일반적인 DLP 정책을 구현하는 데 필요한 모든 것을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-338">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![기본 설정 및 고급 설정의 DLP 옵션](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="0bd43-340">고급 설정</span><span class="sxs-lookup"><span data-stu-id="0bd43-340">Advanced settings</span></span>

<span data-ttu-id="0bd43-341">사용자 지정 DLP 정책을 만들어야 하는 경우에는 **고급 설정 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-341">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="0bd43-342">고급 설정에서는 규칙 편집기를 사용하여 인스턴스 개수, 각 규칙의 일치 정확도(신뢰도 수준)를 비롯한 모든 옵션을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-342">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="0bd43-343">특정 장으로 건너뛰려면 규칙 편집기 상단의 탐색에 있는 항목을 클릭하여 해당 장으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-343">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP 규칙 편집기의 상단 탐색 모음](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="0bd43-345">DLP 정책 템플릿</span><span class="sxs-lookup"><span data-stu-id="0bd43-345">DLP policy templates</span></span>

<span data-ttu-id="0bd43-346">DLP 정책을 생성하는 첫 번째 단계는 보호할 정보를 선택하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-346">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="0bd43-347">DLP 템플릿을 사용하여 새로운 규칙 집합을 처음부터 새로 작성하고 기본적으로 포함해야 하는 정보 유형을 고민하는 데 필요한 시간이 단축됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-347">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="0bd43-348">그런 다음 조직의 특정 요구 사항에 맞게 해당 요구 사항을 추가하거나 수정하여 규칙을 미세 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-348">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="0bd43-349">미리 구성된 DLP 정책 템플릿은 HIPAA 데이터, PCI-DSS 데이터, 금융서비스 현대화법(Gramm-Leach-Bliley Act) 데이터 또는 고유 PII(개인 식별 정보)와 같은 특정 유형의 중요한 정보를 검색하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-349">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="0bd43-350">일반적인 유형의 중요한 정보를 쉽게 찾아 보호할 수 있도록 하기 위해 Microsoft 365에 포함된 정책 템플릿에는 이미 시작하는 데 필요한 가장 일반적인 중요한 정보 유형이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-350">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Microsoft 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![미국 애국자법을 위한 템플릿에 중점을 두는 데이터 손실 방지 정책에 대한 템플릿 목록](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="0bd43-352">조직에 고유한 요구 사항이 있을 경우 **사용자 지정 정책** 옵션을 선택하여 DLP 정책을 처음부터 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-352">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="0bd43-353">사용자 지정 정책은 비어 있으며, 미리 구성된 규칙이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-353">A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="0bd43-354">테스트 모드를 사용하여 점차적으로 DLP 정책 롤아웃</span><span class="sxs-lookup"><span data-stu-id="0bd43-354">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="0bd43-355">DLP 정책을 만든 후에는 완전히 적용하기 전에 서서히 롤아웃하면서 영향을 평가하고 효율성을 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-355">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="0bd43-356">예를 들어 새 DLP 정책으로 인해 사용자들이 작업을 완료하기 위해 액세스해야 하는 많은 문서에 대한 액세스를 실수로 차단하는 것을 원치 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-356">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="0bd43-357">영향이 클 수 있는 DLP 정책을 생성하는 경우에는 다음과 같은 순서를 따르는 것이 좋습니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-357">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="0bd43-358">**정책 팁이 없는 테스트 모드에서 시작** 하고 DLP 보고서 및 모든 사고 보고서를 사용하여 영향을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-358">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact.</span></span> <span data-ttu-id="0bd43-359">DLP 보고서를 사용하여 정책 일치의 횟수, 위치, 유형 및 심각도를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-359">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="0bd43-360">결과에 따라 필요에 맞게 규칙을 미세 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-360">Based on the results, you can fine tune the rules as needed.</span></span> <span data-ttu-id="0bd43-361">테스트 모드에서 DLP 정책은 조직에서 작업하는 사용자의 생산성에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-361">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="0bd43-p151">**알림 및 정책 팁을 사용하여 테스트 모드로 전환** 하여 사용자에게 규정 준수 정책을 교육하고 적용될 규칙을 준비하도록 할 수 있습니다. 이 단계에서 규칙을 미세 조정할 수 있도록 사용자에게 가양성을 보고하도록 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-p151">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="0bd43-364">규칙에서 작업이 적용되고 콘텐츠가 보호되도록 **정책에 대한 전체 적용을 시작합니다**.</span><span class="sxs-lookup"><span data-stu-id="0bd43-364">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected.</span></span> <span data-ttu-id="0bd43-365">DLP 보고서 및 모든 사고 보고서나 알림을 계속 모니터링하여 결과가 의도한 대로 나타나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-365">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 

    ![테스트 모드를 사용하고 정책을 설정하기 위한 옵션](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    <span data-ttu-id="0bd43-367">언제든지 DLP 정책을 종료할 수 있습니다. 이 경우 정책의 모든 규칙들이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-367">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="0bd43-368">하지만 규칙 편집기에서 상태를 전환하여 각 규칙을 개별적으로 종료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-368">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>

    ![정책에서 규칙을 종료하기 위한 옵션](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    <span data-ttu-id="0bd43-370">정책에서 여러 규칙의 우선 순위를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-370">You can also change the priority of multiple rules in a policy.</span></span> <span data-ttu-id="0bd43-371">이를 위해 편집할 정책을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-371">To do that, open a policy for editing.</span></span> <span data-ttu-id="0bd43-372">규칙의 행에서 줄임표(**...**)를 선택하고 **아래로 이동** 또는 **마지막 규칙 가져오기** 와 같은 옵션을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bd43-372">In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0bd43-373">![규칙 우선 순위 설정](../media/dlp-set-rule-priority.png)</span><span class="sxs-lookup"><span data-stu-id="0bd43-373">![Set rule priority](../media/dlp-set-rule-priority.png)</span></span>
  
## <a name="dlp-reports"></a><span data-ttu-id="0bd43-374">DLP 보고서</span><span class="sxs-lookup"><span data-stu-id="0bd43-374">DLP reports</span></span>

<span data-ttu-id="0bd43-375">DLP 정책을 만들고 설정한 후에는 의도한 대로 작동하는지와 규정 준수 상태를 유지하는 데 도움이 되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-375">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="0bd43-376">DLP 보고서를 사용하면 시간에 따른 DLP 정책 및 규칙 일치 수와 가양성 및 재정의 수를 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-376">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="0bd43-377">각 보고서에 대해 위치, 시간 프레임에 따라 일치하는 항목을 필터링할 수 있으며 특정 정책, 규칙 또는 작업으로 범위를 좁힐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-377">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="0bd43-378">DLP 보고서를 사용하면 비즈니스 통찰력을 얻고 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-378">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="0bd43-379">특정 기간에 초점을 맞추고 스파이크 및 추세의 이유를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-379">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="0bd43-380">조직의 규정 준수 정책을 위반하는 비즈니스 프로세스를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-380">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="0bd43-381">DLP 정책이 비즈니스에 미치는 영향을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-381">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="0bd43-382">또한 DLP 보고서를 사용하여 실행 중에 DLP 정책을 미세 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-382">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![보안 및 규정 준수 센터의 보고서 대시보드](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="0bd43-384">DLP 정책이 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="0bd43-384">How DLP policies work</span></span>

<span data-ttu-id="0bd43-p156">DLP는 심도 깊은 콘텐츠 분석(단순 텍스트 검색 아님)을 사용하여 중요한 정보를 검색합니다. 이 심도 깊은 콘텐츠 분석은 키워드 일치, 사전 일치, 정규식 평가, 내부 함수 및 기타 방법을 사용하여 DLP 정책과 일치하는 콘텐츠를 검색합니다. 잠재적으로 데이터의 일부만 중요한 것으로 간주됩니다. DLP 정책은 나머지 콘텐츠로 작업하는 사람들에게 영향을 주거나 작업을 지연시키지 않으면서 해당 데이터를 식별 및 모니터링하고 자동으로 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-p156">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="0bd43-389">정책이 동기화됨</span><span class="sxs-lookup"><span data-stu-id="0bd43-389">Policies are synced</span></span>

<span data-ttu-id="0bd43-390">보안 &amp; 규정 준수 센터에서 DLP 정책을 만든 후 정책은 중앙 정책 저장소에 저장되며 다음을 포함하는 다양한 콘텐츠 원본과 동기화합니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-390">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="0bd43-391">Exchange Online, 웹용 Outlook 및 Outlook.</span><span class="sxs-lookup"><span data-stu-id="0bd43-391">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
    
- <span data-ttu-id="0bd43-392">비즈니스용 OneDrive 사이트.</span><span class="sxs-lookup"><span data-stu-id="0bd43-392">OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="0bd43-393">SharePoint Online 사이트.</span><span class="sxs-lookup"><span data-stu-id="0bd43-393">SharePoint Online sites.</span></span>
    
- <span data-ttu-id="0bd43-394">Office 데스크톱 프로그램 (Excel, PowerPoint 및 Word).</span><span class="sxs-lookup"><span data-stu-id="0bd43-394">Office desktop programs (Excel, PowerPoint, and Word).</span></span>

- <span data-ttu-id="0bd43-395">Microsoft Teams 채널 및 채팅 메시지.</span><span class="sxs-lookup"><span data-stu-id="0bd43-395">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="0bd43-396">정책이 올바른 위치와 동기화된 후 콘텐츠를 평가하고 작업을 적용하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-396">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="0bd43-397">비즈니스용 OneDrive 및 SharePoint Online 사이트에서의 정책 평가</span><span class="sxs-lookup"><span data-stu-id="0bd43-397">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="0bd43-398">SharePoint Online 사이트 및 비즈니스용 OneDrive 사이트 전체에 걸쳐 문서는 지속적으로 변경됩니다. 즉 계속해서 생성되고, 편집되고, 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-398">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="0bd43-399">즉, 문서는 언제든지 DLP 정책과 충돌을 일으키거나 정책을 준수할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-399">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="0bd43-400">예를 들어 한 사람이 자신의 팀 사이트에 중요한 정보를 포함하지 않는 문서를 업로드할 수 있습니다. 하지만 후에 다른 사람이 같은 문서를 편집하고 중요한 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-400">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="0bd43-p158">이러한 이유로 DLP 정책은 백그라운드에서 문서의 정책 일치 여부를 자주 확인합니다. 이러한 검사를 비동기 정책 평가로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-p158">For this reason, DLP policies check documents for policy matches frequently in the background. You can think of this as asynchronous policy evaluation. </span></span><!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a><span data-ttu-id="0bd43-403">작업 방법</span><span class="sxs-lookup"><span data-stu-id="0bd43-403">How it works</span></span>
 
<span data-ttu-id="0bd43-404">사용자가 사이트에서 문서를 추가하거나 변경하면 검색 엔진에서 콘텐츠를 검색하여 나중에 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-404">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="0bd43-405">이 과정이 진행되는 동안 콘텐츠에 중요한 정보가 있는지 그리고 공유되고 있는지 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-405">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="0bd43-406">발견된 모든 중요한 정보는 검색 인덱스에 안전하게 저장되므로, 일반 사용자가 아닌 규정 준수 팀만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-406">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="0bd43-407">사용자가 설정한 각 DLP 정책은 백그라운드에서(비동기적) 실행되며 정책과 일치하는 모든 콘텐츠를 자주 검색하고 부주의한 누설이 일어나지 않도록 방지하는 작업을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-407">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![DLP 정책에서 콘텐츠를 비동기적으로 평가하는 방법을 보여주는 다이어그램](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --><span data-ttu-id="0bd43-p160"> 마지막으로 문서는 DLP 정책과 충돌할 수 있지만 DLP 정책을 준수할 수도 있습니다. 예를 들어 어떤 사람이 신용 카드 번호를 문서를 추가하는 경우 DLP 정책이 문서에 대한 액세스를 자동으로 차단할 수 있습니다. 하지만 나중에 이 사람이 중요한 정보를 제거하면 다음 번에 정책에 대해 문서가 평가될 때 작업(이 경우 차단)이 자동으로 실행 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-p160"> Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="0bd43-412">DLP는 인덱스를 지정할 수 있는 모든 콘텐츠를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-412">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="0bd43-413">기본적으로 크롤링되는 파일 형식에 대한 자세한 내용은 [SharePoint Server의 크롤링되는 기본 파일 이름의 확장명 및 구문 분석되는 파일 형식](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bd43-413">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>

> [!NOTE]
> <span data-ttu-id="0bd43-414">DLP 정책이 문서를 분석하기 전에 문서를 공유하지 못하게 하기 위해 콘텐츠가 인덱싱될 때까지 SharePoint 파일의 공유를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-414">In order to prevent documents from being shared before DLP policies had the opportunity to analyze them, sharing of new files in SharePoint can be blocked until its content has been indexed.</span></span> <span data-ttu-id="0bd43-415">자세한 내용은 [신규 파일을 기본으로 민감하게 설정하기](/sharepoint/sensitive-by-default)를 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd43-415">See, [Mark new files as sensitive by default](/sharepoint/sensitive-by-default) for detailed information.</span></span> 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="0bd43-416">Exchange, Outlook 및 웹 상 Outlook의 정책 평가</span><span class="sxs-lookup"><span data-stu-id="0bd43-416">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="0bd43-417">Exchange Online을 위치로 포함 하는 DLP 정책을 만드는 경우 해당 정책은 Office 365 보안 &amp; 준수 센터에서 Exchange Online으로 동기화 된 후 Exchange Online에서 웹 상 Outlook 및 Outlook으로 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-417">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="0bd43-418">Outlook에서 메시지를 작성할 때 생성 중인 콘텐츠가 DLP 정책을 기준으로 평가됨에 따라 사용자에게 정책 팁이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-418">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="0bd43-419">메시지가 발생하면 정상적인 메일 흐름의 일부로서 DLP 정책을 기준으로 평가되며, 이와 함께 Exchange 메일 흐름 규칙(전송 규칙이라고도 함)과 Exchange 관리 센터에서 생성된 DLP 정책을 기준으로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-419">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="0bd43-420">DLP 정책은 메시지와 첨부 파일을 모두 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-420">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="0bd43-421">Office 데스크톱 프로그램의 정책 평가</span><span class="sxs-lookup"><span data-stu-id="0bd43-421">Policy evaluation in the Office desktop programs</span></span>

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
<span data-ttu-id="0bd43-422">Excel, PowerPoint 및 Word에는 중요한 정보를 식별하고 DLP 정책을 적용하는 SharePoint Online 및 비즈니스용 OneDrive와 동일한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-422">Excel, PowerPoint, and Word include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="0bd43-423">해당 Office 프로그램은 중앙 정책 저장소에서 직접 해당 DLP 정책을 동기화한 후 사용자들이 DLP 정책에 포함된 사이트에서 연 문서로 작업할 때 DLP 정책을 기준으로 콘텐츠를 지속적으로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-423">These Office programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="0bd43-424">Office의 DLP 정책 평가는 해당 콘텐츠를 사용하는 프로그램의 성능이나 사용자의 생산성에 영향을 미치지 않도록 고안되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-424">DLP policy evaluation in Office is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="0bd43-425">규모가 큰 문서에서 작업 중이거나 사용자의 컴퓨터가 다른 작업 중인 경우 정책 팁이 표시되는 데 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-425">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="0bd43-426">Microsoft Teams의 정책 평가</span><span class="sxs-lookup"><span data-stu-id="0bd43-426">Policy evaluation in Microsoft Teams</span></span>
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

<span data-ttu-id="0bd43-427">Microsoft Teams를 위치로 포함하는 DLP 정책을 만드는 경우 해당 정책은 Office 365 보안 &amp; 준수 센터에서 사용자 계정 및 Microsoft Teams 채널과 채팅 메시지와 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-427">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="0bd43-428">DLP 정책을 구성 하는 방법에 따라 제3자가 Microsoft Teams 채팅 또는 채널 메시지에서 중요한 정보를 공유하려고 시도하는 경우 메시지가 차단되거나 취소될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-428">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="0bd43-429">그리고 중요한 정보를 포함하고 게스트(외부 사용자)와 공유되는 문서가 해당 사용자에게 열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-429">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="0bd43-430">더 자세한 내용은 [데이터 손실 방지 및 Microsoft Teams](dlp-microsoft-teams.md)를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bd43-430">To learn more, see [Data loss prevention and Microsoft Teams](dlp-microsoft-teams.md).</span></span>
 
## <a name="permissions"></a><span data-ttu-id="0bd43-431">사용 권한</span><span class="sxs-lookup"><span data-stu-id="0bd43-431">Permissions</span></span>

<span data-ttu-id="0bd43-432">DLP 정책을 만드는 규정 준수 팀의 구성원에게는 보안 &amp; 준수 센터에 대한 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-432">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="0bd43-433">기본적으로 테넌트 관리자는 해당 위치에 액세스할 수 있으며, 테넌트 관리자의 사용 권한을 모두 주지 않으면서 준수 관리자 및 기타 사용자에게 보안 &amp; 준수 센터에 대한 액세스 권한을 부여할 수 있습니다. 이를 위해, 다음의 단계가 권장됩니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-433">By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="0bd43-434">Microsoft 365에서 그룹을 생성하고 규정 준수 책임자를 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bd43-434">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="0bd43-435">보안 &amp; 준수 센터의 **사용 권한** 페이지에서 역할 그룹을 생성하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bd43-435">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="0bd43-436">역할 그룹을 만드는 동안 **역할 선택** 섹션을 사용하여 역할 그룹에 **DLP 준수 관리** 역할을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-436">While creating the role group, use the **Choose Roles** section to add the following role to the Role Group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="0bd43-437">**구성원 선택** 섹션을 사용하여 이전에 만든 Microsoft 365 그룹을 역할 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-437">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="0bd43-438">**보기 전용 DLP 준수 관리** 역할을 부여하여 DLP 정책 및 DLP 보고서에 대한 보기 전용 권한이 있는 역할 그룹을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-438">You can also create a role group with view-only privileges to the DLP policies and DLP reports by granting the **View-Only DLP Compliance Management** role.</span></span>

<span data-ttu-id="0bd43-439">더 자세한 내용은 [Office 365 준수 센터 액세스 권한 부여하기](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bd43-439">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="0bd43-p168">이러한 정책은 DLP 정책을 만들고 적용하는 데만 필요합니다. 정책 적용을 위해서는 콘텐츠에 액세스하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-p168">These permissions are required only to create and apply a DLP policy. Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="0bd43-442">DLP cmdlet 찾기</span><span class="sxs-lookup"><span data-stu-id="0bd43-442">Find the DLP cmdlets</span></span>

<span data-ttu-id="0bd43-443">대부분의 보안 &amp; 준수 센터용 cmdlet을 사용하려면 다음의 단계를 따르십시오:</span><span class="sxs-lookup"><span data-stu-id="0bd43-443">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. <span data-ttu-id="0bd43-444">[원격 PowerShell을 사용하여 Office 365 보안 &amp; 준수 센터에 연결](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="0bd43-444">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="0bd43-445">이 [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection) 중 하나를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bd43-445">Use any of these [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span></span>
    
<span data-ttu-id="0bd43-446">하지만 DLP 보고서에서는 Exchange Online을 포함한 Microsoft 365에서 데이터를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-446">However, DLP reports need pull data from across Microsoft 365, including Exchange Online.</span></span> <span data-ttu-id="0bd43-447">이러한 이유로 **DLP 보고서용 cmdlet은 보안 &amp; 준수 센터 Powershell이 아닌 Exchange Online Powershell에서 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0bd43-447">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="0bd43-448">따라서 DLP 보고서용 cmdlet을 사용하려면 다음의 단계가 필요합니다:</span><span class="sxs-lookup"><span data-stu-id="0bd43-448">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. <span data-ttu-id="0bd43-449">[원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd43-449">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="0bd43-450">다음과 같은 DLP 보고서용 cmdlet 중 하나 사용</span><span class="sxs-lookup"><span data-stu-id="0bd43-450">Use any of these cmdlets for the DLP reports:</span></span>
    
    - [<span data-ttu-id="0bd43-451">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="0bd43-451">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [<span data-ttu-id="0bd43-452">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="0bd43-452">Get-DlpDetailReport</span></span>](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a><span data-ttu-id="0bd43-453">추가 정보</span><span class="sxs-lookup"><span data-stu-id="0bd43-453">More information</span></span>

- [<span data-ttu-id="0bd43-454">서식 파일에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0bd43-454">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="0bd43-455">DLP 정책에 대한 알림을 보내고 정책 팁 표시</span><span class="sxs-lookup"><span data-stu-id="0bd43-455">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="0bd43-456">FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0bd43-456">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="0bd43-457">DLP 정책 템플릿에 포함되는 내용</span><span class="sxs-lookup"><span data-stu-id="0bd43-457">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="0bd43-458">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="0bd43-458">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="0bd43-459">DLP 함수가 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="0bd43-459">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="0bd43-460">사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="0bd43-460">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)

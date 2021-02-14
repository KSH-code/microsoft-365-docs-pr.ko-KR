---
title: 템플릿에서 DLP 정책 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
description: 이 문서에서는 Office 365에 포함된 템플릿 중 하나를 사용하여 DLP 정책을 만드는 방법을 배우게 됩니다.
ms.openlocfilehash: 612f6d0c9459c31087bafa5c498bd4767535e169
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327810"
---
# <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="fc378-103">템플릿에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="fc378-103">Create a DLP policy from a template</span></span>

<span data-ttu-id="fc378-104">DLP 정책을 사용하여 가장 쉽고 가장 일반적인 방법은 Office 365에 포함된 템플릿 중 하나를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-104">The easiest, most common way to get started with DLP policies is to use one of the templates included in Office 365.</span></span> <span data-ttu-id="fc378-105">이러한 템플릿 중 하나를 있는 대로 사용하거나 조직의 특정 규정 준수 요구 사항에 맞게 규칙을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-105">You can use one of these templates as is, or customize the rules to meet your organization's specific compliance requirements.</span></span>
  
<span data-ttu-id="fc378-106">Microsoft 365에는 광범위한 일반적인 규제 및 비즈니스 정책 요구를 충족하는 데 도움이 될 수 있는 40개가 넘는 즉시 사용 템플릿이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-106">Microsoft 365 includes over 40 ready-to-use templates that can help you meet a wide range of common regulatory and business policy needs.</span></span> <span data-ttu-id="fc378-107">예를 들어 다음에 대한 DLP 정책 템플릿이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-107">For example, there are DLP policy templates for:</span></span>
  
- <span data-ttu-id="fc378-108">GLBA(Gramm-Leach-Bliley Act)</span><span class="sxs-lookup"><span data-stu-id="fc378-108">Gramm-Leach-Bliley Act (GLBA)</span></span>
    
- <span data-ttu-id="fc378-109">PCI-DSS(Payment Card Industry Data Security Standard)</span><span class="sxs-lookup"><span data-stu-id="fc378-109">Payment Card Industry Data Security Standard (PCI-DSS)</span></span>
    
- <span data-ttu-id="fc378-110">U.S. PII(United States Personally Identifiable Information)</span><span class="sxs-lookup"><span data-stu-id="fc378-110">United States Personally Identifiable Information (U.S. PII)</span></span>
    
- <span data-ttu-id="fc378-111">미국 HIPAA(Health Insurance Act)</span><span class="sxs-lookup"><span data-stu-id="fc378-111">United States Health Insurance Act (HIPAA)</span></span>
    
<span data-ttu-id="fc378-p103">기존 규칙을 수정하거나 새로 추가하여 템플릿을 미세 조정할 수 있습니다. 예를 들어 새로운 유형의 중요한 정보를 규칙에 추가하거나, 한 규칙의 템플릿 수를 수정하여 트리거하기 더 어렵게 또는 더 쉽게 만들거나, 업무 정당성을 제공하여 규칙의 작업을 재정의할 수 있도록 하거나, 알림 및 사고 보고서를 받을 수 있는 사람을 변경할 수 있습니다. DLP 정책 템플릿은 여러 일반적인 규정 준수 시나리오에 대한 유연한 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-p103">You can fine tune a template by modifying any of the existing rules or adding new ones. For example, you can add new types of sensitive information to a rule, modify the counts in a rule to make it harder or easier to trigger, allow people to override the actions in a rule by providing a business justification, or change who notifications and incident reports are sent to. A DLP policy template is a flexible starting point for many common compliance scenarios.</span></span>
  
<span data-ttu-id="fc378-115">기본 규칙이 없는 사용자 지정 템플릿을 선택하고, 조직의 특정 규정 준수 요구에 맞게 DLP 정책을 처음부터 새로 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-115">You can also choose the Custom template, which has no default rules, and configure your DLP policy from scratch, to meet the specific compliance requirements for your organization.</span></span>
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a><span data-ttu-id="fc378-116">예: 모든 비즈니스용 OneDrive 사이트에서 중요한 정보를 식별하고 조직 외부의 사용자에 대한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="fc378-116">Example: Identify sensitive information across all OneDrive for Business sites and restrict access for people outside your organization</span></span>

<span data-ttu-id="fc378-117">비즈니스용 OneDrive 계정을 통해 조직의 사용자들이 문서를 쉽게 공동 작업하고 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-117">OneDrive for Business accounts make it easy for people across your organization to collaborate and share documents.</span></span> <span data-ttu-id="fc378-118">그러나 규정 준수 책임자는 비즈니스용 OneDrive 계정에 저장된 중요한 정보가 조직 외부의 사용자와 부재 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-118">But a common concern for compliance officers is that sensitive information stored in OneDrive for Business accounts may be inadvertently shared with people outside your organization.</span></span> <span data-ttu-id="fc378-119">DLP 정책은 이러한 위험을 줄이는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-119">A DLP policy can help mitigate this risk.</span></span>
  
<span data-ttu-id="fc378-120">이 예에서는 ITIN(개별 납세자 번호), 사회 보장 번호 및 미국 여권 번호를 포함하는 미국 PII 데이터를 식별하는 DLP 정책을 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-120">In this example, you'll create a DLP policy that identifies U.S. PII data, which includes Individual Taxpayer Identification Numbers (ITIN), Social Security Numbers, and U.S. passport numbers.</span></span> <span data-ttu-id="fc378-121">템플릿을 사용하여 시작한 다음 조직의 규정 준수 요구 사항을 충족하도록 템플릿을 수정합니다. 특히 다음과 같은 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-121">You'll get started by using a template, and then you'll modify the template to meet your organization's compliance requirements—specifically, you'll:</span></span>
  
- <span data-ttu-id="fc378-122">DLP 정책이 훨씬 더 많은 중요한 데이터를 보호할 수 있도록 미국 은행 계좌 번호와 미국 운전 면허 번호 등 몇 가지 중요한 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-122">Add a couple of types of sensitive information—U.S. bank account numbers and U.S. driver's license numbers—so that the DLP policy protects even more of your sensitive data.</span></span>
    
- <span data-ttu-id="fc378-123">중요한 정보를 한 번만 발생하면 외부 사용자의 액세스를 제한할 수 있도록 정책을 보다 민감하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-123">Make the policy more sensitive, so that a single occurrence of sensitive information is enough to restrict access for external users.</span></span>
    
- <span data-ttu-id="fc378-124">업무 정당성을 제공하거나 가양성을 보고하여 작업을 재정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-124">Allow users to override the actions by providing a business justification or reporting a false positive.</span></span> <span data-ttu-id="fc378-125">이렇게 하면 중요한 정보를 공유하기 위한 유효한 업무 이유가 있는 경우 DLP 정책은 조직의 사용자가 작업을 완료하는 것을 방지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-125">This way, your DLP policy won't prevent people in your organization from getting their work done, provided they have a valid business reason for sharing the sensitive information.</span></span>
    
### <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="fc378-126">템플릿에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="fc378-126">Create a DLP policy from a template</span></span>

1. <span data-ttu-id="fc378-127">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-127">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="fc378-128">회사 또는 학교 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-128">Sign in using your work or school account.</span></span> <span data-ttu-id="fc378-129">이제 보안 준수 &amp; 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-129">You're now in the Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="fc378-130">보안 준수 센터 왼쪽 &amp; \> 탐색 데이터 손실 \> **방지** \> **정책** \> **+ 정책 만들기**</span><span class="sxs-lookup"><span data-stu-id="fc378-130">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![정책 단추 만들기](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="fc378-132">다음에 필요한 중요한 정보 유형을 보호하는 DLP 정책 템플릿을 \> **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="fc378-132">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="fc378-133">이 예에서는 보호하려는  대부분의 중요한 정보 유형이 이미 포함되어 있기 때문에 개인 정보 보호 \> **미국 PII(개인** 식별 정보) 데이터를 선택합니다. 나중에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-133">In this example, you'll select **Privacy** \> **U.S. Personally Identifiable Information ‎(PII)‎ Data** because it already includes most of the types of sensitive information that you want to protect—you'll add a couple later.</span></span> 
    
    <span data-ttu-id="fc378-134">템플릿을 선택하면 오른쪽의 설명을 읽고 템플릿이 보호하는 중요한 정보의 유형을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-134">When you select a template, you can read the description on the right to learn what types of sensitive information the template protects.</span></span>
    
    ![DLP 정책 템플릿 선택 페이지](../media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. <span data-ttu-id="fc378-136">정책 이름을 \> 다음으로 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-136">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="fc378-137">DLP 정책이 보호할 위치를 선택하려는 경우 다음 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-137">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="fc378-138">Choose **All locations in Office 365** \> **Next.**</span><span class="sxs-lookup"><span data-stu-id="fc378-138">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="fc378-139">Choose **Let me choose specific locations** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="fc378-139">Choose **Let me choose specific locations** \> **Next**.</span></span> <span data-ttu-id="fc378-140">이 예제에서는 이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-140">For this example, choose this.</span></span>
    
    <span data-ttu-id="fc378-141">모든 Exchange 전자 메일 또는 모든 OneDrive 계정과 같은  전체 위치를 포함하거나 제외하기 위해 해당 위치의 상태를 켜거나 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-141">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="fc378-142">특정 SharePoint 사이트 또는 비즈니스용 OneDrive 계정만 포함하려면 상태를 켜고  포함 아래의 링크를 클릭하여 특정 사이트 또는 계정을 선택하세요. </span><span class="sxs-lookup"><span data-stu-id="fc378-142">To include only specific SharePoint sites or OneDrive for Business accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> <span data-ttu-id="fc378-143">사이트에 정책을 적용하면 해당 정책에 구성된 규칙이 해당 사이트의 모든 하위 사이트에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-143">When you apply a policy to a site, the rules configured in that policy are automatically applied to all subsites of that site.</span></span> 
    
    ![DLP 정책을 적용할 수 있는 위치에 대한 옵션](../media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    <span data-ttu-id="fc378-145">이 예에서는 모든 비즈니스용 OneDrive 계정에 저장된 중요한 정보를  보호하기 위해 **Exchange** 전자 메일 및  **SharePoint** 사이트에 대한 상태를 해제하고 **OneDrive** 계정에 대해 상태를 그대로 떠야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-145">In this example, to protect sensitive information stored in all OneDrive for Business accounts, turn off the **Status** for both **Exchange email** and **SharePoint sites**, and leave the **Status** on for **OneDrive accounts**.</span></span>
    
7. <span data-ttu-id="fc378-146">Choose **Use advanced settings** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="fc378-146">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="fc378-147">DLP 정책 템플릿에는 특정 유형의 중요한 정보를 검색하는 조건과 그에 따른 작업이 미리 정의된 규칙이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-147">A DLP policy template contains predefined rules with conditions and actions that detect and act upon specific types of sensitive information.</span></span> <span data-ttu-id="fc378-148">기존 규칙을 편집, 삭제 또는 해제하거나 새 규칙을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-148">You can edit, delete, or turn off any of the existing rules, or add new ones.</span></span> <span data-ttu-id="fc378-149">완료되면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-149">When done, click **Next**.</span></span>
    
    ![미국 PII 정책 템플릿에서 확장된 규칙](../media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    <span data-ttu-id="fc378-151">이 예제에서는 미국 PII 데이터 템플릿에 미리 정의된 두 가지 규칙이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-151">In this example, the U.S. PII Data template includes two predefined rules:</span></span>
    
  - <span data-ttu-id="fc378-152">**미국 PII가 검색된 콘텐츠의 양이 적습니다.** 이 규칙은 세 가지 유형의 중요한 정보(ITIN, SSN 및 미국 여권 번호)의 1-10회가 포함된 파일을 검색합니다. 여기서 파일은 조직 외부의 사용자와 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-152">**Low volume of content detected U.S. PII** This rule looks for files containing between 1 and 10 occurrences of each of three types of sensitive information (ITIN, SSN, and U.S. passport numbers), where the files are shared with people outside the organization.</span></span> <span data-ttu-id="fc378-153">찾은 경우 규칙은 기본 사이트 모음 관리자, 문서 소유자 및 문서를 마지막으로 수정한 사람에 대해 전자 메일 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-153">If found, the rule sends an email notification to the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
  - <span data-ttu-id="fc378-154">**미국 PII에서 검색된 대량의 콘텐츠** 이 규칙은 동일한 세 가지 중요한 정보 유형 각각이 10개 이상 포함된 파일을 검색합니다. 여기서 파일은 조직 외부의 사용자와 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-154">**High volume of content detected U.S. PII** This rule looks for files containing 10 or more occurrences of each of the same three sensitive information types, where the files are shared with people outside the organization.</span></span> <span data-ttu-id="fc378-155">이 작업이 발견된 경우 전자 메일 알림을 보내고 파일에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-155">If found, this action also sends an email notification, plus it restricts access to the file.</span></span> <span data-ttu-id="fc378-156">비즈니스용 OneDrive 계정의 콘텐츠의 경우 기본 사이트 모음 관리자, 문서 소유자 및 문서를 마지막으로 수정한 사람을 제외한 모든 사용자에 대해 문서 사용 권한이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-156">For content in a OneDrive for Business account, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
    <span data-ttu-id="fc378-157">조직의 특정 요구 사항을 충족하기 위해 중요한 정보를 한 번만 발생하면 외부 사용자의 액세스를 차단할 수 있도록 규칙을 보다 쉽게 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-157">To meet your organization's specific requirements, you may want to make the rules easier to trigger, so that a single occurrence of sensitive information is enough to block access for external users.</span></span> <span data-ttu-id="fc378-158">이러한 규칙을 보고 나면 낮은 수 및 높은 수 규칙이 필요하지 않습니다. 중요한 정보가 발견된 경우 액세스를 차단하는 단일 규칙만 필요하다는 것을 이해하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-158">After looking at these rules, you understand that you don't need low and high count rules—you need only a single rule that blocks access if any occurrence of sensitive information is found.</span></span>
    
    <span data-ttu-id="fc378-159">따라서 검색된 미국 **PII 삭제** 규칙의 콘텐츠 양이 적은 규칙을 \> **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-159">So you expand the rule named **Low volume of content detected U.S. PII** \> **Delete rule**.</span></span>
    
    ![규칙 삭제 단추](../media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. <span data-ttu-id="fc378-161">이제 이 예에서는 두 가지 중요한 정보 유형(미국 은행 계좌 번호 및 미국 운전 면허 번호)을 추가하고, 사용자가 규칙을 다시 정하고, 횟수를 원하는 수로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-161">Now, in this example, you need to add two sensitive information types (U.S. bank account numbers and U.S. driver's license numbers), allow people to override a rule, and change the count to any occurrence.</span></span> <span data-ttu-id="fc378-162">하나의 규칙을 편집하여 이 모든 작업을 할 수 있으므로 미국 **PII** 편집 규칙을 검색한 많은 콘텐츠의 \> **양을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-162">You can do all of this by editing one rule, so select **High volume of content detected U.S. PII** \> **Edit rule**.</span></span>
    
    ![규칙 편집 단추](../media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. <span data-ttu-id="fc378-164">중요한 정보 유형을 추가하기 위해 **조건** 섹션에서 유형을 \> **추가하거나 변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-164">To add a sensitive information type, in the **Conditions** section \> **Add or change types**.</span></span> <span data-ttu-id="fc378-165">그런 다음 **추가** 또는 변경 유형에서 선택된 미국 은행 계좌 번호 및 미국 운전 면허 번호 추가 완료를 \>  \>   \>  \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-165">Then, under **Add or change types** \> choose **Add** \> select **U.S. Bank Account Number** and **U.S. Driver's License Number** \> **Add** \> **Done**.</span></span>
    
    ![형식 추가 또는 변경 옵션](../media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![유형 추가 또는 변경 창](../media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. <span data-ttu-id="fc378-168">횟수(규칙을 트리거하는 데 필요한 중요한 정보의 인스턴스 수)를 변경하려면 인스턴스 수에서 각 유형에 대한  \> **최소값을** \> 1로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-168">To change the count (the number of instances of sensitive information required to trigger the rule), under **Instance count** \> choose the **min** value for each type \> enter 1.</span></span> <span data-ttu-id="fc378-169">최소 개수는 비어 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-169">The minimum count cannot be empty.</span></span> <span data-ttu-id="fc378-170">최대 개수는 비어 있을 수 있습니다. 빈 **최대값이** 모든 값으로 **변환됩니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-170">The maximum count can be empty; an empty **max** value convert to **any**.</span></span>
    
    <span data-ttu-id="fc378-171">완료되면 모든 중요한 정보 유형에 대한 최소 개수는 **1로,** 최대 개수는 **1이 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-171">When finished, the min count for all of the sensitive information types should be **1** and the max count should be **any**.</span></span> <span data-ttu-id="fc378-172">즉, 이러한 유형의 중요한 정보가 발생하면 이 조건이 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-172">In other words, any occurrence of this type of sensitive information will satisfy this condition.</span></span>
    
    ![중요한 정보 유형에 대한 인스턴스 수](../media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. <span data-ttu-id="fc378-174">최종 사용자 지정의 경우, DLP 정책이 유효한 업무 정당성 또는 가긍성에 있는 경우 사용자의 작업을 차단하지 못하도록 하여 사용자 알림에 차단 작업을 다시 정의하는 옵션을 포함하도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="fc378-174">For the final customization, you don't want your DLP policies to block people from doing their work when they have a valid business justification or encounter a false positive, so you want the user notification to include options to override the blocking action.</span></span>
    
    <span data-ttu-id="fc378-175">사용자 **알림 섹션에서** 템플릿에서 이 규칙에 대해 기본적으로 전자 메일 알림 및 정책 팁이 켜져 있는지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-175">In the **User notifications** section, you can see that email notifications and policy tips are turned on by default for this rule in the template.</span></span> 
    
    <span data-ttu-id="fc378-176">사용자  다시 설정 섹션에서 비즈니스 정당성에 대한 오버라이드가 켜져 있지만 가짓 긍정을 보고하는 다시는 설정되지 않는지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-176">In the **User overrides** section, you can see that overrides for a business justification are turned on, but overrides to report false positives are not.</span></span> <span data-ttu-id="fc378-177">가짓 **긍정으로** 보고하는 경우 자동으로 규칙을 다시 저지합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-177">Choose **Override the rule automatically if they report it as a false positive**.</span></span>
    
    ![사용자 알림 섹션 및 사용자 overrides 섹션](../media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. <span data-ttu-id="fc378-179">규칙 편집기 위쪽에서 이 규칙의 이름을 미국 **PII로** 검색된 기본 대량 콘텐츠에서 미국 **PII로** 검색된 모든 콘텐츠로 변경합니다. 이 콘텐츠는 중요한 정보 유형의 발생에 의해 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-179">At the top of the rule editor, change the name of this rule from the default **High volume of content detected U.S. PII** to **Any content detected with U.S. PII** because it's now triggered by any occurrence of its sensitive information types.</span></span> 
    
14. <span data-ttu-id="fc378-180">규칙 편집기 저장의 맨 \> **아래에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-180">At the bottom of the rule editor \> **Save**.</span></span>
    
15. <span data-ttu-id="fc378-181">다음으로 이 규칙에 대한 조건 및 작업을 \> **검토합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-181">Review the conditions and actions for this rule \> **Next**.</span></span>
    
    <span data-ttu-id="fc378-182">오른쪽에서 규칙에 대한 **상태** 스위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-182">On the right, notice the **Status** switch for the rule.</span></span> <span data-ttu-id="fc378-183">전체 정책을 해제하면 정책에 포함된 모든 규칙도 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-183">If you turn off an entire policy, all rules contained in the policy are also turned off.</span></span> <span data-ttu-id="fc378-184">그러나 여기서 전체 정책을 해제하지 않고 특정 규칙을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-184">However, here you can turn off a specific rule without turning off the entire policy.</span></span> <span data-ttu-id="fc378-185">이 기능은 많은 수의 가양성을 생성하는 규칙을 조사해야 할 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-185">This can be useful when you need to investigate a rule that is generating a large number of false positives.</span></span> 
    
16. <span data-ttu-id="fc378-186">다음 페이지에서 다음을 읽고 이해하고 규칙을 끄거나 먼저 테스트할지 \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-186">On the next page, read and understand the following, and then choose whether to turn on the rule or test it out first \> **Next**.</span></span>
    
     <span data-ttu-id="fc378-187">DLP 정책을 만들기 전에, 완전히 적용하지 않은 상태에서 서서히 롤아웃하면서 영향을 평가하고 효율성을 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-187">Before you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before you fully enforce them.</span></span> <span data-ttu-id="fc378-188">예를 들어 새 DLP 정책으로 사용자들이 작업을 완료하는 데 필요한 수천 개의 문서에 대한 액세스를 의도치 않은 것으로 차단하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-188">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require to get their work done.</span></span> 
    
    <span data-ttu-id="fc378-189">영향이 클 수 있는 DLP 정책을 생성하는 경우에는 다음과 같은 순서를 따르는 것이 좋습니다:</span><span class="sxs-lookup"><span data-stu-id="fc378-189">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
    
17. <span data-ttu-id="fc378-p121">정책 설명이 없는 테스트 모드에서 시작하고 DLP 보고서를 사용하여 영향을 평가합니다. DLP 보고서를 사용하여 정책 일치의 횟수, 위치, 유형 및 심각도를 확인할 수 있습니다. 결과에 따라 필요에 맞게 규칙을 미세 조정할 수 있습니다. 테스트 모드에서 DLP 정책은 조직에서 작업하는 사용자의 생산성에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-p121">Start in test mode without Policy Tips and then use the DLP reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
18. <span data-ttu-id="fc378-p122">알림 및 정책 팁을 사용하여 테스트 모드로 전환하여 사용자에게 규정 준수 정책을 교육하고 적용될 규칙을 준비하도록 할 수 있습니다. 이 단계에서 규칙을 미세 조정할 수 있도록 사용자에게 가양성을 보고하도록 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-p122">Move to Test mode with notifications and Policy Tips so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span>
    
19. <span data-ttu-id="fc378-196">규칙이 적용되어 콘텐츠가 보호될 수 있도록 정책을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-196">Turn on the policies so that the rules are enforced and the content's protected.</span></span> <span data-ttu-id="fc378-197">DLP 보고서 및 모든 사고 보고서나 알림을 계속 모니터링하여 결과가 의도한 대로 나타나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-197">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
    ![테스트 모드를 사용하고 정책을 설정하기 위한 옵션](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. <span data-ttu-id="fc378-199">이 정책에 대한 설정을 검토하고 \> 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-199">Review your settings for this policy \> choose **Create**.</span></span>
    
<span data-ttu-id="fc378-200">DLP 정책을 만들고 켜면 해당 정책이 해당 콘텐츠에 대한 규칙을 자동으로 적용하기 시작하는 SharePoint Online 사이트 또는 비즈니스용 OneDrive 계정과 같은 포함된 모든 콘텐츠 원본에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-200">After you create and turn on a DLP policy, it's deployed to any content sources that it includes, such as SharePoint Online sites or OneDrive for Business accounts, where the policy begins automatically enforcing its rules on that content.</span></span>
  
## <a name="view-the-status-of-a-dlp-policy"></a><span data-ttu-id="fc378-201">DLP 정책의 상태 보기</span><span class="sxs-lookup"><span data-stu-id="fc378-201">View the status of a DLP policy</span></span>

<span data-ttu-id="fc378-202">보안 준수 센터의 데이터 손실 방지 섹션에서  정책 페이지에서  DLP 정책의 상태를 볼 &amp; 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-202">At any time, you can view the status of your DLP policies on the **Policy** page in the **Data loss prevention** section of the Security &amp; Compliance Center.</span></span> <span data-ttu-id="fc378-203">여기에서 정책이 제대로 사용 또는 사용되지 않도록 설정되었는지 여부, 정책이 테스트 모드인지 여부 등의 중요 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-203">Here you can find important information, such as whether a policy was successfully enabled or disabled, or whether the policy is in test mode.</span></span> 
  
<span data-ttu-id="fc378-204">아래에는 기타 상태와 해당 의미가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-204">Here are the different statuses and what they mean.</span></span>
  
|<span data-ttu-id="fc378-205">**상태**</span><span class="sxs-lookup"><span data-stu-id="fc378-205">**Status**</span></span>|<span data-ttu-id="fc378-206">**설명**</span><span class="sxs-lookup"><span data-stu-id="fc378-206">**Explanation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fc378-207">**켜는 중…**</span><span class="sxs-lookup"><span data-stu-id="fc378-207">**Turning on…**</span></span> <br/> |<span data-ttu-id="fc378-p125">정책이 포함하는 콘텐츠 원본으로 배포 중입니다. 정책이 아직 모든 원본에 적용되지는 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-p125">The policy is being deployed to the content sources that it includes. The policy is not yet enforced on all sources.</span></span>  <br/> |
|<span data-ttu-id="fc378-210">**테스트 중(알림 사용)**</span><span class="sxs-lookup"><span data-stu-id="fc378-210">**Testing, with notifications**</span></span> <br/> |<span data-ttu-id="fc378-p126">정책이 테스트 모드입니다. 규칙의 작업이 적용되지 않지만 정책 일치 항목은 수집되고 DLP 보고서를 사용하여 볼 수 있습니다. 정책 일치 항목에 대한 알림이 지정된 받는 사람에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-p126">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="fc378-214">**테스트 중(알림 사용 안 함)**</span><span class="sxs-lookup"><span data-stu-id="fc378-214">**Testing, without notifications**</span></span> <br/> |<span data-ttu-id="fc378-p127">정책이 테스트 모드입니다. 규칙의 작업이 적용되지 않지만 정책 일치 항목은 수집되고 DLP 보고서를 사용하여 볼 수 있습니다. 정책 일치 항목에 대한 알림이 지정된 받는 사람에게 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-p127">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are not sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="fc378-218">**켜짐**</span><span class="sxs-lookup"><span data-stu-id="fc378-218">**On**</span></span> <br/> |<span data-ttu-id="fc378-p128">정책이 활성 상태이며 적용됩니다. 정책이 모든 콘텐츠 원본으로 배포되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-p128">The policy is active and enforced. The policy was successfully deployed to all its content sources.</span></span>  <br/> |
|<span data-ttu-id="fc378-221">**끄는 중...**</span><span class="sxs-lookup"><span data-stu-id="fc378-221">**Turning off…**</span></span> <br/> |<span data-ttu-id="fc378-p129">정책이 포함하는 콘텐츠 원본에서 제거 중입니다. 정책이 여전히 활성 상태이며 일부 원본에 적용될 수 있습니다. 정책을 끄는 데 45시간까지 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-p129">The policy is being removed from the content sources that it includes. The policy may still be active and enforced on some sources. Turning off a policy may take up to 45 minutes.</span></span>  <br/> |
|<span data-ttu-id="fc378-225">**끄기**</span><span class="sxs-lookup"><span data-stu-id="fc378-225">**Off**</span></span> <br/> |<span data-ttu-id="fc378-p130">정책이 활성 상태가 아니며 적용되지 않습니다. 정책에 대한 설정(원본, 키워드, 기간 등)은 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-p130">The policy is not active and not enforced. The settings for the policy (sources, keywords, duration, etc) are saved.</span></span>  <br/> |
|<span data-ttu-id="fc378-228">**삭제...**</span><span class="sxs-lookup"><span data-stu-id="fc378-228">**Deleting…**</span></span> <br/> |<span data-ttu-id="fc378-229">정책이 삭제되는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-229">The policy is in the process of being deleted.</span></span> <span data-ttu-id="fc378-230">정책이 활성 상태가 아니며 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-230">The policy is not active and not enforced.</span></span> <span data-ttu-id="fc378-231">일반적으로 정책을 삭제하는 데 1시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-231">It normally takes an hour for a policy to delet</span></span> <br/> |
   
## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="fc378-232">DLP 정책 끄기</span><span class="sxs-lookup"><span data-stu-id="fc378-232">Turn off a DLP policy</span></span>

<span data-ttu-id="fc378-233">DLP 정책을 편집하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-233">You can edit or turn off a DLP policy at any time.</span></span> <span data-ttu-id="fc378-234">정책을 끄면 정책의 모든 규칙이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-234">Turning off a policy disables all of the rules in the policy.</span></span>
  
<span data-ttu-id="fc378-235">DLP 정책을 편집하거나 해제하려면 정책  페이지에서 정책 편집 \> 정책을 \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc378-235">To edit or turn off a DLP policy, on the **Policy** page \> select the policy \> **Edit policy**.</span></span>
  
![정책 편집 단추](../media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
<span data-ttu-id="fc378-237">또한 위에서 설명한 대로 정책을 편집한 다음 해당 규칙의 상태를  해제하여 각 규칙을 개별적으로 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc378-237">In addition, you can turn off each rule individually by editing the policy and then toggling off the **Status** of that rule, as described above.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="fc378-238">추가 정보</span><span class="sxs-lookup"><span data-stu-id="fc378-238">More information</span></span>

- [<span data-ttu-id="fc378-239">데이터 손실 방지 정책 개요</span><span class="sxs-lookup"><span data-stu-id="fc378-239">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="fc378-240">DLP 정책에 대한 알림을 보내고 정책 팁 표시</span><span class="sxs-lookup"><span data-stu-id="fc378-240">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="fc378-241">FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="fc378-241">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="fc378-242">DLP 정책 템플릿에 포함되는 내용</span><span class="sxs-lookup"><span data-stu-id="fc378-242">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="fc378-243">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="fc378-243">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    


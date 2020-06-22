---
title: 보안 및 준수 센터에서 사용자 지정 중요한 정보 유형 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 보안 및 준수 센터의 그래픽 사용자 인터페이스에서 DLP에 대한 사용자 지정 중요한 정보 유형을 만들고, 수정, 제거 및 테스트하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f702582a0e2c53b0846cd0586295d9bbea657e3c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818067"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="de609-103">보안 및 준수 센터에서 사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="de609-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

<span data-ttu-id="de609-104">이 문서를 읽고 보안 및 준수 센터([https://protection.office.com](https://protection.office.com))에서 [사용자 지정 중요한 정보 유형](custom-sensitive-info-types.md)을 만들어 보세요.</span><span class="sxs-lookup"><span data-stu-id="de609-104">Read this article to create a [custom sensitive information type](custom-sensitive-info-types.md) in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="de609-105">이 방법으로 만드는 사용자 지정 중요한 정보 유형은 이름이 `Microsoft.SCCManaged.CustomRulePack`인 규칙 패키지에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="de609-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="de609-106">PowerShell 및 정확한 데이터 매치 기능을 사용하여 사용자 지정 중요한 정보 유형을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de609-106">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="de609-107">해당 방법에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de609-107">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="de609-108">보안 및 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="de609-108">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="de609-109">정확한 데이터 매치(EDM)를 사용하여 DLP를 위한 사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="de609-109">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="before-you-begin"></a><span data-ttu-id="de609-110">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="de609-110">Before you begin</span></span>

> [!NOTE]
> <span data-ttu-id="de609-111">사용자 지정 정보 유형을 UI를 통해 작성하고, 테스트하고 배포하려면 전역 관리자 또는 준수 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-111">You should have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="de609-112">Office 365에서 [관리자 역할 정보](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de609-112">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="de609-113">조직에 DLP(데이터 손실 방지)를 포함하는 구독(예: Office 365 Enterprise)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-113">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="de609-114">[메시징 정책 및 규정 준수 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de609-114">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="de609-115">Custom sensitive information types require familiarity with regular expressions (RegEx).</span><span class="sxs-lookup"><span data-stu-id="de609-115">Custom sensitive information types require familiarity with regular expressions (RegEx).</span></span> <span data-ttu-id="de609-116">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="de609-116">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="de609-117">Microsoft 고객 서비스 및 지원은 사용자 지정 분류 또는 정규식 패턴 만들기를 지원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de609-117">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="de609-118">지원 엔지니어는 테스트 목적으로 샘플 정규식 패턴 제공 또는 예상대로 트리거되지 않는 기존 정규식 패턴 문제 해결 지원과 같은 기능을 제한적으로 지원할 수 있습니다. 그러나 사용자 지정 콘텐츠 일치 개발이 귀하의 요구 사항이나 의무를 충족할 것이라고 확신할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de609-118">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="de609-119">DLP는 SharePoint Online 및 비즈니스용 OneDrive 사이트에서 중요한 정보를 식별하고 분류하기 위해 검색 크롤러를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-119">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="de609-120">기존 콘텐츠에서 새로운 사용자 지정 중요한 정보 유형을 식별하려면 해당 콘텐츠에 대한 크롤링을 다시 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-120">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="de609-121">콘텐츠는 일정을 기반으로 크롤링되지만 사이트 모음, 목록 또는 라이브러리의 콘텐츠를 수동으로 다시 크롤링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de609-121">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="de609-122">자세한 내용은 [사이트, 라이브러리 또는 목록을 크롤링 및 다시 인덱싱하도록 수동으로 요청](https://docs.microsoft.com/sharepoint/crawl-site-content)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de609-122">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="de609-123">보안 및 준수 센터에서 사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="de609-123">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="de609-124">보안 및 준수 센터에서 **분류** \> **중요한 정보 유형**으로 이동한 후 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-124">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="de609-125">설정은 매우 명확하며 마법사의 연결 페이지에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-125">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="de609-126">**이름**</span><span class="sxs-lookup"><span data-stu-id="de609-126">**Name**</span></span>

- <span data-ttu-id="de609-127">**설명**</span><span class="sxs-lookup"><span data-stu-id="de609-127">**Description**</span></span>

- <span data-ttu-id="de609-128">**근접**</span><span class="sxs-lookup"><span data-stu-id="de609-128">**Proximity**</span></span>

- <span data-ttu-id="de609-129">**신뢰 수준**</span><span class="sxs-lookup"><span data-stu-id="de609-129">**Confidence level**</span></span>

- <span data-ttu-id="de609-130">**기본 패턴 요소**(키워드, 정규식 또는 사전)</span><span class="sxs-lookup"><span data-stu-id="de609-130">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="de609-131">선택 사항인 **지원 패턴 요소**(키워드, 정규식 또는 사전) 및 해당하는 **최소 비용** 값</span><span class="sxs-lookup"><span data-stu-id="de609-131">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="de609-132">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge".</span><span class="sxs-lookup"><span data-stu-id="de609-132">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge".</span></span> <span data-ttu-id="de609-133">To create this custom sensitive information type, do the following steps:</span><span class="sxs-lookup"><span data-stu-id="de609-133">To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="de609-134">보안 및 준수 센터에서 **분류** \> **중요한 정보 유형**으로 이동한 후 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-134">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![중요한 정보 유형 및 만들기 단추 위치](../media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="de609-136">**이름 및 설명 선택** 페이지가 열리면 다음 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-136">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="de609-137">**이름**: 직원 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="de609-137">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="de609-138">**설명**: 9자리 Contoso 직원 ID 번호를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-138">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![이름 및 설명 페이지](../media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="de609-140">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-140">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="de609-141">**일치 요구 사항** 페이지가 열리면 **요소 추가**를 클릭하고 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-141">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="de609-142">**다음이 포함된 콘텐츠 검색**:</span><span class="sxs-lookup"><span data-stu-id="de609-142">**Detect content containing**:</span></span>
 
      <span data-ttu-id="de609-143">a.</span><span class="sxs-lookup"><span data-stu-id="de609-143">a.</span></span> <span data-ttu-id="de609-144">Click **Any of these** and select **Regular expression**.</span><span class="sxs-lookup"><span data-stu-id="de609-144">Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="de609-145">b.</span><span class="sxs-lookup"><span data-stu-id="de609-145">b.</span></span> <span data-ttu-id="de609-146">In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span><span class="sxs-lookup"><span data-stu-id="de609-146">In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="de609-147">**지원 요소**: **지원 요소 추가**를 클릭하고 **이 키워드 목록 포함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-147">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="de609-148">**이 키워드 목록 포함** 영역이 표시되면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-148">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="de609-149">**키워드 목록**: 직원, ID, 배지 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-149">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="de609-150">**최소 개수**: 기본값 1을 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="de609-150">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="de609-151">기본값인 **신뢰 수준** 값 60을 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="de609-151">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="de609-152">기본값인 **문자 근접** 값 300을 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="de609-152">Leave the default **Character proximity** value 300.</span></span>

    ![페이지 일치에 대한 요구 사항](../media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="de609-154">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="de609-155">**검토 및 완료** 페이지가 열리면 설정을 검토하고 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-155">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![검토 및 완료 페이지](../media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="de609-157">The next page encourages you to test the new custom sensitive information type by clicking **Yes**.</span><span class="sxs-lookup"><span data-stu-id="de609-157">The next page encourages you to test the new custom sensitive information type by clicking **Yes**.</span></span> <span data-ttu-id="de609-158">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="de609-158">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span> <span data-ttu-id="de609-159">To test the rule later, click **No**.</span><span class="sxs-lookup"><span data-stu-id="de609-159">To test the rule later, click **No**.</span></span>

    ![테스트 권장 사항 페이지](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="de609-161">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="de609-161">How do you know this worked?</span></span>

<span data-ttu-id="de609-162">새로운 중요한 정보 유형을 성공적으로 만들었는지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-162">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="de609-163">**분류** \> **중요한 정보 유형**으로 이동하고 새로운 사용자 지정 중요한 정보 유형이 나열되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="de609-163">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="de609-164">Test the new custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="de609-164">Test the new custom sensitive information type.</span></span> <span data-ttu-id="de609-165">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="de609-165">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="de609-166">보안 및 준수 센터에서 사용자 지정 중요한 정보 유형 수정</span><span class="sxs-lookup"><span data-stu-id="de609-166">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="de609-167">**참고:**</span><span class="sxs-lookup"><span data-stu-id="de609-167">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="de609-168">You can only modify custom sensitive information types; you can't modify built-in sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="de609-168">You can only modify custom sensitive information types; you can't modify built-in sensitive information types.</span></span> <span data-ttu-id="de609-169">But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="de609-169">But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types.</span></span> <span data-ttu-id="de609-170">For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="de609-170">For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="de609-171">You can only modify custom sensitive information types that you created in the UI.</span><span class="sxs-lookup"><span data-stu-id="de609-171">You can only modify custom sensitive information types that you created in the UI.</span></span> <span data-ttu-id="de609-172">If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span><span class="sxs-lookup"><span data-stu-id="de609-172">If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="de609-173">보안 및 준수 센터에서 **분류** \> **중요한 정보 유형**으로 이동하고, 수정할 사용자 지정 중요한 정보 유형을 선택한 후 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-173">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![중요한 정보 유형 및 편집 단추 위치](../media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="de609-175">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="de609-175">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center.</span></span> <span data-ttu-id="de609-176">For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="de609-176">For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="de609-177">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="de609-177">How do you know this worked?</span></span>

<span data-ttu-id="de609-178">수정한 중요한 정보 유형을 성공적으로 만들었는지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-178">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="de609-179">**분류** \> **중요한 정보 유형**으로 이동하고 수정한 사용자 지정 중요한 정보 유형의 속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-179">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="de609-180">Test the modified custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="de609-180">Test the modified custom sensitive information type.</span></span> <span data-ttu-id="de609-181">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="de609-181">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="de609-182">보안 및 준수 센터에서 사용자 지정 중요한 정보 유형 제거</span><span class="sxs-lookup"><span data-stu-id="de609-182">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="de609-183">**참고**:</span><span class="sxs-lookup"><span data-stu-id="de609-183">**Notes**:</span></span>

- <span data-ttu-id="de609-184">사용자 지정 중요한 정보 유형만 제거할 수 있습니다. 기본 제공 중요한 정보 유형은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de609-184">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="de609-185">사용자 지정 중요한 정보 유형을 제거하기 전에 DLP 정책이나 Exchange 메일 흐름 규칙(전송 규칙이라고도 함)이 중요한 정보 유형을 계속 참조하지 않는 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-185">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="de609-186">보안 및 준수 센터에서 **분류** \> **중요한 정보 유형**으로 이동하고, 제거할 사용자 지정 중요한 정보 유형을 한 개 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-186">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="de609-187">플라이아웃이 열리면 **삭제**(두 개 이상을 선택한 경우 **중요한 정보 유형 삭제**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-187">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![중요한 정보 유형 및 삭제 단추 위치](../media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="de609-189">나타나는 경고 메시지에서 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-189">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="de609-190">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="de609-190">How do you know this worked?</span></span>

<span data-ttu-id="de609-191">사용자 지정 중요한 정보 유형을 성공적으로 삭제했는지 확인하려면 **분류** \> **중요한 정보 유형**으로 이동하여 사용자 지정 중요한 정보 유형이 더 이상 나열되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-191">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="de609-192">보안 및 준수 센터에서 사용자 지정 중요한 정보 유형 테스트</span><span class="sxs-lookup"><span data-stu-id="de609-192">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="de609-193">보안 및 준수 센터에서 **분류** \> **중요한 정보 유형**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-193">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="de609-194">Select one or more custom sensitive information types to test.</span><span class="sxs-lookup"><span data-stu-id="de609-194">Select one or more custom sensitive information types to test.</span></span> <span data-ttu-id="de609-195">In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span><span class="sxs-lookup"><span data-stu-id="de609-195">In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![중요한 정보 유형 및 유형 테스트 단추 위치](../media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="de609-197">**테스트할 파일 업로드** 페이지가 열리면 파일을 끌어서 놓거나 **찾아보기**를 클릭하고 파일을 선택하여 테스트할 문서를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-197">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![테스트할 파일 업로드 페이지](../media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="de609-199">**테스트** 단추를 클릭하여 파일에서 패턴 일치에 대해 문서를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-199">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="de609-200">**결과 일치** 페이지에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de609-200">On the **Match results** page, click **Finish**.</span></span>

    ![결과 일치](../media/scc-cust-sens-info-type-test-results.png)

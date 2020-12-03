---
title: FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: DLP (데이터 손실 방지) 정책을 사용 하 여 타사 시스템의 속성이 포함 된 문서를 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: a3dd82dae76336dc3d1293430e10ba505585e707
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562979"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="61fbe-103">FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="61fbe-103">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="61fbe-104">Microsoft 365 DLP (데이터 손실 방지) 정책은 분류 속성 또는 항목 속성을 사용 하 여 중요 한 항목을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-104">Microsoft 365 data loss prevention (DLP) policies can use classification properties or item properties to identify sensitive items.</span></span> <span data-ttu-id="61fbe-105">예를 들면 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-105">For example you can use:</span></span>

- <span data-ttu-id="61fbe-106">Windows Server FCI (파일 분류 인프라) 속성</span><span class="sxs-lookup"><span data-stu-id="61fbe-106">Windows Server File Classification infrastructure (FCI) properties</span></span>
- <span data-ttu-id="61fbe-107">SharePoint 문서 속성</span><span class="sxs-lookup"><span data-stu-id="61fbe-107">SharePoint document properties</span></span>
- <span data-ttu-id="61fbe-108">타사 시스템 문서 속성</span><span class="sxs-lookup"><span data-stu-id="61fbe-108">third-party system document properties</span></span>

![Office 365 외부 분류 시스템을 보여 주는 다이어그램](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

<span data-ttu-id="61fbe-110">예를 들어 조직에서 Windows Server FCI를 사용 하 여 주민 등록 번호와 같은 개인 데이터를 갖는 항목을 식별 한 다음, 개인 식별이 **가능한 정보** 속성을 문서에 있는 개인 데이터의 유형 및 수에 따라 **고급**, **보통**, **낮음**, **공용** 또는 **PII가 아닌** 사용자로 분류 하 여 문서를 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-110">For example, your organization might use Windows Server FCI to identify items with personal data such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of personal data found in the document.</span></span>

<span data-ttu-id="61fbe-111">Microsoft 365에서는 해당 속성이 **High** 및 **Medium** 과 같은 특정 값으로 설정 된 문서를 식별 하는 DLP 정책을 만든 다음 해당 파일에 대 한 액세스를 차단 하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-111">In Microsoft 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files.</span></span> <span data-ttu-id="61fbe-112">해당 속성이 **낮음** 으로 설정된 경우에는 전자 메일 알림 전송 등의 다른 작업을 수행하는 다른 규칙을 동일한 정책에 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-112">The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification.</span></span> <span data-ttu-id="61fbe-113">이러한 방식으로 DLP는 Windows Server FCI와 통합 되며, Windows Server 기반 파일 서버에서 Microsoft 365로 업로드 되거나 공유 되는 Office 문서를 보호 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-113">In this way, DLP integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Microsoft 365 from Windows Server-based file servers.</span></span>

<span data-ttu-id="61fbe-114">DLP 정책은 단순히 특정 속성 이름/값 쌍을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-114">A DLP policy simply looks for a specific property name/value pair.</span></span> <span data-ttu-id="61fbe-115">속성에 SharePoint search에 해당 하는 관리 속성이 있으면 모든 문서 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-115">Any document property can be used, as long as the property has a corresponding managed property for SharePoint search.</span></span> <span data-ttu-id="61fbe-116">예를 들어 SharePoint 사이트 모음에는 **Customer** 라는 필수 필드와 함께 **트립 보고서** 라는 콘텐츠 형식이 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-116">For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**.</span></span> <span data-ttu-id="61fbe-117">사용자가 출장 보고서를 만들 때마다 고객 이름을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-117">Whenever a person creates a trip report, they must enter the customer name.</span></span> <span data-ttu-id="61fbe-118">이 속성 이름/값 쌍은 DLP 정책 에서도 사용할 수 있으며, 예를 들어 **Customer** 필드에 **Contoso** 가 포함 되어 있는 경우 게스트가 문서에 대 한 액세스를 차단 하는 규칙을 원하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-118">This property name/value pair can also be used in a DLP policy—for example, if you want a rule that blocks access to the document for guests when the **Customer** field contains **Contoso**.</span></span>

<span data-ttu-id="61fbe-119">특정 Microsoft 365 레이블이 있는 콘텐츠에 DLP 정책을 적용 하려면 여기에 나와 있는 단계를 수행 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-119">If you want to apply your DLP policy to content with specific Microsoft 365 labels, you should not follow the steps here.</span></span> <span data-ttu-id="61fbe-120">대신 [보존 레이블을 DLP 정책의 조건으로 사용](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="61fbe-120">Instead, learn how to [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="61fbe-121">DLP 정책 만들기 전</span><span class="sxs-lookup"><span data-stu-id="61fbe-121">Before you create the DLP policy</span></span>

<span data-ttu-id="61fbe-122">DLP 정책에서 Windows Server FCI 속성 또는 기타 속성을 사용하려면 먼저 SharePoint 관리 센터에서 관리 속성을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-122">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center.</span></span> <span data-ttu-id="61fbe-123">그 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-123">Here's why.</span></span>

<span data-ttu-id="61fbe-p106">예제</span><span class="sxs-lookup"><span data-stu-id="61fbe-p106">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>

<span data-ttu-id="61fbe-131">DLP는 검색 크롤러를 사용 하 여 사이트에서 중요 한 정보를 식별 하 고 분류 한 다음 중요 한 정보를 검색 인덱스의 안전한 부분에 저장 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-131">This is important because DLP uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index.</span></span> <span data-ttu-id="61fbe-132">Office 365로 문서를 업로드하는 경우 SharePoint는 문서 속성을 기준으로 크롤링된 속성을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-132">When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties.</span></span> <span data-ttu-id="61fbe-133">그러나 FCI 또는 DLP 정책의 다른 속성을 사용하려면 해당 속성을 갖는 콘텐츠가 인덱스에 보관될 수 있게 크롤링된 속성이 관리 속성에 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-133">But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>

<span data-ttu-id="61fbe-134">검색 및 관리 속성에 대 한 자세한 내용은 [SharePoint Online에서 검색 스키마 관리](https://go.microsoft.com/fwlink/p/?LinkID=627454)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61fbe-134">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="61fbe-135">1단계: 필요한 속성을 갖는 문서를 Office 365에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-135">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="61fbe-136">먼저 DLP 정책에서 참조하려는 속성을 갖는 문서를 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-136">You first need to upload a document with the property that you want to reference in your DLP policy.</span></span> <span data-ttu-id="61fbe-137">Microsoft 365에서 속성을 검색 하 고 크롤링 속성을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-137">Microsoft 365 will detect the property and automatically create a crawled property from it.</span></span> <span data-ttu-id="61fbe-138">다음 단계에서는 관리 속성을 만든 다음 관리 속성을이 크롤링 속성에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-138">In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>

### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="61fbe-139">2단계: 관리 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="61fbe-139">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="61fbe-140">Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-140">Sign in to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="61fbe-141">왼쪽 탐색 영역에서 **관리 센터** \> **SharePoint** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-141">In the left navigation, choose **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="61fbe-142">이제 사용자는 SharePoint 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-142">You're now in the SharePoint admin center.</span></span>

3. <span data-ttu-id="61fbe-143">왼쪽 탐색 창의 검색 관리 페이지 **에서 검색** \> **search administration** \> **스키마 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-143">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>

   ![검색 관리 페이지의 SharePoint 관리 센터](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. <span data-ttu-id="61fbe-145">**관리 속성** 페이지에서 \> **새 관리 속성** 을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-145">On the **Managed Properties** page \> **New Managed Property**.</span></span>

   ![관리 속성 페이지에서 새 관리 속성 단추가 강조 표시 된](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. <span data-ttu-id="61fbe-p110">속성의 이름 및 설명을 입력합니다. 이 이름은 DLP 정책에 표시되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-p110">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>

6. <span data-ttu-id="61fbe-149">**형식** 에서 **텍스트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-149">For **Type**, choose **Text**.</span></span>

7. <span data-ttu-id="61fbe-150">**기본 특징** 아래에서 **쿼리 가능** 및 **조회 가능** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-150">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>

8. <span data-ttu-id="61fbe-151">**크롤링 속성에** 매핑 아래에서 \> **매핑을 추가** 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-151">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>

9. <span data-ttu-id="61fbe-152">**크롤링 속성 선택** 대화 상자에서 \> DLP 정책 확인에 사용할 Windows Server fci 속성 또는 기타 속성에 해당 하는 크롤링 속성을 찾아 선택 합니다 \> **OK**.</span><span class="sxs-lookup"><span data-stu-id="61fbe-152">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>

   ![크롤링된 속성 선택](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. <span data-ttu-id="61fbe-154">페이지 맨 아래에서 \> **확인을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-154">At the bottom of the page \> **OK**.</span></span>

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="61fbe-155">FCI 속성 또는 기타 속성을 사용하는 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="61fbe-155">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="61fbe-156">이 예에서는 조직에서 Windows Server 기반 파일 서버에 FCI를 사용 하 고 있습니다. 특히 **높은**, **중간**, **낮음**, **공용**, **PII가 아닌** 사용할 수 있는 **개인 식별** 이 가능한 값이 포함 된 fci 분류 속성을 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-156">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**.</span></span> <span data-ttu-id="61fbe-157">이제 Office 365에서 해당 DLP 정책에 기존 FCI 분류를 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-157">Now they want to use their existing FCI classification in their DLP policies in Office 365.</span></span>

<span data-ttu-id="61fbe-158">먼저 위 단계에 따라 SharePoint Online에서 관리 속성을 만듭니다. 이 속성은 FCI 속성에서 자동으로 만들어진 크롤링 속성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-158">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>

<span data-ttu-id="61fbe-159">다음으로, 조건 **문서 속성** 을 사용 하는 두 개의 규칙을 포함 하는 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-159">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>

- <span data-ttu-id="61fbe-160">**Fci PII 콘텐츠-높음, 보통** 첫 번째 규칙은 FCI 분류 속성 **개인 식별 정보가** **높은** 또는 **보통** 이 고 문서가 조직 외부의 사용자와 공유 되는 경우 문서에 대 한 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-160">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span>

- <span data-ttu-id="61fbe-161">**Fci PII 콘텐츠-낮음** 두 번째 규칙은 FCI 분류 속성 **개인 식별 정보가** **낮은** 정보이 고 문서가 조직 외부의 사용자와 공유 되는 경우 문서 소유자에 게 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-161">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span>

### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="61fbe-162">PowerShell을 사용 하 여 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="61fbe-162">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="61fbe-163">조건 **문서 속성에 포함 된 이러한 값** 은 일시적으로 보안 및 준수 센터의 UI에서 사용할 수 &amp; 없지만 PowerShell을 사용 하 여이 조건을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-163">The condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell.</span></span> <span data-ttu-id="61fbe-164">Cmdlet을 사용  `New\Set\Get-DlpCompliancePolicy` 하 여 DLP 정책에 대 한 작업을 수행 하 고  `New\Set\Get-DlpComplianceRule` 매개 변수와 함께 cmdlet을 사용  `ContentPropertyContainsWords` 하 여 조건을 추가할 수 있습니다 **문서 속성에 이러한 값이 포함 되어** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-164">You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>

<span data-ttu-id="61fbe-165">이러한 cmdlet에 대 한 자세한 내용은 [Security &amp; 준수 센터 cmdlet](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61fbe-165">For more information on these cmdlets, see [Security &amp; Compliance Center cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>

1. [<span data-ttu-id="61fbe-166">&amp;원격 PowerShell을 사용 하 여 보안 및 준수 센터에 연결</span><span class="sxs-lookup"><span data-stu-id="61fbe-166">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)

2. <span data-ttu-id="61fbe-167">을 사용 하 여 정책을 만듭니다  `New-DlpCompliancePolicy` .</span><span class="sxs-lookup"><span data-stu-id="61fbe-167">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>

<span data-ttu-id="61fbe-168">이 PowerShell은 모든 위치에 적용 되는 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-168">This PowerShell creates a DLP policy that applies to all locations.</span></span>

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. <span data-ttu-id="61fbe-169">위에서 설명한 두 가지 규칙을 사용 하 여  `New-DlpComplianceRule` , 즉 **낮은** 값에 대 한 규칙을 만들고, **높은** 값과 **중간** 가치에 대해 다른 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-169">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span>

   <span data-ttu-id="61fbe-170">다음은 이러한 두 가지 규칙을 만드는 PowerShell 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-170">Here is a PowerShell example that creates these two rules.</span></span> <span data-ttu-id="61fbe-171">속성 이름/값 쌍은 큰따옴표로 묶여 있고 속성 이름에는 공백 없이 쉼표로 구분 된 여러 값을 다음과 같이 지정할 수 있습니다.  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="61fbe-171">The property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   <span data-ttu-id="61fbe-172">Windows Server FCI에는이 예에서 사용 되는 **개인 식별** 이 가능한 정보를 포함 하 여 기본 제공 되는 여러 속성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-172">Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example.</span></span> <span data-ttu-id="61fbe-173">각 속성에 사용할 수 있는 값은 조직 마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-173">The possible values for each property can be different for every organization.</span></span> <span data-ttu-id="61fbe-174">여기에서 사용 되는 **높은** 값, **중간 규모** 및 **낮음을** 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-174">The **High**, **Moderate**, and **Low** values used here are only an example.</span></span> <span data-ttu-id="61fbe-175">조직의 경우 Windows server FCI 분류 속성을 사용할 수 있는 값을 포함 하는 파일 서버 기반 파일 서버</span><span class="sxs-lookup"><span data-stu-id="61fbe-175">For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server.</span></span> <span data-ttu-id="61fbe-176">자세한 내용은 [분류 속성 만들기](https://go.microsoft.com/fwlink/p/?LinkID=627456)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="61fbe-176">For more information, see [Create a classification property](https://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>

<span data-ttu-id="61fbe-177">완료 되 면 정책에는 문서 속성을 사용 하는 두 가지 새 규칙에 **이러한 값 조건이 포함** 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-177">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition.</span></span> <span data-ttu-id="61fbe-178">이 조건은 UI에는 표시 되지 않지만 다른 조건, 작업 및 설정은 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-178">This condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span>

<span data-ttu-id="61fbe-179">규칙 하나는 **개인 식별 정보** 속성이 **높은** 또는 **보통** 인 콘텐츠에 대한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-179">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**.</span></span> <span data-ttu-id="61fbe-180">또 다른 규칙은 **개인 식별 정보** 속성이 **낮음** 인 콘텐츠에 대해 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-180">A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>

![방금 만든 두 규칙을 보여 주는 새로운 DLP 정책 대화](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="61fbe-182">DLP 정책을 만든 후</span><span class="sxs-lookup"><span data-stu-id="61fbe-182">After you create the DLP policy</span></span>

<span data-ttu-id="61fbe-183">이전 섹션의 단계를 수행 하면 해당 속성을 사용 하 여 콘텐츠를 빠르게 검색할 DLP 정책이 생성 되지만 콘텐츠가 새로 업로드 되는 경우 (콘텐츠가 인덱싱되지 않도록), 해당 콘텐츠가 이전에 편집 된 경우에만 콘텐츠가 다시 인덱싱되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-183">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>

<span data-ttu-id="61fbe-p117">모든 위치에서 해당 속성을 갖는 콘텐츠를 검색하려는 경우 DLP 정책이 해당 속성의 모든 콘텐츠를 인식할 수 있게 라이브러리, 사이트 또는 사이트 모음을 다시 인덱싱하도록 수동으로 요청할 수 있습니다. SharePoint Online에서 콘텐츠는 정의된 크롤링 일정에 따라 자동으로 크롤링됩니다. 크롤러는 마지막 크롤링 이후에 변경된 콘텐츠를 선택하고 인덱스를 업데이트합니다. 예약된 다음 크롤링 전에 DLP 정책을 통해 콘텐츠를 보호해야 할 경우 다음 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-p117">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>

> [!CAUTION]
> <span data-ttu-id="61fbe-188">사이트를 다시 인덱싱하면 검색 시스템에서 대량의 부하가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-188">Re-indexing a site can cause a massive load on the search system.</span></span> <span data-ttu-id="61fbe-189">시나리오에서 절대적으로 필요한 경우가 아니면 사이트를 다시 인덱싱하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="61fbe-189">Don't re-index your site unless your scenario absolutely requires it.</span></span>

<span data-ttu-id="61fbe-190">자세한 내용은 [사이트, 라이브러리 또는 목록을 크롤링 및 다시 인덱싱하도록 수동으로 요청](https://go.microsoft.com/fwlink/p/?LinkID=627457)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61fbe-190">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>

### <a name="reindex-a-site-optional"></a><span data-ttu-id="61fbe-191">사이트 다시 인덱싱 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="61fbe-191">Reindex a site (optional)</span></span>

1. <span data-ttu-id="61fbe-192">사이트에서 **설정** (오른쪽 위의 기어 아이콘) \> **사이트 설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-192">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>

2. <span data-ttu-id="61fbe-193">**검색** 에서 **검색 및 오프 라인 가용성 다시** \> **인덱싱 사이트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61fbe-193">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>

## <a name="more-information"></a><span data-ttu-id="61fbe-194">추가 정보</span><span class="sxs-lookup"><span data-stu-id="61fbe-194">More information</span></span>

- [<span data-ttu-id="61fbe-195">데이터 손실 방지 정책 개요</span><span class="sxs-lookup"><span data-stu-id="61fbe-195">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)

- [<span data-ttu-id="61fbe-196">서식 파일에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="61fbe-196">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)

- [<span data-ttu-id="61fbe-197">DLP 정책에 대한 알림을 보내고 정책 팁 표시</span><span class="sxs-lookup"><span data-stu-id="61fbe-197">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)

- [<span data-ttu-id="61fbe-198">DLP 정책 템플릿에 포함되는 내용</span><span class="sxs-lookup"><span data-stu-id="61fbe-198">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)

- [<span data-ttu-id="61fbe-199">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="61fbe-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

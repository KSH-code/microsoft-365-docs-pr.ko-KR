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
description: DLP(데이터 손실 방지) 정책을 사용하여 타사 시스템의 속성이 있는 문서를 보호하는 방법을 학습합니다.
ms.openlocfilehash: a3dd82dae76336dc3d1293430e10ba505585e707
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562979"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="c5477-103">FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c5477-103">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="c5477-104">Microsoft 365 DLP(데이터 손실 방지) 정책은 분류 속성 또는 항목 속성을 사용하여 중요한 항목을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-104">Microsoft 365 data loss prevention (DLP) policies can use classification properties or item properties to identify sensitive items.</span></span> <span data-ttu-id="c5477-105">예를 들어 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-105">For example you can use:</span></span>

- <span data-ttu-id="c5477-106">Windows Server FCI(파일 분류 인프라) 속성</span><span class="sxs-lookup"><span data-stu-id="c5477-106">Windows Server File Classification infrastructure (FCI) properties</span></span>
- <span data-ttu-id="c5477-107">SharePoint 문서 속성</span><span class="sxs-lookup"><span data-stu-id="c5477-107">SharePoint document properties</span></span>
- <span data-ttu-id="c5477-108">타사 시스템 문서 속성</span><span class="sxs-lookup"><span data-stu-id="c5477-108">third-party system document properties</span></span>

![Office 365 외부 분류 시스템을 보여 주는 다이어그램](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

<span data-ttu-id="c5477-110">예를 들어 조직에서는 Windows Server FCI를 사용하여 주민 등록 번호와 같은 개인 데이터가 있는  항목을 식별한 다음 문서에서 찾은 개인 데이터의 발생 수와 유형에 따라 개인 식별이 가능한 정보 속성을 높음, 보통, 낮음, 공용 또는 **PII가** 아닌 것으로 설정하여 문서를 분류할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="c5477-110">For example, your organization might use Windows Server FCI to identify items with personal data such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of personal data found in the document.</span></span>

<span data-ttu-id="c5477-111">Microsoft 365에서는 해당 속성이 **High** 및 **Medium과** 같은 특정 값으로 설정된 문서를 식별하는 DLP 정책을 만든 다음 해당 파일에 대한 액세스를 차단하는 등의 작업을 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-111">In Microsoft 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files.</span></span> <span data-ttu-id="c5477-112">해당 속성이 **낮음** 으로 설정된 경우에는 전자 메일 알림 전송 등의 다른 작업을 수행하는 다른 규칙을 동일한 정책에 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-112">The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification.</span></span> <span data-ttu-id="c5477-113">이러한 방식으로 DLP는 Windows Server FCI와 통합되어 Windows Server 기반 파일 서버에서 Microsoft 365로 업로드되거나 공유되는 Office 문서를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-113">In this way, DLP integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Microsoft 365 from Windows Server-based file servers.</span></span>

<span data-ttu-id="c5477-114">DLP 정책은 단순히 특정 속성 이름/값 쌍을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-114">A DLP policy simply looks for a specific property name/value pair.</span></span> <span data-ttu-id="c5477-115">속성에 SharePoint 검색에 대한 해당 관리 속성이 있는 경우 모든 문서 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-115">Any document property can be used, as long as the property has a corresponding managed property for SharePoint search.</span></span> <span data-ttu-id="c5477-116">예를 들어 SharePoint 사이트 모음은 이름이 **Customer인** 필수 필드와 함께 Trip Report라는 콘텐츠 형식을 **사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c5477-116">For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**.</span></span> <span data-ttu-id="c5477-117">사용자가 여행 보고서를 만드는 경우 고객 이름을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-117">Whenever a person creates a trip report, they must enter the customer name.</span></span> <span data-ttu-id="c5477-118">이 속성 이름/값 쌍은 DLP 정책에서도 사용할 수 있습니다. 예를 들어 **고객** 필드에 **Contoso가** 포함된 경우 게스트의 문서 액세스를 차단하는 규칙이 필요한 경우</span><span class="sxs-lookup"><span data-stu-id="c5477-118">This property name/value pair can also be used in a DLP policy—for example, if you want a rule that blocks access to the document for guests when the **Customer** field contains **Contoso**.</span></span>

<span data-ttu-id="c5477-119">특정 Microsoft 365 레이블이 있는 콘텐츠에 DLP 정책을 적용하려는 경우 여기에 있는 단계를 수행하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-119">If you want to apply your DLP policy to content with specific Microsoft 365 labels, you should not follow the steps here.</span></span> <span data-ttu-id="c5477-120">대신 보존 레이블을 DLP 정책의 조건으로 사용하는 [방법을 배워야 합니다.](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)</span><span class="sxs-lookup"><span data-stu-id="c5477-120">Instead, learn how to [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="c5477-121">DLP 정책 만들기 전</span><span class="sxs-lookup"><span data-stu-id="c5477-121">Before you create the DLP policy</span></span>

<span data-ttu-id="c5477-122">DLP 정책에서 Windows Server FCI 속성 또는 기타 속성을 사용하려면 먼저 SharePoint 관리 센터에서 관리 속성을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-122">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center.</span></span> <span data-ttu-id="c5477-123">그 이유는 다음과 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-123">Here's why.</span></span>

<span data-ttu-id="c5477-p106">예제</span><span class="sxs-lookup"><span data-stu-id="c5477-p106">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>

<span data-ttu-id="c5477-131">이는 DLP가 검색 크롤러를 사용하여 사이트에서 중요한 정보를 식별하고 분류한 다음 해당 중요한 정보를 검색 인덱스의 보안 부분에 저장하기 때문에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-131">This is important because DLP uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index.</span></span> <span data-ttu-id="c5477-132">Office 365로 문서를 업로드하는 경우 SharePoint는 문서 속성을 기준으로 크롤링된 속성을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-132">When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties.</span></span> <span data-ttu-id="c5477-133">그러나 FCI 또는 DLP 정책의 다른 속성을 사용하려면 해당 속성을 갖는 콘텐츠가 인덱스에 보관될 수 있게 크롤링된 속성이 관리 속성에 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-133">But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>

<span data-ttu-id="c5477-134">검색 및 관리 속성에 대한 자세한 내용은 [SharePoint Online에서 검색 schema 관리를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkID=627454)</span><span class="sxs-lookup"><span data-stu-id="c5477-134">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="c5477-135">1단계: 필요한 속성을 갖는 문서를 Office 365에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-135">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="c5477-136">먼저 DLP 정책에서 참조하려는 속성을 갖는 문서를 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-136">You first need to upload a document with the property that you want to reference in your DLP policy.</span></span> <span data-ttu-id="c5477-137">Microsoft 365는 속성을 검색하고 속성에서 크롤링 속성을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-137">Microsoft 365 will detect the property and automatically create a crawled property from it.</span></span> <span data-ttu-id="c5477-138">다음 단계에서는 관리 속성을 만든 다음 관리 속성을 이 크롤링 속성에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-138">In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>

### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="c5477-139">2단계: 관리 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="c5477-139">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="c5477-140">Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-140">Sign in to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="c5477-141">왼쪽 탐색에서 **관리 센터** \> **SharePoint를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5477-141">In the left navigation, choose **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="c5477-142">이제 사용자는 SharePoint 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-142">You're now in the SharePoint admin center.</span></span>

3. <span data-ttu-id="c5477-143">In the left navigation, choose **search** \> on the search **administration** page Manage \> **Search Schema.**</span><span class="sxs-lookup"><span data-stu-id="c5477-143">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>

   ![검색 관리 페이지의 SharePoint 관리 센터](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. <span data-ttu-id="c5477-145">관리 속성 **페이지에서** \> **새 관리 속성**</span><span class="sxs-lookup"><span data-stu-id="c5477-145">On the **Managed Properties** page \> **New Managed Property**.</span></span>

   ![관리 속성 페이지에서 새 관리 속성 단추가 강조 표시 된](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. <span data-ttu-id="c5477-p110">속성의 이름 및 설명을 입력합니다. 이 이름은 DLP 정책에 표시되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-p110">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>

6. <span data-ttu-id="c5477-149">**형식** 에서 **텍스트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-149">For **Type**, choose **Text**.</span></span>

7. <span data-ttu-id="c5477-150">**기본 특징** 아래에서 **쿼리 가능** 및 **조회 가능** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-150">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>

8. <span data-ttu-id="c5477-151">**크롤링 속성에** 대한 매핑 아래에서 \> **매핑을 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5477-151">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>

9. <span data-ttu-id="c5477-152">**크롤링** 속성 선택 대화 상자에서 Windows Server FCI 속성 또는 DLP 정책 확인에 사용할 다른 속성에 해당하는 크롤링 속성을 찾아 \> \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5477-152">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>

   ![크롤링된 속성 선택](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. <span data-ttu-id="c5477-154">페이지 맨 아래에서 \> 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5477-154">At the bottom of the page \> **OK**.</span></span>

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="c5477-155">FCI 속성 또는 기타 속성을 사용하는 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c5477-155">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="c5477-156">이 예에서 조직은 Windows Server 기반 파일 서버에서 FCI를 사용하고 있습니다. 특히, 높음, 보통, 낮음,  공용 및 **PII가** 아닌 값과 함께 개인 식별이 가능한 정보라는 FCI 분류 속성을 사용합니다.  </span><span class="sxs-lookup"><span data-stu-id="c5477-156">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**.</span></span> <span data-ttu-id="c5477-157">이제 Office 365의 DLP 정책에서 기존 FCI 분류를 사용하려는 경우</span><span class="sxs-lookup"><span data-stu-id="c5477-157">Now they want to use their existing FCI classification in their DLP policies in Office 365.</span></span>

<span data-ttu-id="c5477-158">먼저 위 단계에 따라 SharePoint Online에서 관리 속성을 만듭니다. 이 속성은 FCI 속성에서 자동으로 만들어진 크롤링 속성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-158">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>

<span data-ttu-id="c5477-159">다음으로, 둘 다 조건 문서 속성에 다음 값을 포함하는 두 규칙이 포함된 DLP **정책을 생성합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5477-159">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>

- <span data-ttu-id="c5477-160">**FCI PII 콘텐츠 - 높음, 보통** 첫 번째 규칙은 FCI 분류 속성 개인  식별이 가능한 정보가 **높음** 또는  보통과 같고 문서가 조직 외부의 사용자와 공유되는 경우 문서에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-160">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span>

- <span data-ttu-id="c5477-161">**FCI PII 콘텐츠 - 낮음** 두 번째 규칙은 FCI 분류 속성 개인 식별이 가능한 정보가 **낮음과** 같고 문서가 조직 외부의 사용자와 공유되는 경우 문서 소유자에게 알림을 전송합니다. </span><span class="sxs-lookup"><span data-stu-id="c5477-161">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span>

### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="c5477-162">PowerShell을 사용하여 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c5477-162">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="c5477-163">문서 **속성에** 이러한 값이 포함된 조건은 보안 준수 센터의 UI에서 일시적으로 사용할 수 없지만 PowerShell을 사용하여 이 조건을 사용할 &amp; 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-163">The condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell.</span></span> <span data-ttu-id="c5477-164">cmdlet을 사용하여 DLP 정책을 사용할 수 있으며, 매개 변수와 `New\Set\Get-DlpCompliancePolicy` 함께 cmdlet을 사용하여 Document 속성에 이러한 값이 포함된 조건을 추가할 `New\Set\Get-DlpComplianceRule` `ContentPropertyContainsWords` 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c5477-164">You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>

<span data-ttu-id="c5477-165">이러한 cmdlet에 대한 자세한 내용은 보안 준수 센터 [ &amp; cmdlet을 참조하세요.](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="c5477-165">For more information on these cmdlets, see [Security &amp; Compliance Center cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>

1. [<span data-ttu-id="c5477-166">원격 PowerShell을 사용하여 보안 &amp; 준수 센터에 연결</span><span class="sxs-lookup"><span data-stu-id="c5477-166">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)

2. <span data-ttu-id="c5477-167">.를 사용하여 정책을 만들 수  `New-DlpCompliancePolicy` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-167">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>

<span data-ttu-id="c5477-168">이 PowerShell은 모든 위치에 적용되는 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-168">This PowerShell creates a DLP policy that applies to all locations.</span></span>

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. <span data-ttu-id="c5477-169">위에서 설명한 두 규칙을 만들고, 여기서 한 규칙은 Low 값에 대해, 다른 규칙은 높음 및 보통 `New-DlpComplianceRule`  **값에 대한 규칙입니다.** </span><span class="sxs-lookup"><span data-stu-id="c5477-169">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span>

   <span data-ttu-id="c5477-170">다음은 이러한 두 규칙을 만드는 PowerShell 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-170">Here is a PowerShell example that creates these two rules.</span></span> <span data-ttu-id="c5477-171">속성 이름/값 쌍은 따오기 표시로 묶고, 속성 이름은 공백이 없는 여러 값을 0으로 구분하여 지정할 수 있습니다.  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="c5477-171">The property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   <span data-ttu-id="c5477-172">Windows Server FCI에는 이 예에서  사용되는 개인 식별 정보를 포함하여 많은 기본 제공 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-172">Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example.</span></span> <span data-ttu-id="c5477-173">각 속성에 대해 가능한 값은 조직마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-173">The possible values for each property can be different for every organization.</span></span> <span data-ttu-id="c5477-174">여기서 **사용되는 높음,** **보통** 및 **낮음** 값은 예에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-174">The **High**, **Moderate**, and **Low** values used here are only an example.</span></span> <span data-ttu-id="c5477-175">조직의 경우 Windows Server 기반 파일 서버의 서버 리소스 관리자 파일에서 가능한 값으로 Windows Server FCI 분류 속성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-175">For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server.</span></span> <span data-ttu-id="c5477-176">자세한 내용은 [분류 속성 만들기를 참조하십시오.](https://go.microsoft.com/fwlink/p/?LinkID=627456)</span><span class="sxs-lookup"><span data-stu-id="c5477-176">For more information, see [Create a classification property](https://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>

<span data-ttu-id="c5477-177">완료되면 정책에 문서 속성을 사용하는 두 개의 새 규칙에 이러한 값 조건이 **포함되어야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-177">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition.</span></span> <span data-ttu-id="c5477-178">다른 조건, 작업 및 설정이 나타나지만 이 조건은 UI에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-178">This condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span>

<span data-ttu-id="c5477-179">규칙 하나는 **개인 식별 정보** 속성이 **높은** 또는 **보통** 인 콘텐츠에 대한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-179">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**.</span></span> <span data-ttu-id="c5477-180">또 다른 규칙은 **개인 식별 정보** 속성이 **낮음** 인 콘텐츠에 대해 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-180">A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>

![방금 만든 두 규칙을 보여 주는 새로운 DLP 정책 대화](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="c5477-182">DLP 정책을 만든 후</span><span class="sxs-lookup"><span data-stu-id="c5477-182">After you create the DLP policy</span></span>

<span data-ttu-id="c5477-183">이전 섹션의 단계를 수행하면 해당 속성이 있는 콘텐츠를 빠르게 검색하는 DLP 정책이 만들어지지만 해당 콘텐츠가 새로 업로드된 경우(콘텐츠가 인덱싱될 수 있도록) 또는 해당 콘텐츠가 오래 되지만 편집만 된 경우(콘텐츠가 다시 인덱싱될 수 있도록).</span><span class="sxs-lookup"><span data-stu-id="c5477-183">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>

<span data-ttu-id="c5477-p117">모든 위치에서 해당 속성을 갖는 콘텐츠를 검색하려는 경우 DLP 정책이 해당 속성의 모든 콘텐츠를 인식할 수 있게 라이브러리, 사이트 또는 사이트 모음을 다시 인덱싱하도록 수동으로 요청할 수 있습니다. SharePoint Online에서 콘텐츠는 정의된 크롤링 일정에 따라 자동으로 크롤링됩니다. 크롤러는 마지막 크롤링 이후에 변경된 콘텐츠를 선택하고 인덱스를 업데이트합니다. 예약된 다음 크롤링 전에 DLP 정책을 통해 콘텐츠를 보호해야 할 경우 다음 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-p117">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>

> [!CAUTION]
> <span data-ttu-id="c5477-188">사이트를 다시 인덱싱하면 검색 시스템에서 대량의 부하가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-188">Re-indexing a site can cause a massive load on the search system.</span></span> <span data-ttu-id="c5477-189">시나리오에 반드시 필요한 경우를 위해 사이트를 다시 인덱싱하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5477-189">Don't re-index your site unless your scenario absolutely requires it.</span></span>

<span data-ttu-id="c5477-190">자세한 내용은 [사이트, 라이브러리 또는 목록을 크롤링 및 다시 인덱싱하도록 수동으로 요청](https://go.microsoft.com/fwlink/p/?LinkID=627457)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5477-190">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>

### <a name="reindex-a-site-optional"></a><span data-ttu-id="c5477-191">사이트 다시 인덱스(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="c5477-191">Reindex a site (optional)</span></span>

1. <span data-ttu-id="c5477-192">사이트에서 설정(오른쪽  위에 있는 기어 아이콘) \> **사이트 설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5477-192">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>

2. <span data-ttu-id="c5477-193">Under **Search,** choose **Search and offline availability** \> **Reindex site.**</span><span class="sxs-lookup"><span data-stu-id="c5477-193">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>

## <a name="more-information"></a><span data-ttu-id="c5477-194">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c5477-194">More information</span></span>

- [<span data-ttu-id="c5477-195">데이터 손실 방지 정책 개요</span><span class="sxs-lookup"><span data-stu-id="c5477-195">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)

- [<span data-ttu-id="c5477-196">서식 파일에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c5477-196">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)

- [<span data-ttu-id="c5477-197">DLP 정책에 대한 알림을 보내고 정책 팁 표시</span><span class="sxs-lookup"><span data-stu-id="c5477-197">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)

- [<span data-ttu-id="c5477-198">DLP 정책 템플릿에 포함되는 내용</span><span class="sxs-lookup"><span data-stu-id="c5477-198">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)

- [<span data-ttu-id="c5477-199">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="c5477-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

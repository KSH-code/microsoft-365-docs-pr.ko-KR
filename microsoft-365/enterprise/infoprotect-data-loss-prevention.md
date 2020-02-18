---
title: '5단계: Office 365 데이터 손실 방지 구성'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365의 Office 365 데이터 손실 방지를 이해 및 배포
ms.openlocfilehash: 896670e9ae83324a1220d64f49a8ea48aee85169
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067225"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="254b0-103">5단계: Office 365 데이터 손실 방지 구성</span><span class="sxs-lookup"><span data-stu-id="254b0-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="254b0-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="254b0-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![6단계: 정보 보호](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="254b0-106">Office 365 보안 및 준수 센터의 DLP(데이터 손실 방지) 정책을 사용하면 Microsoft 365 전체에서 중요한 정보를 식별하고, 모니터링하고, 자동으로 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-106">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="254b0-107">DLP 정책을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-107">With DLP policies, you can:</span></span>

- <span data-ttu-id="254b0-108">Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams와 같은 다양한 위치에서 중요한 정보를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-108">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="254b0-109">문서에 대한 액세스를 차단하거나 문서를 포함하는 전자 메일을 차단하여 중요한 정보를 실수로 공유하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-109">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="254b0-110">데스크톱 버전의 Excel, PowerPoint 및 Word에서 중요한 정보를 모니터링하고 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-110">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="254b0-111">사용자가 워크플로를 중단하지 않고 전자 메일 알림 및 정책 팁을 사용하여 규정 준수 상태를 유지하는 방법을 알 수 있도록 도와줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-111">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="254b0-112">조직의 DLP 정책과 일치하는 내용을 표시하는 DLP 보고서를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-112">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="254b0-113">DLP 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-113">A DLP policy specifies:</span></span>

- <span data-ttu-id="254b0-114">**위치:** Microsoft Teams 채팅 및 채널뿐 아니라, Exchange Online, SharePoint Online 및 비즈니스용 OneDrive 사이트와 같은 위치.</span><span class="sxs-lookup"><span data-stu-id="254b0-114">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="254b0-115">**시기:** 특정 정책 규칙 내에서 일치해야 하는 조건.</span><span class="sxs-lookup"><span data-stu-id="254b0-115">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="254b0-116">**방법:** 일치하는 정책 규칙의 조치를 일치하는 조건에 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-116">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="254b0-117">위의 명령이 반환하는 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-117">In other words:</span></span>

- <span data-ttu-id="254b0-118">이 위치(위치)에 있는 문서의 경우, 콘텐츠가 규칙의 조건과 일치하면(시기) 해당 규칙에 지정된 조치를 자동으로 적용합니다(방법).</span><span class="sxs-lookup"><span data-stu-id="254b0-118">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="254b0-119">필요한 DLP 정책의 집합을 확인하려면 문서와 데이터 손실 방지가 필요한 문서 내 데이터 유형을 분석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-119">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="254b0-120">예를 들어, 미국 내 금융 조직인 경우, 사회 보장 번호가 있는 문서가 조직 외부에서 공유되거나 전자 메일로 조직 외부의 위치로 전송되는 것을 방지하는 DLP 정책을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-120">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="254b0-121">다음으로, 정확한 DLP 동작을 보장하고 가양성을 최소화하기 위해 테스트 위치를 사용하여 정책을 구성하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-121">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="254b0-122">마지막으로, 새 정책과 기대하는 동작을 직원에게 알리고 위치의 범위를 확장하여 조직에 이를 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="254b0-122">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="254b0-123">자세한 내용은 [DLP 정책 권장 사항 시작하기](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="254b0-123">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="254b0-124">중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step5)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="254b0-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="254b0-125">다음 단계</span><span class="sxs-lookup"><span data-stu-id="254b0-125">Next step</span></span>

|||
|:-------|:-----|
|![6단계](../media/stepnumbers/Step6.png)|[<span data-ttu-id="254b0-127">전자 메일 암호화 구성</span><span class="sxs-lookup"><span data-stu-id="254b0-127">Configure email encryption</span></span>](infoprotect-email-encryption.md)|



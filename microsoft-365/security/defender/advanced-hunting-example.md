---
title: Microsoft Defender for Office 365
description: 고급 헌팅을 사용하여 전자 메일 위협 검색 시작
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965151"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="37601-104">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="37601-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="37601-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="37601-105">**Applies to:**</span></span>
- <span data-ttu-id="37601-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37601-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="37601-107">고급 검색을 사용하여 전자 메일 위협 검색을 시작하고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="37601-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="37601-108">다음 방법을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="37601-108">Try this:</span></span>

<span data-ttu-id="37601-109">[Office 365용 Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) 문서의 [시작](/microsoft-365/security/office-365-security/defender-for-office-365) 섹션에는 다음과 같은 논리적 초기 구성 덩어리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37601-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="37601-110">이름에 'Anti'가 있는 모든 것을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="37601-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="37601-111">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="37601-111">Anti-malware</span></span>
   - <span data-ttu-id="37601-112">피싱 방지</span><span class="sxs-lookup"><span data-stu-id="37601-112">Anti-phishing</span></span>
   - <span data-ttu-id="37601-113">스팸 방지</span><span class="sxs-lookup"><span data-stu-id="37601-113">Anti-spam</span></span>
2. <span data-ttu-id="37601-114">이름에 'Safe'로 모든 것을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="37601-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="37601-115">안전한 링크</span><span class="sxs-lookup"><span data-stu-id="37601-115">Safe Links</span></span>
   - <span data-ttu-id="37601-116">안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="37601-116">Safe Attachments</span></span>
3. <span data-ttu-id="37601-117">작업을 방어할 때 (예:</span><span class="sxs-lookup"><span data-stu-id="37601-117">Defend the workloads (ex.</span></span> <span data-ttu-id="37601-118">SharePoint 온라인, OneDrive 및 Teams).</span><span class="sxs-lookup"><span data-stu-id="37601-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="37601-119">제로 아워 자동 제거로 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="37601-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="37601-120">[링크](../office-365-security/protect-against-threats.md)를 통해 바로 시작하여 첫날에 구성을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="37601-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="37601-121">**시작** 의 마지막 단계는 ZAP라고도 하는 **제로 아워 자동 제거** 를 사용해 사용자를 보호하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37601-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="37601-122">배달 후에 의심스러운 메일이나 악의적인 메일에 대한 제로 아워 자동 제거가 성공적이었는지 알아보는 것은 매우 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37601-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="37601-123">Kusto 쿼리 언어로 빠르게 검색하여 문제를 검색할 수 있다는 점은 이러한 두 보안 센터의 수렴한 이점입니다.</span><span class="sxs-lookup"><span data-stu-id="37601-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="37601-124">보안 팀은 헌팅 고급 헌팅에서 다음  단계를 수행하여 ZAP 누락을 [](https://security.microsoft.com/advanced-hunting) \> **모니터링할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="37601-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="37601-125">고급 헌팅 페이지에서 쿼리를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="37601-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="37601-126">다음 쿼리를 쿼리 창에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="37601-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="37601-127">쿼리 **실행 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="37601-127">Select **Run query**.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="쿼리 패널 맨 위에 선택된 쿼리가 있는 고급 헌팅 페이지(헌팅 아래)를 표시하고 Kusto 쿼리를 실행하여 지난 7일 동안의 ZAP 작업을 캡처합니다.":::

<span data-ttu-id="37601-129">이 쿼리의 데이터는 쿼리 자체 아래에 있는 결과 패널에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="37601-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="37601-130">결과에는 사용자 지정 가능한 결과 집합의 'DeviceName', 'AccountDisplayName', 'ZapTime' 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="37601-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="37601-131">레코드에 대한 결과를 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37601-131">Results can also be exported for your records.</span></span> <span data-ttu-id="37601-132">쿼리가 다시 필요하면 **저장** > **다른 이름으로 저장** 을 선택하고 쿼리 목록, 공유 또는 커뮤니티 쿼리에 쿼리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37601-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="37601-133">관련 정보</span><span class="sxs-lookup"><span data-stu-id="37601-133">Related information</span></span>
- [<span data-ttu-id="37601-134">고급 헌팅 모범 사례</span><span class="sxs-lookup"><span data-stu-id="37601-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="37601-135">개요 - 고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="37601-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)

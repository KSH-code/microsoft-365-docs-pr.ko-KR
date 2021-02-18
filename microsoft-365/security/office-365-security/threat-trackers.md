---
title: 위협 트래커 - 신규 및 주목할 만한 사항
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: a097f5ca-eac0-44a4-bbce-365f35b79ed1
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 조직이 보안 문제를 가장 잘 아는 데 도움이 될 수 있도록 새로운 주목할 만한 추적을 포함하여 위협 트래커에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a734085e9bc341424ee40757a21b855442605bcd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287392"
---
# <a name="threat-trackers---new-and-noteworthy"></a><span data-ttu-id="6add9-103">위협 트래커 - 신규 및 주목할 만한 사항</span><span class="sxs-lookup"><span data-stu-id="6add9-103">Threat Trackers - New and Noteworthy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6add9-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="6add9-104">**Applies to**</span></span>
- [<span data-ttu-id="6add9-105">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="6add9-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6add9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6add9-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="6add9-107">[Office 365 위협](office-365-ti.md) 조사 및 대응 기능을 통해 조직의 보안 팀은 사이버 보안 위협을 검색하고 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-107">[Office 365 Threat Investigation and Response](office-365-ti.md) capabilities enable your organization's security team to discover and take action against cybersecurity threats.</span></span> <span data-ttu-id="6add9-108">Office 365 위협 조사 및 응답 기능에는 주목할 만한 추적기 등의 위협 트래커 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-108">Office 365 Threat Investigation and Response capabilities include Threat Tracker features, including Noteworthy trackers.</span></span> <span data-ttu-id="6add9-109">이 문서를 읽고 이러한 새로운 기능 및 다음 단계를 간략하게 살펴 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-109">Read this article to get an overview of these new features and next steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6add9-110">이제 Office 365 위협 인텔리전스가 추가 위협 방지 기능과 함께 Office 365 계획 2용 Microsoft Defender가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-110">Office 365 Threat Intelligence is now Microsoft Defender for Office 365 Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="6add9-111">자세한 내용은 [Microsoft Defender for Office 365](https://products.office.com/exchange/advance-threat-protection) 요금제 및 가격 및 [Office 365용 Microsoft Defender](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)서비스 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6add9-111">To learn more, see [Microsoft Defender for Office 365 plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Microsoft Defender for Office 365 Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="what-are-threat-trackers"></a><span data-ttu-id="6add9-112">위협 트래커란?</span><span class="sxs-lookup"><span data-stu-id="6add9-112">What are Threat Trackers?</span></span>

<span data-ttu-id="6add9-113">위협 추적은 회사에 영향을 줄 수 있는 다양한 사이버 보안 문제에 대한 인텔리전스를 제공하는 정보 위젯 및 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-113">Threat Trackers are informative widgets and views that provide you with intelligence on different cybersecurity issues that might impact your company.</span></span> <span data-ttu-id="6add9-114">예를 들어 위협 트래커를 사용하여 추세 맬웨어 캠페인에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-114">For example, you can view information about trending malware campaigns using Threat Trackers.</span></span>

![맬웨어 캠페인을 보여주는 위협 트래커의 예](../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png)

<span data-ttu-id="6add9-116">대부분의 추적 페이지에는 주기적으로 업데이트되는 추세 번호, 가장 큰 문제 또는 가장 큰 증가를 파악하는 데 도움이  되는 위젯, 더 자세한 정보를 볼 수 있는 탐색기로 연결되는 작업 열의 빠른 링크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-116">Most tracker pages include trending numbers that are updated periodically, widgets to help you understand which issues are the biggest or have grown the most, and a quick link in the **Actions** column that takes you to Explorer, where you can view more detailed information.</span></span>

![탐색기에서 캠페인 정보의 예](../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png)

<span data-ttu-id="6add9-118">추적기 기능은 [Office 365 계획 2용 Microsoft Defender에서](office-365-ti.md)얻을 수 있는 많은 기능 중 일부에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-118">Trackers are just a few of the many great features you get with [Microsoft Defender for Office 365 Plan 2](office-365-ti.md).</span></span> <span data-ttu-id="6add9-119">위협 추적에는 [Noteworth 추적기,](#noteworthy-trackers) [인기](#trending-trackers) [추적기,](#tracked-queries)추적된 쿼리 및 [저장된 쿼리가 포함됩니다.](#saved-queries)</span><span class="sxs-lookup"><span data-stu-id="6add9-119">Threat Trackers include [Noteworth trackers](#noteworthy-trackers), [Trending trackers](#trending-trackers), [Tracked queries](#tracked-queries), and [Saved queries](#saved-queries).</span></span>

<span data-ttu-id="6add9-120">조직에 대한 위협 트래커를 보고 사용하기 위해 보안 & 준수 센터()로 이동하여 위협 관리 <https://protection.office.com>  \> **위협 추적을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6add9-120">To view and use your Threat Trackers for your organization, go to the Security & Compliance Center (<https://protection.office.com>) and choose **Threat management** \> **Threat tracker**.</span></span>

> [!NOTE]
> <span data-ttu-id="6add9-121">위협 트래커를 사용하려면 전역 관리자, 보안 관리자 또는 보안 독자가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-121">To use Threat Trackers, you must be a global administrator, security administrator, or security reader.</span></span> <span data-ttu-id="6add9-122">보안 [및 준수 센터에서 & 참조합니다.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="6add9-122">See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="noteworthy-trackers"></a><span data-ttu-id="6add9-123">주목할 만한 추적기</span><span class="sxs-lookup"><span data-stu-id="6add9-123">Noteworthy trackers</span></span>

<span data-ttu-id="6add9-124">주목할 만한 추적기에서는 알아야 할 크고 작은 위협과 위험을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-124">Noteworthy trackers are where you'll find big and smaller threats and risks that we think you should know about.</span></span> <span data-ttu-id="6add9-125">주목할 만한 추적은 이러한 문제가 Microsoft 365 환경에 존재하는지 여부와, 진행 중이 어떻게 되는지, Office 365의 사용에 미치는 영향에 대한 자세한 내용을 설명하는 문서(예: 문서)에 대한 링크를 찾을 수 있도록 도와 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-125">Noteworthy trackers help you find whether these issues exist in your Microsoft 365 environment, plus link to articles (like this one) that give you more details on what is happening, and how they'll impact your organization's use of Office 365.</span></span> <span data-ttu-id="6add9-126">새로운 위협(예: Wannacry, 페티야) 또는 몇 가지 새로운 문제가 생성될 수 있는 기존 위협(예: 다른 시작 메모 항목 - 네무코드)에 여부에 따라서는 사용자와 보안 팀이 주기적으로 검토하고 검사해야 하는 중요한 새 항목을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-126">Whether it's a big new threat (e.g. Wannacry, Petya) or an existing threat that might create some new challenges (like our other inaugural Noteworthy item - Nemucod), this is where you'll find important new items you and your security team should review and examine periodically.</span></span>

<span data-ttu-id="6add9-127">일반적으로 새로운 위협을 식별하고 이 기능이 제공하는 추가 가시성이 필요할 수 있는 것으로 생각되는 경우 주목할 만한 추적 기능은 몇 주 동안 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-127">Typically Noteworthy trackers will be posted for just a couple of weeks when we identify new threats and think you might need the extra visibility that this feature provides.</span></span> <span data-ttu-id="6add9-128">위협에 대한 가장 큰 위험이 지나면 해당 참고 항목은 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-128">Once the biggest risk for a threat has passed, we'll remove that Noteworthy item.</span></span> <span data-ttu-id="6add9-129">이렇게 하면 다른 관련 새 항목과 함께 목록을 최신으로 최신으로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-129">This way, we can keep the list fresh and up to date with other relevant new items.</span></span>

### <a name="trending-trackers"></a><span data-ttu-id="6add9-130">인기 추적기</span><span class="sxs-lookup"><span data-stu-id="6add9-130">Trending trackers</span></span>

<span data-ttu-id="6add9-131">인기 있는 추적기(이전의 캠페인)는 지난 주에 조직의 전자 메일에 수신된 새로운 위협을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-131">Trending trackers (formerly called Campaigns) highlight new threats received in your organization's email in the past week.</span></span>

![인기 맬웨어 캠페인 위젯의 예](../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png)

<span data-ttu-id="6add9-133">인기 있는 추적기에서 더 광범위한 회사 환경을 공격에 대비하기 위해 검토해야 하는 새로운 위협에 대한 아이디어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-133">Trending trackers give you an idea of new threats you should review to ensure your broader corporate environment is prepared against attacks.</span></span>

### <a name="tracked-queries"></a><span data-ttu-id="6add9-134">추적된 쿼리</span><span class="sxs-lookup"><span data-stu-id="6add9-134">Tracked queries</span></span>

<span data-ttu-id="6add9-135">추적된 쿼리는 저장된 쿼리를 활용하여 조직에서 Microsoft 365 활동을 주기적으로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-135">Tracked queries leverage your saved queries to periodically assess Microsoft 365 activity in your organization.</span></span> <span data-ttu-id="6add9-136">이렇게 하면 이벤트 추세가 제공될 것이고 그 다음 달에 더 많은 이벤트가 발생하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-136">This gives you event trending, with more to come in the coming months.</span></span> <span data-ttu-id="6add9-137">추적된 쿼리는 자동으로 실행되어 쿼리를 다시 실행할 필요 없이 최신 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-137">Tracked queries run automatically, giving you up-to-date information without having to remember to re-run your queries.</span></span>

![선택한 쿼리가 하나인 추적된 쿼리의 예](../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png)

### <a name="saved-queries"></a><span data-ttu-id="6add9-139">저장된 쿼리</span><span class="sxs-lookup"><span data-stu-id="6add9-139">Saved queries</span></span>

<span data-ttu-id="6add9-140">저장된 쿼리는 Trackers 섹션에도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-140">Saved queries are also found in the Trackers section.</span></span> <span data-ttu-id="6add9-141">저장된 쿼리를 사용하여 매번 검색을 다시 만들지 않고도 더 빠르고 반복적으로 되돌리기 원하는 공통 탐색기 검색을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-141">You can use Saved queries to store the common Explorer searches that you want to get back to quicker and repeatedly, without having to re-create the search every time.</span></span>

![선택한 쿼리가 하나인 저장된 쿼리의 예](../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png)

<span data-ttu-id="6add9-143">항상 탐색기 페이지 맨 위에 있는 저장 쿼리 단추를 사용하여  기록 추적기 쿼리 또는 자체 탐색기 쿼리를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-143">You can always save a Noteworthy tracker query or any of your own Explorer queries using the **Save query** button at the top of the Explorer page.</span></span> <span data-ttu-id="6add9-144">여기에 저장된 모든 항목은 추적기 페이지의 **저장된** 쿼리 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-144">Anything saved there will show up in the **Saved queries** list on the Tracker page.</span></span>

## <a name="trackers-and-explorer"></a><span data-ttu-id="6add9-145">추적기 및 탐색기</span><span class="sxs-lookup"><span data-stu-id="6add9-145">Trackers and Explorer</span></span>

<span data-ttu-id="6add9-146">전자 메일, 콘텐츠 또는 Office 활동을 검토하는지(출시 예정) 탐색기 및 추적기는 함께 작업하여 보안 위험 및 위협을 조사하고 추적하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-146">Whether you're reviewing email, content, or Office activities (coming soon), Explorer and Trackers work together to help you investigate and track security risks and threats.</span></span> <span data-ttu-id="6add9-147">또한 추적기에서는 새로운 문제, 주목할만한 문제 및 자주 검색되는 문제를 강조 표시하여 사용자를 보호하는 정보를 제공합니다. 클라우드로 전환할 때 비즈니스를 보다 잘 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-147">All together, Trackers provide you with information to protect your users by highlighting new, notable, and frequently searched issues - ensuring your business is better protected as it moves to the cloud.</span></span>

<span data-ttu-id="6add9-148">또한 보안 및 준수 센터의 개요 오른쪽 아래 모서리에 있는 피드백 단추를 클릭하여 항상 이 또는 기타 Microsoft 365 보안 기능에 대한 피드백을 & [있습니다.](https://support.microsoft.com/office/a5f2fd18-b029-4257-b5a8-ae83e7768c85) </span><span class="sxs-lookup"><span data-stu-id="6add9-148">And remember that you can always provide us feedback on this or other Microsoft 365 security features by clicking on the **Feedback** button in the lower right corner of the [Overview of the Security & Compliance Center](https://support.microsoft.com/office/a5f2fd18-b029-4257-b5a8-ae83e7768c85).</span></span>

![보안 및 준수 센터](../../media/86c330db-8132-4150-8475-220258fe04fb.png)

## <a name="trackers-and-microsoft-defender-for-office-365"></a><span data-ttu-id="6add9-150">Office 365용 추적기 및 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6add9-150">Trackers and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="6add9-151">시작된 주목할 만한 위협으로 안전한 첨부 파일에서 감지된 고급 맬웨어 위협을 [강조하고 있습니다.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="6add9-151">With our inaugural Noteworthy threat, we're highlighting advanced malware threats detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="6add9-152">Office 365 Enterprise E5 고객인 경우 [Office 365용 Microsoft Defender를](office-365-atp.md)사용하지 않는 경우 구독에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-152">If you're an Office 365 Enterprise E5 customer and you're not using [Microsoft Defender for Office 365](office-365-atp.md), you should be - it's included in your subscription.</span></span> <span data-ttu-id="6add9-153">Office 365용 Defender는 Office 365 서비스로 전자 메일 흐름을 필터링하는 다른 보안 도구가 있는 경우에도 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-153">Defender for Office 365 provides value even if you have other security tools filtering email flow with your Office 365 services.</span></span> <span data-ttu-id="6add9-154">그러나 기본 전자 [](atp-safe-links.md) 메일 보안 솔루션이 Office 365를 통해 진행되는 경우 스팸 방지 및 안전한 링크 기능이 가장 잘 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-154">However, anti-spam and [Safe Links](atp-safe-links.md) features work best when your main email security solution is through Office 365.</span></span>

![보안 및 준수 센터의 Office 365용 Microsoft &](../../media/cee70d07-f0c1-459b-843c-2d10c253349f.png)

<span data-ttu-id="6add9-156">오늘날의 위협이 있는 세계에서 기존의 맬웨어 방지 검사만 실행하면 공격으로부터 충분히 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-156">In today's threat-riddled world, running only traditional anti-malware scans means you are not protected well enough against attacks.</span></span> <span data-ttu-id="6add9-157">오늘날의 보다 정교한 공격자는 일반적으로 사용 가능한 도구를 사용하여 기존의 서명 기반 맬웨어 방지 엔진에서 인식되지 않는 새로운, 난독 또는 지연된 공격을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-157">Today's more sophisticated attackers use commonly available tools to create new, obfuscated, or delayed attacks that won't be recognized by traditional signature-based anti-malware engines.</span></span> <span data-ttu-id="6add9-158">안전한 첨부 파일 기능은 전자 메일 첨부 파일을 사용하여 가상 환경에서 이를 확인하여 안전하거나 악의적인지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-158">The Safe Attachments feature takes email attachments and detonates them in a virtual environment to determine whether they're safe or malicious.</span></span> <span data-ttu-id="6add9-159">이 데토니타 프로세스는 가상 컴퓨터 환경에서 각 파일을 연 다음 파일을 연 후 발생하는 과정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-159">This detonation process opens each file in a virtual computer environment, then watches what happens after the file is opened.</span></span> <span data-ttu-id="6add9-160">PDF 및 압축 파일이든 Office 문서이든, 파일에서 악성 코드가 숨겨져 있으며, 희생자가 컴퓨터에서 파일을 열 때만 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-160">Whether it's a PDF, and compressed file, or an Office document, malicious code can be hidden in a file, activating only once the victim opens it on their computer.</span></span> <span data-ttu-id="6add9-161">Office 365용 Defender는 전자 메일 흐름에서 파일을 검색하고 분석하여 동작, 파일 신뢰도 및 다양한 방어 규칙을 기반으로 이러한 위협을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-161">By detonating and analyzing the file in the email flow, Defender for Office 365 capabilities finds these threats based on behaviors, file reputation, and a number of heuristic rules.</span></span>

<span data-ttu-id="6add9-162">새로운 주목할 만한 위협 필터는 안전 첨부 파일을 통해 최근에 검색된 항목을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-162">The new Noteworthy threat filter highlights items that were recently detected through Safe Attachments.</span></span> <span data-ttu-id="6add9-163">이러한 검색은 전자 메일 흐름 또는 다른 고객의 전자 메일에서 이전에 Microsoft 365에서 찾지 못했던 새로운 악성 파일인 항목을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-163">These detections represent items that are new malicious files, not previously found by Microsoft 365 in either your email flow or other customers' email.</span></span> <span data-ttu-id="6add9-164">Noteworthy Threat Tracker의 항목에 주의를 기울여 대상을 지정한 사용자와 고급 분석 탭에 표시된 검색 세부 정보를 검토합니다(탐색기에서 전자 메일의 제목을 클릭하여 찾음).</span><span class="sxs-lookup"><span data-stu-id="6add9-164">Pay attention to the items in the Noteworthy Threat Tracker, see who was targeted by them, and review the detonation details shown on the Advanced Analysis tab (found by clicking on the subject of the email in Explorer).</span></span> <span data-ttu-id="6add9-165">안전 첨부 파일 기능에서 검색된 전자 메일에서만 이 탭을 찾을 수 있습니다. 이 참고 사항 추적기는 해당 필터를 포함하지만 탐색기에서 다른 검색에 해당 필터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-165">Note you'll only find this tab on emails detected by the Safe Attachments capability - this Noteworthy tracker includes that filter, but you can also use that filter for other searches in Explorer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6add9-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6add9-166">Next steps</span></span>

- <span data-ttu-id="6add9-167">조직에 이러한 Office 365 위협 조사 및 응답 기능이 아직 없는 경우 [Office 365](office-365-ti.md)위협 조사 및 응답 기능을 어떻게 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="6add9-167">If your organization doesn't already have these Office 365 Threat Investigation and Response capabilities, see [How do we get Office 365 Threat Investigation and Response capabilities?](office-365-ti.md).</span></span>

- <span data-ttu-id="6add9-168">보안 팀에 올바른 역할 및 사용 권한이 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-168">Make sure that your security team has the correct roles and permissions assigned.</span></span> <span data-ttu-id="6add9-169">전역 관리자 또는 보안 관리자 또는 검색 및 제거 역할이 보안 및 준수 센터에 & 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-169">You must be a global administrator, or have the Security Administrator or Search and Purge role assigned in the Security & Compliance Center.</span></span> <span data-ttu-id="6add9-170">보안 [및 준수 센터에서 & 참조합니다.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="6add9-170">See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="6add9-171">새 추적기에서 Microsoft 365 환경에 표시하는지 감시합니다.</span><span class="sxs-lookup"><span data-stu-id="6add9-171">Watch for the new Trackers to show up in your Microsoft 365 environment.</span></span> <span data-ttu-id="6add9-172">사용 가능한 경우 여기에서 추적을 찾을 수 [있습니다.](https://protection.office.com/)</span><span class="sxs-lookup"><span data-stu-id="6add9-172">When available, you'll find your Trackers [here](https://protection.office.com/).</span></span> <span data-ttu-id="6add9-173">위협  관리 \> **위협 추적기로 이동.**</span><span class="sxs-lookup"><span data-stu-id="6add9-173">Go to **Threat management** \> **Threat trackers**.</span></span>

- <span data-ttu-id="6add9-174">아직 수행하지 않은 경우 안전한 링크 및 안전한 첨부 파일을 포함하여 조직용 [Office 365용 Microsoft Defender에](office-365-atp.md) 대해 자세히 알아보고 [구성하세요.](atp-safe-attachments.md) [](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="6add9-174">If you haven't already done so, learn more about and configure [Microsoft Defender for Office 365](office-365-atp.md) for your organization, including [Safe links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md).</span></span>

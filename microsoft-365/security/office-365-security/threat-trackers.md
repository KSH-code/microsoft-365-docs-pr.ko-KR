---
title: 위협 추적기 - 신규 및 주목할 만한 요소
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
description: 조직이 보안 문제의 맨 위에 오게 도와주는 새로운 주목할 만한 추적기 등 위협 추적기에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0a5db47ccd3e1686b6b49174cb9b3c24256b8cbd
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083047"
---
# <a name="threat-trackers---new-and-noteworthy"></a><span data-ttu-id="0a978-103">위협 추적기 - 신규 및 주목할 만한 요소</span><span class="sxs-lookup"><span data-stu-id="0a978-103">Threat Trackers - New and Noteworthy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0a978-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="0a978-104">**Applies to**</span></span>
- [<span data-ttu-id="0a978-105">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="0a978-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0a978-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a978-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0a978-107">[Office 365 위협](office-365-ti.md) 조사 및 대응 기능을 통해 조직의 보안 팀이 사이버 보안 위협을 검색하고 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-107">[Office 365 Threat Investigation and Response](office-365-ti.md) capabilities enable your organization's security team to discover and take action against cybersecurity threats.</span></span> <span data-ttu-id="0a978-108">Office 365 위협 조사 및 응답 기능에는 주목할 만한 추적기 등의 위협 추적기 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-108">Office 365 Threat Investigation and Response capabilities include Threat Tracker features, including Noteworthy trackers.</span></span> <span data-ttu-id="0a978-109">이 문서를 읽고 이러한 새로운 기능과 다음 단계를 간략하게 살펴 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-109">Read this article to get an overview of these new features and next steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a978-110">Office 365 위협 인텔리전스가 추가 위협 방지 기능과 Office 365 계획 2에 대한 Microsoft Defender입니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-110">Office 365 Threat Intelligence is now Microsoft Defender for Office 365 Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="0a978-111">자세한 내용은 Microsoft [Defender for Office 365](https://products.office.com/exchange/advance-threat-protection) 및 Microsoft [Defender for Office 365 참조하세요.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="0a978-111">To learn more, see [Microsoft Defender for Office 365 plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Microsoft Defender for Office 365 Service Description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="what-are-threat-trackers"></a><span data-ttu-id="0a978-112">위협 트래커란?</span><span class="sxs-lookup"><span data-stu-id="0a978-112">What are Threat Trackers?</span></span>

<span data-ttu-id="0a978-113">위협 트래커는 회사에 영향을 줄 수 있는 다양한 사이버 보안 문제에 대한 인텔리전스를 제공하는 정보 위젯 및 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-113">Threat Trackers are informative widgets and views that provide you with intelligence on different cybersecurity issues that might impact your company.</span></span> <span data-ttu-id="0a978-114">예를 들어 위협 트래커를 사용하여 추세 맬웨어 캠페인에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-114">For example, you can view information about trending malware campaigns using Threat Trackers.</span></span>

![맬웨어 캠페인을 표시하는 위협 추적기 예](../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png)

<span data-ttu-id="0a978-116">대부분의 트래커 페이지에는 주기적으로 업데이트되는 추세 번호, 가장 큰 문제 또는 증가한 문제를 이해하는 데 도움이  되는 위젯, 더 자세한 정보를 볼 수 있는 탐색기로 연결되는 작업 열의 빠른 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-116">Most tracker pages include trending numbers that are updated periodically, widgets to help you understand which issues are the biggest or have grown the most, and a quick link in the **Actions** column that takes you to Explorer, where you can view more detailed information.</span></span>

![탐색기에서 캠페인 정보의 예](../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png)

<span data-ttu-id="0a978-118">추적기 기능은 계획 [2용 Microsoft Defender에서](office-365-ti.md)얻을 수 있는 몇 가지 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-118">Trackers are just a few of the many great features you get with [Microsoft Defender for Office 365 Plan 2](office-365-ti.md).</span></span> <span data-ttu-id="0a978-119">위협 추적기에는 [주목할만한](#noteworthy-trackers)추적기, [인기](#trending-trackers)트래커, 추적된 [쿼리](#tracked-queries)및 저장된 [쿼리가 포함됩니다.](#saved-queries)</span><span class="sxs-lookup"><span data-stu-id="0a978-119">Threat Trackers include [Noteworth trackers](#noteworthy-trackers), [Trending trackers](#trending-trackers), [Tracked queries](#tracked-queries), and [Saved queries](#saved-queries).</span></span>

<span data-ttu-id="0a978-120">조직에 대한 위협 추적기 보기 및 사용을 위해 Microsoft 365 Defender 포털()으로 이동하여 전자 메일 <https://security.microsoft.com> & **위협** \> **추적기 를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="0a978-120">To view and use your Threat Trackers for your organization, go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and choose **Email & collaboration** \> **Threat tracker**.</span></span>

> [!NOTE]
> <span data-ttu-id="0a978-121">위협 추적기를 사용하려면 전역 관리자, 보안 관리자 또는 보안 읽기 권한자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-121">To use Threat Trackers, you must be a global administrator, security administrator, or security reader.</span></span> <span data-ttu-id="0a978-122">웹 [사이트 포털의 Microsoft 365 Defender 참조합니다.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="0a978-122">See [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

### <a name="noteworthy-trackers"></a><span data-ttu-id="0a978-123">주목할 만한 추적기</span><span class="sxs-lookup"><span data-stu-id="0a978-123">Noteworthy trackers</span></span>

<span data-ttu-id="0a978-124">주목할 만한 추적기에서는 알아야 할 크고 작은 위협과 위험을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-124">Noteworthy trackers are where you'll find big and smaller threats and risks that we think you should know about.</span></span> <span data-ttu-id="0a978-125">주목할 만한 트래커는 이러한 문제가 Microsoft 365 환경에 존재하는지 여부와 진행되는 문제에 대한 자세한 내용을 설명하는 문서(예: 문서)에 대한 링크, 그리고 이러한 문제가 조직의 조직 사용에 미치는 영향을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="0a978-125">Noteworthy trackers help you find whether these issues exist in your Microsoft 365 environment, plus link to articles (like this one) that give you more details on what is happening, and how they'll impact your organization's use of Office 365.</span></span> <span data-ttu-id="0a978-126">새로운 위협(예: Wannacry, 페티야)이든, 새로운 과제를 만들 수 있는 기존 위협(예: 다른 취임 주의 항목 - Nemucod)이든, 이를 통해 사용자와 보안 팀이 주기적으로 검토하고 검사해야 하는 중요한 새 항목을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-126">Whether it's a big new threat (e.g. Wannacry, Petya) or an existing threat that might create some new challenges (like our other inaugural Noteworthy item - Nemucod), this is where you'll find important new items you and your security team should review and examine periodically.</span></span>

<span data-ttu-id="0a978-127">일반적으로 새로운 위협을 식별하고 이 기능이 제공하는 추가 가시성이 필요할 수 있는 것으로 생각될 때 주목할 만한 트래커가 몇 주 동안 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-127">Typically Noteworthy trackers will be posted for just a couple of weeks when we identify new threats and think you might need the extra visibility that this feature provides.</span></span> <span data-ttu-id="0a978-128">위협에 대한 가장 큰 위험이 지나면 해당 주목할 만한 항목이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-128">Once the biggest risk for a threat has passed, we'll remove that Noteworthy item.</span></span> <span data-ttu-id="0a978-129">이렇게 하면 다른 관련 새 항목과 함께 목록을 최신으로 최신으로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-129">This way, we can keep the list fresh and up to date with other relevant new items.</span></span>

### <a name="trending-trackers"></a><span data-ttu-id="0a978-130">인기 트래커</span><span class="sxs-lookup"><span data-stu-id="0a978-130">Trending trackers</span></span>

<span data-ttu-id="0a978-131">인기 있는 추적기(이전의 캠페인)는 지난 주에 조직의 전자 메일에 수신된 새로운 위협을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-131">Trending trackers (formerly called Campaigns) highlight new threats received in your organization's email in the past week.</span></span>

![인기 맬웨어 캠페인 위젯의 예](../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png)

<span data-ttu-id="0a978-133">인기 트래커는 더 광범위한 회사 환경을 공격에 대비하기 위해 검토해야 하는 새로운 위협에 대한 아이디어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-133">Trending trackers give you an idea of new threats you should review to ensure your broader corporate environment is prepared against attacks.</span></span>

### <a name="tracked-queries"></a><span data-ttu-id="0a978-134">추적된 쿼리</span><span class="sxs-lookup"><span data-stu-id="0a978-134">Tracked queries</span></span>

<span data-ttu-id="0a978-135">추적된 쿼리는 저장된 쿼리를 활용하여 조직의 Microsoft 365 주기적으로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-135">Tracked queries leverage your saved queries to periodically assess Microsoft 365 activity in your organization.</span></span> <span data-ttu-id="0a978-136">이를 통해 이벤트 추세가 제공될 수 있습니다. 그 다음 몇 개월에 더 많은 이벤트가 제공될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-136">This gives you event trending, with more to come in the coming months.</span></span> <span data-ttu-id="0a978-137">추적된 쿼리는 자동으로 실행되며 쿼리를 다시 실행할 필요 없이 최신 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-137">Tracked queries run automatically, giving you up-to-date information without having to remember to re-run your queries.</span></span>

![선택한 쿼리가 하나인 추적된 쿼리의 예](../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png)

### <a name="saved-queries"></a><span data-ttu-id="0a978-139">저장된 쿼리</span><span class="sxs-lookup"><span data-stu-id="0a978-139">Saved queries</span></span>

<span data-ttu-id="0a978-140">저장된 쿼리는 추적기 섹션에도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-140">Saved queries are also found in the Trackers section.</span></span> <span data-ttu-id="0a978-141">저장된 쿼리를 사용하여 매번 검색을 다시 만들지 않고도 더 빠르고 반복적으로 돌아가고자 하는 일반적인 탐색기 검색을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-141">You can use Saved queries to store the common Explorer searches that you want to get back to quicker and repeatedly, without having to re-create the search every time.</span></span>

![선택한 쿼리가 하나인 저장된 쿼리의 예](../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png)

<span data-ttu-id="0a978-143">항상 탐색기 페이지의 맨 위에 있는 저장 쿼리 단추를 사용하여  주목할만한 추적기 쿼리 또는 사용자 자신의 탐색기 쿼리를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-143">You can always save a Noteworthy tracker query or any of your own Explorer queries using the **Save query** button at the top of the Explorer page.</span></span> <span data-ttu-id="0a978-144">저장한 모든 항목은 추적기 페이지의 **저장된** 쿼리 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-144">Anything saved there will show up in the **Saved queries** list on the Tracker page.</span></span>

## <a name="trackers-and-explorer"></a><span data-ttu-id="0a978-145">추적기 및 탐색기</span><span class="sxs-lookup"><span data-stu-id="0a978-145">Trackers and Explorer</span></span>

<span data-ttu-id="0a978-146">전자 메일, 콘텐츠 또는 Office 활동(출시 예정)을 검토하는지 여부에 관계가 없습니다. 탐색기 및 추적기는 함께 작동하여 보안 위험과 위협을 조사하고 추적하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-146">Whether you're reviewing email, content, or Office activities (coming soon), Explorer and Trackers work together to help you investigate and track security risks and threats.</span></span> <span data-ttu-id="0a978-147">추적기에서 새로운, 주목할만한 자주 검색되는 문제를 강조 표시하여 사용자를 보호하는 정보를 제공합니다. 클라우드로 전환할 때 비즈니스를 보다 잘 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-147">All together, Trackers provide you with information to protect your users by highlighting new, notable, and frequently searched issues - ensuring your business is better protected as it moves to the cloud.</span></span>

<span data-ttu-id="0a978-148">또한 오른쪽 아래 모서리에 있는 피드백 단추를 클릭하여 항상 이 또는  기타 Microsoft 365 보안 기능에 대한 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-148">And remember that you can always provide us feedback on this or other Microsoft 365 security features by clicking on the **Feedback** button in the lower-right corner.</span></span>

![Microsoft 365 Defender 포털](../../media/microsoft-365-defender-portal.png)

## <a name="trackers-and-microsoft-defender-for-office-365"></a><span data-ttu-id="0a978-150">트래커 및 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0a978-150">Trackers and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0a978-151">취임 후의 주목할 만한 위협으로, 첨부 파일 에서 검색된 고급 [맬웨어 위협을 금고 있습니다.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="0a978-151">With our inaugural Noteworthy threat, we're highlighting advanced malware threats detected by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="0a978-152">E5 고객으로 Office 365 Enterprise Microsoft [Defender를](defender-for-office-365.md)Office 365 경우 구독에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-152">If you're an Office 365 Enterprise E5 customer and you're not using [Microsoft Defender for Office 365](defender-for-office-365.md), you should be - it's included in your subscription.</span></span> <span data-ttu-id="0a978-153">Defender for Office 365 서비스를 사용하여 전자 메일 흐름을 필터링하는 다른 보안 도구가 있는 경우에도 Office 365 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-153">Defender for Office 365 provides value even if you have other security tools filtering email flow with your Office 365 services.</span></span> <span data-ttu-id="0a978-154">그러나 스팸 방지 [](safe-links.md) 및 금고 링크 기능은 기본 전자 메일 보안 솔루션을 통해 작업할 때 가장 Office 365.</span><span class="sxs-lookup"><span data-stu-id="0a978-154">However, anti-spam and [Safe Links](safe-links.md) features work best when your main email security solution is through Office 365.</span></span>

![microsoft Defender for Office 365 포털에서 Microsoft 365 Defender 수 있습니다.](../../media/policies.png)

<span data-ttu-id="0a978-156">오늘날의 위협을 없애는 세계에서 기존의 맬웨어 방지 검사만 실행하면 공격으로부터 충분히 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-156">In today's threat-riddled world, running only traditional anti-malware scans means you are not protected well enough against attacks.</span></span> <span data-ttu-id="0a978-157">오늘날 좀 더 정교한 공격자는 일반적으로 사용할 수 있는 도구를 사용하여 기존의 서명 기반 맬웨어 방지 엔진에서 인식되지 않는 새로운, 난독 또는 지연된 공격을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-157">Today's more sophisticated attackers use commonly available tools to create new, obfuscated, or delayed attacks that won't be recognized by traditional signature-based anti-malware engines.</span></span> <span data-ttu-id="0a978-158">금고 첨부 파일 기능은 전자 메일 첨부 파일을 사용하여 가상 환경에서 이를 확인하여 안전한지 또는 악성인지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-158">The Safe Attachments feature takes email attachments and detonates them in a virtual environment to determine whether they're safe or malicious.</span></span> <span data-ttu-id="0a978-159">이 데이타 프로세스는 가상 컴퓨터 환경에서 각 파일을 연 다음 파일을 연 후 어떤 일이 일어나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-159">This detonation process opens each file in a virtual computer environment, then watches what happens after the file is opened.</span></span> <span data-ttu-id="0a978-160">PDF 및 압축된 파일이든 Office 문서이든, 악성 코드는 파일에 숨겨져 있으며, 사용자가 컴퓨터에서 파일을 열 때만 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-160">Whether it's a PDF, and compressed file, or an Office document, malicious code can be hidden in a file, activating only once the victim opens it on their computer.</span></span> <span data-ttu-id="0a978-161">전자 메일 흐름에서 파일을 검색하고 분석하여 Office 365 기능의 Defender는 동작, 파일 신뢰도 및 다양한추론 규칙을 기반으로 이러한 위협을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-161">By detonating and analyzing the file in the email flow, Defender for Office 365 capabilities finds these threats based on behaviors, file reputation, and a number of heuristic rules.</span></span>

<span data-ttu-id="0a978-162">새로운 주목할 만한 위협 필터는 첨부 파일에서 최근에 금고 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-162">The new Noteworthy threat filter highlights items that were recently detected through Safe Attachments.</span></span> <span data-ttu-id="0a978-163">이러한 검색은 전자 메일 흐름 또는 다른 고객의 전자 메일에서 이전에 Microsoft 365 새로운 악성 파일인 항목을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-163">These detections represent items that are new malicious files, not previously found by Microsoft 365 in either your email flow or other customers' email.</span></span> <span data-ttu-id="0a978-164">Noteworthy Threat Tracker의 항목에 주의를 기울여 대상을 지정한 대상을 확인한 다음 고급 분석 탭에 표시되는 검색 세부 정보를 검토합니다(탐색기에서 전자 메일의 제목을 클릭하여 찾음).</span><span class="sxs-lookup"><span data-stu-id="0a978-164">Pay attention to the items in the Noteworthy Threat Tracker, see who was targeted by them, and review the detonation details shown on the Advanced Analysis tab (found by clicking on the subject of the email in Explorer).</span></span> <span data-ttu-id="0a978-165">참고 금고 첨부 파일 기능에서 검색된 전자 메일에서만 이 탭을 찾을 수 있습니다. 이 주목할 만한 추적기는 해당 필터를 포함하지만 탐색기에서 다른 검색에 해당 필터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-165">Note you'll only find this tab on emails detected by the Safe Attachments capability - this Noteworthy tracker includes that filter, but you can also use that filter for other searches in Explorer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0a978-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0a978-166">Next steps</span></span>

- <span data-ttu-id="0a978-167">조직에 이러한 Office 365 위협 조사 및 대응 기능이 없는 경우 위협 조사 및 대응 Office 365 어떻게 [하나요?를 참조하세요.](office-365-ti.md)</span><span class="sxs-lookup"><span data-stu-id="0a978-167">If your organization doesn't already have these Office 365 Threat Investigation and Response capabilities, see [How do we get Office 365 Threat Investigation and Response capabilities?](office-365-ti.md).</span></span>

- <span data-ttu-id="0a978-168">보안 팀에 올바른 역할 및 사용 권한이 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-168">Make sure that your security team has the correct roles and permissions assigned.</span></span> <span data-ttu-id="0a978-169">전역 관리자 또는 보안 관리자 또는 검색 및 제거 역할이 Microsoft 365 Defender 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-169">You must be a global administrator, or have the Security Administrator or Search and Purge role assigned in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="0a978-170">웹 [사이트 포털의 Microsoft 365 Defender 참조합니다.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="0a978-170">See [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="0a978-171">새 추적기에서 새 트래커가 사용자 환경에 Microsoft 365 감시합니다.</span><span class="sxs-lookup"><span data-stu-id="0a978-171">Watch for the new Trackers to show up in your Microsoft 365 environment.</span></span> <span data-ttu-id="0a978-172">사용 가능한 경우 여기에서 추적기 를 찾을 [수 있습니다.](https://https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="0a978-172">When available, you'll find your Trackers [here](https://https://security.microsoft.com/).</span></span> <span data-ttu-id="0a978-173">전자 메일 & **위협** \> **추적기 로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="0a978-173">Go to **Email & collaboration** \> **Threat tracker**.</span></span>

- <span data-ttu-id="0a978-174">아직 수행하지 않은 경우 조직에서 사용할 수 있도록 [Microsoft Defender를](defender-for-office-365.md) Office 365 링크 [](safe-links.md) 및 첨부 금고 금고 [합니다.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="0a978-174">If you haven't already done so, learn more about and configure [Microsoft Defender for Office 365](defender-for-office-365.md) for your organization, including [Safe links](safe-links.md) and [Safe Attachments](safe-attachments.md).</span></span>

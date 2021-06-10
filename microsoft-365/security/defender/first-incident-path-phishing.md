---
title: 피싱 전자 메일 공격의 예
description: 피싱 공격의 예제 분석을 진행합니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 41a2c73ce5e1c3060d88572f4fa7afe63e193f46
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52299991"
---
# <a name="example-of-a-phishing-email-attack"></a><span data-ttu-id="bee31-104">피싱 전자 메일 공격의 예</span><span class="sxs-lookup"><span data-stu-id="bee31-104">Example of a phishing email attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bee31-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="bee31-105">**Applies to:**</span></span>
- <span data-ttu-id="bee31-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bee31-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bee31-107">Microsoft 365 Defender는 전자 메일을 통해 배달된 악의적인 첨부 파일을 감지하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-107">Microsoft 365 Defender can help detect malicious attachments delivered via email.</span></span> <span data-ttu-id="bee31-108">Office 365 및 규정 준수 [센터는](https://protection.office.com/) Microsoft 365 Defender와 통합되어 보안 분석가가 전자 메일 첨부 파일과 같은 Office 365 위협에 대한 가시성을 확보할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-108">Since the [Office 365 Security and Compliance Center](https://protection.office.com/) integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Office 365, such as through email attachments.</span></span>

<span data-ttu-id="bee31-109">예를 들어 분석가에게 다단계 인시던트가 할당된 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-109">For example, an analyst was assigned a multi-stage incident.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="다단계 인시던트의 예"::: 

<span data-ttu-id="bee31-111">**인시던트의 경고** 탭에 경고 및 이벤트에 대한 Office 365 Microsoft Cloud App Security 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-111">In the **Alerts** tab of the incident, alerts from Defender for Office 365 and Microsoft Cloud App Security are displayed.</span></span> <span data-ttu-id="bee31-112">분석가가 전자 메일 메시지 경고를 선택하여 Office 365 대한 Defender로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-112">The analyst can drill down into the Defender for Office 365 alerts by selecting the email messages alerts.</span></span> <span data-ttu-id="bee31-113">경고의 세부 정보는 왼쪽 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-113">The details of the alert are displayed on the side pane.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="전자 메일 경고의 예":::
 
<span data-ttu-id="bee31-115">아래로 스크롤하면 추가 정보가 표시되어 영향을 미치게 된 악성 파일과 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-115">By scrolling down further, more information is displayed, showing the malicious files and user that was impacted.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="전자 메일 경고의 사용자 및 파일에 미치는 영향의 예":::
  
<span data-ttu-id="bee31-117">경고 **열기 페이지를 선택하면** 링크를 선택하여 다양한 정보를 보다 자세히 볼 수 있는 특정 경고로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-117">Selecting **Open alert page** takes you to the specific alert where various information can be viewed in greater detail by selecting the link.</span></span> <span data-ttu-id="bee31-118">탐색기에서 패널 아래쪽에 있는  메시지 보기를 선택하여 실제 전자 메일 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-118">The actual email message can be viewed by selecting **View messages in Explorer** toward the bottom of the panel.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="경고 세부 정보의 예"::: 

<span data-ttu-id="bee31-120">이 경우 분석가가 전자 메일 제목, 받는 사람, 보낸 사람 및 기타 정보가 표시되는 위협 관리 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-120">This takes the analyst to the Threat Management page where the email Subject, Recipient, Sender, and other information are displayed.</span></span> <span data-ttu-id="bee31-121">특수 작업 **아래에 있는** **ZAP는** 분석가에게 제로 아워 자동 제거 기능이 구현되었다고 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-121">**ZAP** under **Special Actions** tells the analyst that the Zero-hour auto purge feature was implemented.</span></span> <span data-ttu-id="bee31-122">ZAP는 조직 전체의 사서함에서 악성 및 스팸 메시지를 자동으로 감지하고 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-122">ZAP automatically detects and removes malicious and spam messages from mailboxes across the organization.</span></span> <span data-ttu-id="bee31-123">자세한 내용은 에서 [제로 아워 ZAP(자동 제거)를 Exchange Online.](../office-365-security/zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="bee31-123">For more information, see [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="bee31-124">작업을 선택하여 특정 메시지에 대해 다른 작업을 수행할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="bee31-124">Other actions can be taken on specific messages by selecting **Actions**.</span></span> 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="다른 작업의 예는 전자 메일 메시지에 대해 수행할 수 있습니다."::: 

## <a name="next-step"></a><span data-ttu-id="bee31-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bee31-126">Next step</span></span>

<span data-ttu-id="bee31-127">ID 기반 [공격 조사 경로를](first-incident-path-identity.md) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="bee31-127">See the [identity-based attack](first-incident-path-identity.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="bee31-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bee31-128">See also</span></span>

- [<span data-ttu-id="bee31-129">사고 개요</span><span class="sxs-lookup"><span data-stu-id="bee31-129">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="bee31-130">사고 조사</span><span class="sxs-lookup"><span data-stu-id="bee31-130">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="bee31-131">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="bee31-131">Manage incidents</span></span>](manage-incidents.md)

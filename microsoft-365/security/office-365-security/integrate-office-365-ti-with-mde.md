---
title: 끝점용 Microsoft Defender와 함께 Office 365 Microsoft Defender 사용
f1.keywords:
- NOCSH
keywords: 통합, Microsoft Defender, 끝점용 Microsoft Defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Microsoft Defender를 Office 365 Microsoft Defender for Endpoint를 사용하여 장치 및 전자 메일 콘텐츠에 대한 위협에 대한 자세한 정보를 얻을 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d54e4ec40c636b8b3ea319e79cbad5005850952
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029270"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="a3ce3-104">끝점용 Microsoft Defender와 함께 Office 365 Microsoft Defender 사용</span><span class="sxs-lookup"><span data-stu-id="a3ce3-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a3ce3-105">[Microsoft Defender for Office 365](defender-for-office-365.md) [Microsoft Defender for Endpoint에서 작동하도록 구성할 수 있습니다.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="a3ce3-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="a3ce3-106">Microsoft Defender for Office 365 Microsoft Defender for Endpoint와 통합하면 보안 운영 팀이 사용자의 장치가 위험에 노출될 경우 신속하게 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ce3-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="a3ce3-107">예를 들어 통합이 사용하도록 설정되면 보안 운영 팀은 감지된 전자 메일 메시지의 영향을 받을 수 있는 장치와 끝점용 Microsoft Defender에서 해당 장치에 대해 생성된 최근 알림 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ce3-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="a3ce3-108">다음 이미지는 끝점용 Microsoft Defender 통합을 사용하도록 설정한 경우 장치 탭의 모양을 나타났습니다. </span><span class="sxs-lookup"><span data-stu-id="a3ce3-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![끝점용 Microsoft Defender를 사용하도록 설정하면 경고가 있는 장치 목록을 볼 수 있습니다.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="a3ce3-110">이 예에서는 감지된 전자 메일 메시지의 받는 사람에게 4개의 장치가 있으며, 다른 하나는 경고를 표시하는지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ce3-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="a3ce3-111">장치에 대한 링크를 클릭하면 해당 페이지가 [](../defender-endpoint/microsoft-defender-security-center.md) Microsoft 365 Defender(이전의 Microsoft Defender 보안 센터)에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a3ce3-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender security center).</span></span>

> [!TIP]
> <span data-ttu-id="a3ce3-112">Microsoft 365 Defender 포털이 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="a3ce3-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="a3ce3-113">에서 [Microsoft Defender for Endpoint를 Microsoft 365 Defender.](../defender/microsoft-365-security-center-mde.md)</span><span class="sxs-lookup"><span data-stu-id="a3ce3-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="a3ce3-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3ce3-114">Requirements</span></span>

- <span data-ttu-id="a3ce3-115">조직에는 Microsoft Defender for Office 365(또는 Office 365 E5) 및 끝점용 Microsoft Defender가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ce3-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="a3ce3-116">전역 관리자 또는 보안 관리자 역할(예: 보안 관리자)이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3ce3-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="a3ce3-117">자세한 내용은 Microsoft 365 Defender [포털의 사용 권한을 참조하세요.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="a3ce3-117">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="a3ce3-118">탐색기(또는 실시간 [검색)에 액세스할 수 있어야 합니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="a3ce3-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="a3ce3-119">Microsoft Defender for Office 365 Microsoft Defender for Endpoint와 통합</span><span class="sxs-lookup"><span data-stu-id="a3ce3-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="a3ce3-120">Microsoft Defender for Office 365 끝점용 Microsoft Defender와 통합은 Endpoint용 Defender 및 365용 Defender에서 Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3ce3-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="a3ce3-121">전역 관리자 또는 보안 <https://security.microsoft.com/threatexplorer> 관리자()입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ce3-121">As a global administrator or a security administrator,<https://security.microsoft.com/threatexplorer>.</span></span>

2. <span data-ttu-id="a3ce3-122">탐색 창에서 전자 메일 전자 메일 &  \> **탐색기 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3ce3-122">In the navigation pane, choose **Email & collaboration** \> **Explorer**.</span></span>

3. <span data-ttu-id="a3ce3-123">탐색기 **페이지의** 화면 오른쪽 위 모서리에서 MDE 단추를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="a3ce3-123">On the **Explorer** page, in the upper right corner of the screen, click **MDE Settings**.</span></span>

4. <span data-ttu-id="a3ce3-124">나타나는 **Microsoft Defender for Endpoint 연결** 플라이아웃에서 끝점용 **Microsoft Defender에** 커넥트(토글 켜기)를 켜고 닫기 아이콘 닫기 를 ![ ](../../media/scc-toggle-on.png) ![ ](../../media/m365-cc-sc-close-icon.png) **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3ce3-124">In the **Microsoft Defender for Endpoint connection** flyout that appears, turn on **Connect to Microsoft Defender for Endpoint** (![Toggle on](../../media/scc-toggle-on.png)) and then click ![Close icon](../../media/m365-cc-sc-close-icon.png) **Close**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE 연결":::

5. <span data-ttu-id="a3ce3-126">탐색 창으로 돌아가서 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="a3ce3-126">Back in the navigation pane, choose **Settings**.</span></span> <span data-ttu-id="a3ce3-127">On the **설정** page, choose **Endpoints**</span><span class="sxs-lookup"><span data-stu-id="a3ce3-127">On the **Settings** page, choose **Endpoints**</span></span>

6. <span data-ttu-id="a3ce3-128">끝점 **페이지가** 열리면 고급 기능을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3ce3-128">On the **Endpoints** page that opens, choose **Advanced features**.</span></span>

7. <span data-ttu-id="a3ce3-129">아래로 스크롤하여 Office 365 위협 인텔리전스 연결을 **으로** 전환하고( ![ 토글합니다.) ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="a3ce3-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn it on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

   <span data-ttu-id="a3ce3-130">완료되면 기본 설정 저장 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3ce3-130">When you're finished, click **Save preferences**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a3ce3-131">관련 문서</span><span class="sxs-lookup"><span data-stu-id="a3ce3-131">Related articles</span></span>

[<span data-ttu-id="a3ce3-132">보안 위협 조사 및 대응 Office 365</span><span class="sxs-lookup"><span data-stu-id="a3ce3-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="a3ce3-133">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a3ce3-133">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="a3ce3-134">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a3ce3-134">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)

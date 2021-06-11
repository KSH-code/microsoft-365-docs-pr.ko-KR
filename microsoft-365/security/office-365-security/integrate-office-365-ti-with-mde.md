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
ms.openlocfilehash: 63ae9f8c1136a973e4fccb63ecfbaee2639c3f6f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904083"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="37bc9-104">끝점용 Microsoft Defender와 함께 Office 365 Microsoft Defender 사용</span><span class="sxs-lookup"><span data-stu-id="37bc9-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="37bc9-105">[Microsoft Defender for Office 365](defender-for-office-365.md) [Microsoft Defender for Endpoint에서 작동하도록 구성할 수 있습니다.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="37bc9-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="37bc9-106">Microsoft Defender for Office 365 Microsoft Defender for Endpoint와 통합하면 보안 운영 팀이 사용자의 장치가 위험에 노출될 경우 신속하게 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37bc9-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="37bc9-107">예를 들어 통합이 사용하도록 설정되면 보안 운영 팀은 감지된 전자 메일 메시지의 영향을 받을 수 있는 장치와 끝점용 Microsoft Defender에서 해당 장치에 대해 생성된 최근 알림 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37bc9-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="37bc9-108">다음 이미지는 끝점용 Microsoft Defender 통합을 사용하도록 설정한 경우 장치 탭의 모양을 나타났습니다. </span><span class="sxs-lookup"><span data-stu-id="37bc9-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![끝점용 Microsoft Defender를 사용하도록 설정하면 경고가 있는 장치 목록을 볼 수 있습니다.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="37bc9-110">이 예에서는 감지된 전자 메일 메시지의 받는 사람에게 4개의 장치가 있으며, 다른 하나는 경고를 표시하는지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37bc9-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="37bc9-111">디바이스에 대한 링크를 클릭하면 Microsoft 365 [Defender(이전의](../defender-endpoint/microsoft-defender-security-center.md) Microsoft Defender 보안 센터) 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="37bc9-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="37bc9-112">Microsoft 365 Defender 포털은 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="37bc9-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="37bc9-113">[Defender의 끝점에 대한 Microsoft Defender를 Microsoft 365 참조합니다.](../defender/microsoft-365-security-center-mde.md)</span><span class="sxs-lookup"><span data-stu-id="37bc9-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="37bc9-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37bc9-114">Requirements</span></span>

- <span data-ttu-id="37bc9-115">조직에 Microsoft Defender for Office 365(또는 E5용)Office 365 Microsoft Defender가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bc9-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="37bc9-116">전역 관리자 또는 보안 관리자 역할(예: 보안 관리자)이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37bc9-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="37bc9-117">(보안 [및 준수 센터의 & 참조)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="37bc9-117">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="37bc9-118">탐색기(또는 실시간 [검색)에 액세스할 수 있어야 합니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="37bc9-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="37bc9-119">Microsoft Defender for Office 365 Microsoft Defender for Endpoint와 통합</span><span class="sxs-lookup"><span data-stu-id="37bc9-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="37bc9-120">Microsoft Defender for Office 365 끝점용 Microsoft Defender와 통합은 Endpoint용 Defender 및 365용 Defender에서 Office 365.</span><span class="sxs-lookup"><span data-stu-id="37bc9-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="37bc9-121">전역 관리자 또는 보안 관리자로 이동하여 [https://protection.office.com](https://protection.office.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="37bc9-121">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="37bc9-122">(이 경우 Office 365 보안 & 센터로 진행됩니다.)</span><span class="sxs-lookup"><span data-stu-id="37bc9-122">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="37bc9-123">탐색 창에서 위협 관리 **탐색기를** \> **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="37bc9-123">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![위협 관리 메뉴의 탐색기](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="37bc9-125">In the upper right corner of the screen, choose **Defender for Endpoint 설정 (MDE 설정)**.</span><span class="sxs-lookup"><span data-stu-id="37bc9-125">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="37bc9-126">끝점 연결용 Microsoft Defender 대화 상자에서 **끝점용 Microsoft Defender에 커넥트 를 으로 전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="37bc9-126">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![끝점 연결용 Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="37bc9-128">Defender Microsoft 365(로 [https://security.microsoft.com](https://security.microsoft.com) 이동).</span><span class="sxs-lookup"><span data-stu-id="37bc9-128">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="37bc9-129">탐색 모음에서 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="37bc9-129">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="37bc9-130">그런 다음 **일반에서** 고급 기능을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="37bc9-130">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="37bc9-131">아래로 스크롤하여 **Office 365 위협 인텔리전스** 연결을 으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="37bc9-131">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 인텔리전스 연결](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="37bc9-133">관련 문서</span><span class="sxs-lookup"><span data-stu-id="37bc9-133">Related articles</span></span>

[<span data-ttu-id="37bc9-134">보안 위협 조사 및 대응 Office 365</span><span class="sxs-lookup"><span data-stu-id="37bc9-134">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="37bc9-135">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="37bc9-135">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="37bc9-136">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="37bc9-136">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)

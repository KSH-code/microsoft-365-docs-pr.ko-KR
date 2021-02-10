---
title: 끝점용 Microsoft Defender와 함께 Office 365용 Microsoft Defender 사용
f1.keywords:
- NOCSH
keywords: 통합, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 끝점용 Microsoft Defender와 함께 Office 365용 Microsoft Defender를 사용하여 장치 및 전자 메일 콘텐츠에 대한 위협에 대한 자세한 정보를 얻을 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 035834e1e4855c0e47defed06043a5fdbd0e63bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166090"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="0502f-104">끝점용 Microsoft Defender와 함께 Office 365용 Microsoft Defender 사용</span><span class="sxs-lookup"><span data-stu-id="0502f-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0502f-105">[Office 365용 Microsoft Defender는](office-365-atp.md) [끝점용 Microsoft Defender와](https://docs.microsoft.com/windows/security/threat-protection)함께 작동하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="0502f-106">Office 365용 Microsoft Defender를 끝점용 Microsoft Defender와 통합하면 보안 운영 팀이 사용자의 장치가 위험에 노출될 경우 신속하게 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="0502f-107">예를 들어 통합을 사용하도록 설정하면 보안 운영 팀에서 검색된 전자 메일 메시지의 영향을 받을 수 있는 장치와 끝점용 Microsoft Defender에서 해당 장치에 대해 생성된 최근 알림의 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="0502f-108">다음 이미지는 끝점용 Microsoft Defender 통합을 사용하도록 설정한 경우 장치 탭의 모양을 나타냈습니다. </span><span class="sxs-lookup"><span data-stu-id="0502f-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![끝점용 Microsoft Defender를 사용하도록 설정하면 경고가 있는 장치 목록을 볼 수 있습니다.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="0502f-110">이 예에서는 검색된 전자 메일 메시지의 받는 사람이 4개의 장치가 있으며, 다른 하나는 경고를 표시하는지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="0502f-111">장치에 대한 링크를 클릭하면 Microsoft Defender 보안 센터()에서 해당 페이지가 <https://securitycenter.windows.com> 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="0502f-112">**[Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** 보안 센터(엔드포인트 포털용 Microsoft Defender)에 대해 자세히 알아보는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="0502f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0502f-113">Requirements</span></span>

- <span data-ttu-id="0502f-114">조직에는 Office 365용 Microsoft Defender(또는 Office 365 E5) 및 끝점용 Microsoft Defender가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="0502f-115">전역 관리자 또는 보안 관리자 역할(예: 보안 관리자)이 보안 및 준수 센터에 [& 있어야 합니다.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="0502f-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="0502f-116">(보안 [및 준수 센터의 & 참조)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="0502f-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="0502f-117">보안 및 준수 [](threat-explorer.md) 센터와 Microsoft Defender 보안 센터에서 탐색기(& 검색)에 모두 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="0502f-118">끝점용 Microsoft Defender와 Office 365용 Microsoft Defender를 통합</span><span class="sxs-lookup"><span data-stu-id="0502f-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="0502f-119">Office 365용 Microsoft Defender를 끝점용 Microsoft Defender와 통합하는 것은 보안 & 준수 센터와 Microsoft Defender 보안 센터를 모두 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="0502f-120">전역 관리자 또는 보안 관리자로 이동하여 <https://protection.office.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="0502f-121">Office 365 보안 및 준수 센터로 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="0502f-122">탐색 창에서 위협 관리 **탐색기를** \> **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0502f-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![위협 관리 메뉴의 탐색기](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="0502f-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span><span class="sxs-lookup"><span data-stu-id="0502f-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="0502f-125">끝점용 Microsoft Defender 연결 대화 상자에서 **끝점용 Microsoft Defender에 연결 기능을 켜고**</span><span class="sxs-lookup"><span data-stu-id="0502f-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![끝점용 Microsoft Defender 연결](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="0502f-127">Microsoft Defender 보안 센터()로 <https://securitycenter.windows.com> 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="0502f-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="0502f-128">탐색 모음에서 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0502f-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="0502f-129">그런 다음 **일반에서** 고급 **기능을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0502f-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="0502f-130">아래로 스크롤하여 **Office 365 위협** 인텔리전스 연결로 이동한 다음 연결을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0502f-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 위협 인텔리전스 연결](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="0502f-132">관련 문서</span><span class="sxs-lookup"><span data-stu-id="0502f-132">Related articles</span></span>

[<span data-ttu-id="0502f-133">Office 365의 위협 조사 및 대응 기능</span><span class="sxs-lookup"><span data-stu-id="0502f-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="0502f-134">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0502f-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="0502f-135">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0502f-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)

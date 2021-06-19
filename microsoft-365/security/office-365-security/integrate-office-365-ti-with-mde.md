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
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028884"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="39113-104">끝점용 Microsoft Defender와 함께 Office 365 Microsoft Defender 사용</span><span class="sxs-lookup"><span data-stu-id="39113-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="39113-105">[Microsoft Defender for Office 365](defender-for-office-365.md) [Microsoft Defender for Endpoint에서 작동하도록 구성할 수 있습니다.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="39113-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="39113-106">Microsoft Defender for Office 365 Microsoft Defender for Endpoint와 통합하면 보안 운영 팀이 사용자의 장치가 위험에 노출될 경우 신속하게 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39113-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="39113-107">예를 들어 통합이 사용하도록 설정되면 보안 운영 팀은 감지된 전자 메일 메시지의 영향을 받을 수 있는 장치와 끝점용 Microsoft Defender에서 해당 장치에 대해 생성된 최근 알림 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39113-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="39113-108">다음 이미지는 끝점용 Microsoft Defender 통합을 사용하도록 설정한 경우 장치 탭의 모양을 나타났습니다. </span><span class="sxs-lookup"><span data-stu-id="39113-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![끝점용 Microsoft Defender를 사용하도록 설정하면 경고가 있는 장치 목록을 볼 수 있습니다.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="39113-110">이 예에서는 감지된 전자 메일 메시지의 받는 사람에게 4개의 장치가 있으며, 다른 하나는 경고를 표시하는지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39113-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="39113-111">디바이스에 대한 링크를 클릭하면 해당 페이지가 [Microsoft 365 Defender(이전의](../defender-endpoint/microsoft-defender-security-center.md) Microsoft Defender 보안 센터).</span><span class="sxs-lookup"><span data-stu-id="39113-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="39113-112">Microsoft 365 Defender 포털이 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="39113-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="39113-113">에서 [Microsoft Defender for Endpoint를 Microsoft 365 Defender.](../defender/microsoft-365-security-center-mde.md)</span><span class="sxs-lookup"><span data-stu-id="39113-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="39113-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39113-114">Requirements</span></span>

- <span data-ttu-id="39113-115">조직에는 Microsoft Defender for Office 365(또는 Office 365 E5) 및 끝점용 Microsoft Defender가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39113-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="39113-116">전역 관리자 또는 보안 관리자 역할(예: 보안 관리자)이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39113-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="39113-117">[(의 사용 권한 Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="39113-117">(See [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="39113-118">탐색기(또는 실시간 [검색)에 액세스할 수 있어야 합니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="39113-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="39113-119">Microsoft Defender for Office 365 Microsoft Defender for Endpoint와 통합</span><span class="sxs-lookup"><span data-stu-id="39113-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="39113-120">Microsoft Defender for Office 365 끝점용 Microsoft Defender와 통합은 Endpoint용 Defender 및 365용 Defender에서 Office 365.</span><span class="sxs-lookup"><span data-stu-id="39113-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="39113-121">전역 관리자 또는 보안 관리자로 이동하여 [https://security.microsoft.com](https://security.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="39113-121">As a global administrator or a security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> <span data-ttu-id="39113-122">이 경우 Microsoft 365 Defender 포털로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="39113-122">(This takes you to the Microsoft 365 Defender portal.)</span></span>

2. <span data-ttu-id="39113-123">탐색 창에서 전자 메일 전자 메일 &  \> **탐색기 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="39113-123">In the navigation pane, choose **Email & collaboration** \> **Explorer**.</span></span>

3. <span data-ttu-id="39113-124">화면의 오른쪽 위 모서리에서 **MDE** 단추를 설정.</span><span class="sxs-lookup"><span data-stu-id="39113-124">In the upper right corner of the screen, click **MDE Settings**.</span></span>

4. <span data-ttu-id="39113-125">끝점 연결용 Microsoft Defender 대화 상자에서 **끝점용 Microsoft Defender에 커넥트 를 으로 전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="39113-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE 연결":::

5. <span data-ttu-id="39113-127">Microsoft 365 Defender 포털( 로 [https://security.microsoft.com](https://security.microsoft.com) 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="39113-127">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="39113-128">탐색 모음에서 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="39113-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="39113-129">그런 다음 **일반에서** 고급 기능을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="39113-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="39113-130">아래로 스크롤하여 **Office 365 위협 인텔리전스** 연결을 으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="39113-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 인텔리전스 연결](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="39113-132">관련 문서</span><span class="sxs-lookup"><span data-stu-id="39113-132">Related articles</span></span>

[<span data-ttu-id="39113-133">보안 위협 조사 및 대응 Office 365</span><span class="sxs-lookup"><span data-stu-id="39113-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="39113-134">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="39113-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="39113-135">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="39113-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)

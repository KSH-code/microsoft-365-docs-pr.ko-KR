---
title: Microsoft defender for Office 365 with Endpoint for for 끝점 사용
f1.keywords:
- NOCSH
keywords: 통합, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Office 365 용 Microsoft Defender for Microsoft Defender Advanced Threat Protection과 함께 사용 하 여 장치 및 전자 메일 콘텐츠에 대 한 위협에 대 한 자세한 정보를 확인할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c95e15c3cf16547843f9d2976dbf9df0d5747c0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48309240"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="51ae6-104">Microsoft defender Advanced Threat Protection과 함께 Microsoft Defender for Office 365 사용</span><span class="sxs-lookup"><span data-stu-id="51ae6-104">Use Microsoft Defender for Office 365 together with Microsoft Defender Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="51ae6-105">[Microsoft defender For Office 365 For](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) [Endpoint에 대](https://docs.microsoft.com/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="51ae6-105">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="51ae6-106">Microsoft defender for Office 365을 끝점에 통합 하면 사용자의 장치가 위험에 처 한 경우 보안 운영 팀이 보다 신속 하 게 작업을 수행 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="51ae6-107">예를 들어 통합을 사용 하도록 설정 하면 보안 운영 팀이 검색 된 전자 메일 메시지의 영향을 받을 가능성이 있는 장치를 볼 수 있을 뿐만 아니라 끝점에 대 한 Microsoft Defender에서 해당 장치에 대 한 최근 경고가 발생 한 횟수를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="51ae6-108">다음 이미지에서는 **장치** 탭에 사용 되는 끝점 통합에 대 한 Microsoft Defender가 있는 것 처럼 보이는 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>
  
![끝점에 대해 Microsoft Defender를 사용 하도록 설정 하면 경고가 있는 장치 목록을 볼 수 있습니다.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="51ae6-110">이 예에서는 검색 된 전자 메일 메시지의 받는 사람에 게 4 개의 장치가 있고 하나에 경고가 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="51ae6-111">장치에 대 한 링크를 클릭 하면 Microsoft Defender 보안 센터 ()에서 해당 페이지가 열립니다 [https://securitycenter.windows.com](https://securitycenter.windows.com) .</span><span class="sxs-lookup"><span data-stu-id="51ae6-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="51ae6-112">**[Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (MICROSOFT defender ATP 포털이 라고도 함)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="51ae6-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="51ae6-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51ae6-113">Requirements</span></span>

- <span data-ttu-id="51ae6-114">조직에 Office 365 (또는 Office 365 E5) 용 Microsoft Defender가 있고 끝점에 대 한 Microsoft Defender가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>
    
- <span data-ttu-id="51ae6-115">전역 관리자 이거나 보안 및 [ &amp; 준수 센터](https://protection.office.com)에서 보안 관리자 역할 (예: 보안 관리자)을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="51ae6-116">( [보안 및 &amp; 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)참조)</span><span class="sxs-lookup"><span data-stu-id="51ae6-116">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="51ae6-117">보안 & 준수 센터 및 Microsoft Defender 보안 센터에서 두 [탐색기 (또는 실시간 검색)](threat-explorer.md) 에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="51ae6-118">Microsoft defender for Office 365을 사용 하 여 끝점을 Microsoft에 통합 하려면</span><span class="sxs-lookup"><span data-stu-id="51ae6-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="51ae6-119">보안 & 준수 센터와 Microsoft Defender 보안 센터를 모두 사용 하 여 Office 365 용 microsoft defender (Microsoft Defender for Endpoint)를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="51ae6-120">전역 관리자 또는 보안 관리자로 이동 하 여 [https://protection.office.com](https://protection.office.com) 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-120">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="51ae6-121">(이 경우 Office 365 보안 & 준수 센터가로 이동 합니다.)</span><span class="sxs-lookup"><span data-stu-id="51ae6-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="51ae6-122">탐색 창에서 **위협 관리**  >  **탐색기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-122">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="51ae6-123">![위협 관리 메뉴의 탐색기](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="51ae6-123">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="51ae6-124">화면의 오른쪽 위 모서리에서 **Wdatp 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-124">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="51ae6-125">Microsoft Defender for 끝점 연결 대화 상자에서 **WINDOWS ATP에 연결**을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="51ae6-126">![끝점 연결용 Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="51ae6-126">![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="51ae6-127">Microsoft Defender 보안 센터 ()로 이동 [https://securitycenter.windows.com](https://securitycenter.windows.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-127">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="51ae6-128">탐색 모음에서 **설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="51ae6-129">그런 다음 **일반**에서 **고급 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="51ae6-130">아래로 스크롤하여 **Office 365 위협 인텔리전스 연결**을 설정 하 고 연결을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="51ae6-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="51ae6-131">![Office 365 위협 인텔리전스 연결](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="51ae6-131">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="51ae6-132">관련 문서</span><span class="sxs-lookup"><span data-stu-id="51ae6-132">Related articles</span></span>

[<span data-ttu-id="51ae6-133">Office 365의 위협 조사 및 응답 기능</span><span class="sxs-lookup"><span data-stu-id="51ae6-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="51ae6-134">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="51ae6-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
  
[<span data-ttu-id="51ae6-135">끝점에 대 한 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="51ae6-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)

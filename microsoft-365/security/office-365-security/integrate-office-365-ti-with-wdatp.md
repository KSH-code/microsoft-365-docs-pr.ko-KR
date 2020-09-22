---
title: Office 365 ATP와 Microsoft Defender ATP를 통합
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Microsoft Defender Advanced Threat Protection과 Office 365 Advanced Threat Protection을 통합 하 여 보다 자세한 위협 관리 정보를 확인 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201974"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="547b0-103">Microsoft Defender Advanced Threat Protection을 사용 하 여 Office 365 Advanced Threat Protection 통합</span><span class="sxs-lookup"><span data-stu-id="547b0-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="547b0-104">Microsoft defender [Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection) (MICROSOFT defender atp)에서 작동 하도록 [Office 365 Advanced threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (office 365 atp)을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="547b0-105">Office 365 ATP를 Microsoft Defender ATP와 통합 하면 사용자의 장치가 위험에 처 한 경우 보안 운영 팀이 보다 신속 하 게 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="547b0-106">예를 들어 통합이 설정 되 면 보안 운영 팀이 검색 된 전자 메일 메시지의 영향을 받을 가능성이 있는 장치를 볼 수 있을 뿐 아니라 해당 장치에 Microsoft Defender ATP가 갖고 있는 최근 알림을 몇 개 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="547b0-107">다음 그림에서는 Microsoft Defender ATP 통합을 사용 하도록 설정한 **장치** 탭의 모양을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![Microsoft Defender ATP를 사용 하도록 설정 하면 경고가 있는 장치 목록을 볼 수 있습니다.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="547b0-109">이 예에서는 검색 된 전자 메일 메시지의 받는 사람에 게 4 개의 장치가 있고 하나에 경고가 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="547b0-110">장치에 대 한 링크를 클릭 하면 Microsoft Defender 보안 센터 ()에서 해당 페이지가 열립니다 [https://securitycenter.windows.com](https://securitycenter.windows.com) .</span><span class="sxs-lookup"><span data-stu-id="547b0-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="547b0-111">**[Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (MICROSOFT defender ATP 포털이 라고도 함)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="547b0-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="547b0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="547b0-112">Requirements</span></span>

- <span data-ttu-id="547b0-113">조직에 Office 365 ATP 계획 2 (또는 Office 365 E5)와 Microsoft Defender ATP가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="547b0-114">전역 관리자 이거나 보안 및 [ &amp; 준수 센터](https://protection.office.com)에서 보안 관리자 역할 (예: 보안 관리자)을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="547b0-115">( [보안 및 &amp; 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)참조)</span><span class="sxs-lookup"><span data-stu-id="547b0-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="547b0-116">보안 & 준수 센터 및 Microsoft Defender 보안 센터에서 두 [탐색기 (또는 실시간 검색)](threat-explorer.md) 에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="547b0-117">Office 365 ATP를 Microsoft Defender ATP와 통합 하려면</span><span class="sxs-lookup"><span data-stu-id="547b0-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="547b0-118">Microsoft Defender ATP와 Office 365 ATP를 통합 하는 기능은 보안 & 준수 센터와 Microsoft Defender 보안 센터를 모두 사용 하 여 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="547b0-119">전역 관리자 또는 보안 관리자로 이동 하 여 [https://protection.office.com](https://protection.office.com) 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="547b0-120">(이 경우 Office 365 보안 & 준수 센터가로 이동 합니다.)</span><span class="sxs-lookup"><span data-stu-id="547b0-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="547b0-121">탐색 창에서 **위협 관리**  >  **탐색기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="547b0-122">![위협 관리 메뉴의 탐색기](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="547b0-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="547b0-123">화면의 오른쪽 위 모서리에서 **Wdatp 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="547b0-124">Microsoft Defender ATP 연결 대화 상자에서 **WINDOWS ATP에 연결**을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="547b0-125">![Microsoft Defender ATP 연결](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="547b0-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="547b0-126">Microsoft Defender 보안 센터 ()로 이동 [https://securitycenter.windows.com](https://securitycenter.windows.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="547b0-127">탐색 모음에서 **설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="547b0-128">그런 다음 **일반**에서 **고급 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="547b0-129">아래로 스크롤하여 **Office 365 위협 인텔리전스 연결**을 설정 하 고 연결을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="547b0-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="547b0-130">![Office 365 위협 인텔리전스 연결](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="547b0-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="547b0-131">관련 문서</span><span class="sxs-lookup"><span data-stu-id="547b0-131">Related articles</span></span>

[<span data-ttu-id="547b0-132">Office 365의 위협 조사 및 응답 기능</span><span class="sxs-lookup"><span data-stu-id="547b0-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="547b0-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="547b0-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="547b0-134">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="547b0-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)

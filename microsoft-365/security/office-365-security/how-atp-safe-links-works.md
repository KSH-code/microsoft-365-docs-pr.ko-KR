---
title: ATP 안전한 링크가 작동하는 방식
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 안전한 링크 기능은 Office 문서 및 전자 메일 메시지에서 하이퍼링크를 클릭 하 여 확인할 시간을 제공 합니다. 이 문서를 읽으면 ATP 안전한 링크가 작동 하는 방식을 확인할 수 있습니다.
ms.openlocfilehash: e19d3a1f93d11cd9873e6b5fad9952b018e0a481
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245884"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="161a5-104">ATP 안전한 링크가 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="161a5-104">How ATP Safe Links works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> <span data-ttu-id="161a5-105">Office 365 ATP 안전한 링크가 올바르게 작동 하려면 모든 서비스가 동일한 버전 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="161a5-106">ATP 안전한 링크가 전자 메일의 Url과 함께 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="161a5-106">How ATP Safe Links works with URLs in email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 <span data-ttu-id="161a5-107">전자 메일에 Url 사용</span><span class="sxs-lookup"><span data-stu-id="161a5-107">with URLs in email</span></span>

<span data-ttu-id="161a5-108">높은 수준에서 [ATP 안전한 링크](atp-safe-links.md) 보호는 전자 메일의 url 365 (온-프레미스 아님)에 따라 어떻게 작동 하는지 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-108">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="161a5-109">사용자가 전자 메일 메시지를 받고, 그 중 일부는 Url을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-109">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="161a5-110">모든 전자 메일은 Exchange Online Protection을 통해 진행 되며, 인터넷 프로토콜 (IP) 및 봉투 필터, 서명 기반 맬웨어 방지, 스팸 방지 및 맬웨어 방지 필터가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-110">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="161a5-111">전자 메일이 사용자의 받은 편지함에 도착 합니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-111">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="161a5-112">사용자가 Office 365에 로그인 하 고 해당 전자 메일 받은 편지 함으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-112">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="161a5-113">사용자가 전자 메일 메시지를 열고 전자 메일 메시지의 URL을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-113">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="161a5-114">ATP 안전한 링크 기능은 웹 사이트를 열기 전에 URL을 즉시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-114">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="161a5-115">URL이 차단, 악의적 또는 안전한 것으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-115">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="161a5-116">조직의 [사용자 지정 차단 된 url 목록](set-up-a-custom-blocked-urls-list-atp.md)에 포함 된 웹 사이트에 대 한 URL 인 경우 [경고 페이지가](atp-safe-links-warning-pages.md) 열립니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-116">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="161a5-117">URL이 악성으로 확인 된 웹 사이트에 대 한 것 이면 [경고 페이지가](atp-safe-links-warning-pages.md) 열립니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-117">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="161a5-118">URL이 다운로드 가능한 파일로 이동 하 고 조직의 [ATP 안전한 링크 정책이](set-up-atp-safe-links-policies.md) 이러한 콘텐츠를 검색 하도록 구성 된 경우 다운로드 가능한 파일이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-118">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="161a5-119">URL이 안전한 것으로 확인 되 면 웹 사이트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-119">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="161a5-120">ATP 안전한 링크가 Office 문서의 Url과 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="161a5-120">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="161a5-121">높은 수준에서 [ATP 안전한 링크](atp-safe-links.md) 보호는 Microsoft 365 앱 (Windows, Mac 또는 브라우저의 최신 버전, windows의 경우에는 IOS 또는 Android 장치에 있는 Office 응용 프로그램, 브라우저에서는 OneNote, PowerPoint의 경우 Visio)의 url에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-121">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="161a5-122">사용자의 컴퓨터, 스마트폰 또는 태블릿에서 Microsoft 365 앱에 enterprise 또는 Business Premium을 설치 했습니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-122">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="161a5-123">(또는 브라우저에서 Office를 사용 중인 경우)</span><span class="sxs-lookup"><span data-stu-id="161a5-123">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="161a5-124">사용자가 Word, Excel, PowerPoint, OneNote (브라우저) 또는 Visio (데스크톱)를 열고 회사 또는 학교 계정을 사용 하 여 Office 365 Enterprise에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-124">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="161a5-125">문서에 Url이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-125">The document contains URLs.</span></span>
    
3. <span data-ttu-id="161a5-126">사용자가 문서에서 URL을 클릭 하면 해당 링크는 ATP Safe Links service에 의해 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-126">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="161a5-127">조직의 [사용자 지정 차단 된 url 목록](set-up-a-custom-blocked-urls-list-atp.md)에 포함 된 웹 사이트에 대 한 URL 인 경우 사용자는 [경고 페이지로](atp-safe-links-warning-pages.md)이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-127">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="161a5-128">URL이 악성으로 확인 된 웹 사이트에 대 한 것 인 경우 사용자는 [경고 페이지로](atp-safe-links-warning-pages.md)이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-128">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="161a5-129">URL이 다운로드 가능한 파일로 이동 하 고 [ATP Safe Links 정책이](set-up-atp-safe-links-policies.md) 이러한 다운로드를 검색 하도록 구성 된 경우 다운로드 가능한 파일이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-129">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="161a5-130">URL이 안전한 것으로 간주 되 면 사용자는 웹 사이트로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-130">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="161a5-131">URL 확인이 실패 하면 안전한 링크 보호 기능이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-131">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="161a5-132">데스크톱 클라이언트에서 사이트를 계속 진행 하기 전에 사용자에 게 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-132">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="161a5-133">각 세션을 시작할 때 사용자가 Office에 대 한 안전한 링크를 사용 하도록 설정 되었는지 확인 하기 위해 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="161a5-133">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      

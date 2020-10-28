---
title: Microsoft 보안 점수를 보내는 대상
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수에 제공 되는 새로운 변경 사항에 대해 설명 합니다.
keywords: microsoft 보안 점수, 보안 점수, office 365 보안 점수, microsoft 보안 점수, microsoft 365 보안 센터, 개선 작업
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779251"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="05303-104">Microsoft 보안 점수를 보내는 대상</span><span class="sxs-lookup"><span data-stu-id="05303-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="05303-105">[Microsoft 보안 점수가](microsoft-secure-score.md) 보안 환경을 보다 효율적으로 지원 하 고 유용성이 향상 되도록 하기 위해 곧 향후 몇 가지 사항을 변경 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05303-105">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="05303-106">점수 및 가능한 최대 점수가 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05303-106">Your score and the maximum possible score may change.</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="05303-107">제안된 변경 내용</span><span class="sxs-lookup"><span data-stu-id="05303-107">Proposed changes</span></span>

### <a name="november-2020"></a><span data-ttu-id="05303-108">11 월 2020</span><span class="sxs-lookup"><span data-stu-id="05303-108">November 2020</span></span>

<span data-ttu-id="05303-109">**> Servicenow 공유** 로 이동 하 여 보안 점수를 통해 servicenow 티켓을 만드는 기능을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="05303-109">Removing the ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** .</span></span>

- <span data-ttu-id="05303-110">ServiceNow 커넥터의 미리 보기 기간이 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="05303-110">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="05303-111">이 기능은 2020 종료에 더 이상 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05303-111">This capability will no longer available by the end of 2020.</span></span> <span data-ttu-id="05303-112">다음 단계를 확인 하는 동안 의견을 보내주셔서 사용자에 게 지속적인 지원을 주셔서 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="05303-112">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="05303-113">Microsoft Defender for Endpoint (이전 Microsoft Defender ATP)와 관련 된 18 개의 향상 작업을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="05303-113">Adding 18 improvement actions related to Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

<span data-ttu-id="05303-114">ASR (Attack Surface Reduction) 관련 권장 사항:</span><span class="sxs-lookup"><span data-stu-id="05303-114">Attack Surface Reduction (ASR) related recommendations:</span></span>
- <span data-ttu-id="05303-115">전자 메일 클라이언트 및 webmail에서 실행 가능한 콘텐츠 차단</span><span class="sxs-lookup"><span data-stu-id="05303-115">Block executable content from email client and webmail</span></span>
- <span data-ttu-id="05303-116">모든 Office 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="05303-116">Block all Office applications from creating child processes</span></span>
- <span data-ttu-id="05303-117">Office 응용 프로그램에서 실행 가능한 콘텐츠를 만들지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="05303-117">Block Office applications from creating executable content</span></span>
- <span data-ttu-id="05303-118">Office 응용 프로그램에서 다른 프로세스에 코드를 주입 하지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="05303-118">Block Office applications from injecting code into other processes</span></span>
- <span data-ttu-id="05303-119">다운로드 한 실행 가능한 콘텐츠를 실행 하는 JavaScript 또는 VBScript 차단</span><span class="sxs-lookup"><span data-stu-id="05303-119">Block JavaScript or VBScript from launching downloaded executable content</span></span>
- <span data-ttu-id="05303-120">잠재적으로 난독 처리 된 스크립트의 실행 차단</span><span class="sxs-lookup"><span data-stu-id="05303-120">Block execution of potentially obfuscated scripts</span></span>
- <span data-ttu-id="05303-121">Office 매크로에서 Win32 API 호출 차단</span><span class="sxs-lookup"><span data-stu-id="05303-121">Block Win32 API calls from Office macros</span></span>
- <span data-ttu-id="05303-122">실행 파일이 전파, 연령 또는 신뢰할 수 있는 목록 조건을 충족 하지 않는 이상 실행 되지 않도록 차단</span><span class="sxs-lookup"><span data-stu-id="05303-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
- <span data-ttu-id="05303-123">랜 섬 웨어에 대 한 고급 보호 사용</span><span class="sxs-lookup"><span data-stu-id="05303-123">Use advanced protection against ransomware</span></span>
- <span data-ttu-id="05303-124">Windows 로컬 보안 기관 하위 시스템 (lsass.exe)에서 자격 증명 가로채기 차단</span><span class="sxs-lookup"><span data-stu-id="05303-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
- <span data-ttu-id="05303-125">PSExec 및 WMI 명령에서 시작 되는 프로세스 만들기 차단</span><span class="sxs-lookup"><span data-stu-id="05303-125">Block process creations originating from PSExec and WMI commands</span></span>
- <span data-ttu-id="05303-126">신뢰할 수 없으며 USB에서 실행 되는 서명 되지 않은 프로세스 차단</span><span class="sxs-lookup"><span data-stu-id="05303-126">Block untrusted and unsigned processes that run from USB</span></span>
- <span data-ttu-id="05303-127">Office 통신 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="05303-127">Block Office communication application from creating child processes</span></span>
- <span data-ttu-id="05303-128">하위 프로세스를 만들지 못하도록 Adobe Reader 차단</span><span class="sxs-lookup"><span data-stu-id="05303-128">Block Adobe Reader from creating child processes</span></span>
- <span data-ttu-id="05303-129">WMI 이벤트 구독을 통해 지 속성 차단</span><span class="sxs-lookup"><span data-stu-id="05303-129">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="05303-130">서비스 관련 권장 사항:</span><span class="sxs-lookup"><span data-stu-id="05303-130">Services related recommendations:</span></span>
- <span data-ttu-id="05303-131">Windows 서비스에 대 한 따옴표 붙지 않은 서비스 경로 수정</span><span class="sxs-lookup"><span data-stu-id="05303-131">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="05303-132">서비스 실행 가능한 경로를 일반 보호 위치로 변경</span><span class="sxs-lookup"><span data-stu-id="05303-132">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="05303-133">Windows 레지스트리에서 캐시 된 암호를 사용 하지 않도록 서비스 계정 변경</span><span class="sxs-lookup"><span data-stu-id="05303-133">Change service account to avoid cached password in windows registry</span></span>

## <a name="related-resources"></a><span data-ttu-id="05303-134">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="05303-134">Related resources</span></span>

- [<span data-ttu-id="05303-135">Microsoft 보안 점수 개요</span><span class="sxs-lookup"><span data-stu-id="05303-135">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="05303-136">보안 상태 평가</span><span class="sxs-lookup"><span data-stu-id="05303-136">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="05303-137">Microsoft 보안 점수 기록 및 목표를 충족 하는 추적</span><span class="sxs-lookup"><span data-stu-id="05303-137">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="05303-138">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="05303-138">What's new</span></span>](microsoft-secure-score-whats-new.md)

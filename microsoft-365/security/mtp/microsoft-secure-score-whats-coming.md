---
title: Microsoft 보안 점수가 어떻게 제공 됩니까?
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 세부 정보를 계산 하는 방법 및 보안 관리자가 예상할 수 있는 사항에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 점수, 보안 센터, 개선 작업
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
ms.openlocfilehash: f9bca47c6a47468d0a5a37b77e4f587745bf619d
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545937"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="f71ae-104">Microsoft 보안 점수가 어떻게 제공 됩니까?</span><span class="sxs-lookup"><span data-stu-id="f71ae-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="f71ae-105">Microsoft의 보안 [점수](microsoft-secure-score-new.md) 를 보안 환경을 보다 효율적으로 대표 하 고 유용성을 향상 시키기 위해 곧 몇 가지 사항을 변경 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71ae-105">To make [Microsoft Secure Score](microsoft-secure-score-new.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="f71ae-106">점수와 가능한 최대 점수가 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f71ae-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="f71ae-107">그러나 보안 환경을 변경 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f71ae-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="f71ae-108">최근 변경 내용에 대 한 자세한 내용은 [Microsoft 보안 점수의 새로운 기능](microsoft-secure-score-new.md#whats-new) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f71ae-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score-new.md#whats-new)</span></span>

## <a name="june-2020"></a><span data-ttu-id="f71ae-109">2020 년 6 월</span><span class="sxs-lookup"><span data-stu-id="f71ae-109">June 2020</span></span>

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="f71ae-110">Microsoft Defender Advanced Threat Protection에 대 한 개선 작업 제거</span><span class="sxs-lookup"><span data-stu-id="f71ae-110">Remove improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="f71ae-111">공격 표면 축소 규칙 켜기</span><span class="sxs-lookup"><span data-stu-id="f71ae-111">Turn on Attack Surface Reduction rules</span></span>

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="f71ae-112">Microsoft Defender Advanced Threat Protection에 대 한 개선 작업 추가</span><span class="sxs-lookup"><span data-stu-id="f71ae-112">Add improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="f71ae-113">하위 프로세스를 만들지 못하도록 Adobe Reader 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-113">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="f71ae-114">랜 섬 웨어에 대 한 고급 보호 사용</span><span class="sxs-lookup"><span data-stu-id="f71ae-114">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="f71ae-115">모든 Office 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-115">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="f71ae-116">Office 응용 프로그램에서 실행 가능한 콘텐츠를 만들지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-116">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="f71ae-117">다운로드 한 실행 가능한 콘텐츠를 실행 하는 JavaScript 또는 VBScript 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-117">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="f71ae-118">잠재적으로 난독 처리 된 스크립트의 실행 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-118">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="f71ae-119">전자 메일 클라이언트 및 webmail에서 실행 가능한 콘텐츠 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-119">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="f71ae-120">Office 통신 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-120">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="f71ae-121">신뢰할 수 없으며 USB에서 실행 되는 서명 되지 않은 프로세스 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-121">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="f71ae-122">WMI 이벤트 구독을 통해 지 속성 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-122">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="f71ae-123">Office 응용 프로그램에서 다른 프로세스에 코드를 주입 하지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-123">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="f71ae-124">실행 파일이 전파, 연령 또는 신뢰할 수 있는 목록 조건을 충족 하지 않는 이상 실행 되지 않도록 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-124">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="f71ae-125">PSExec 및 WMI 명령에서 시작 되는 프로세스 만들기 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-125">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="f71ae-126">Windows 로컬 보안 기관 하위 시스템 (lsass.exe)에서 자격 증명 가로채기 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-126">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="f71ae-127">Office 매크로에서 Win32 API 호출 차단</span><span class="sxs-lookup"><span data-stu-id="f71ae-127">Block Win32 API calls from Office macros</span></span>

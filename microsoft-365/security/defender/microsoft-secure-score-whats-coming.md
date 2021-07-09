---
title: Microsoft 보안 점수에 대한 계획
description: 보안 센터의 Microsoft 보안 점수에 대한 새로운 Microsoft 365 설명
keywords: Microsoft 보안 점수, 보안 점수, Office 365 보안 점수, Microsoft 보안 점수, Microsoft 365 보안 센터, 개선 작업
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 910eb16ad33555ca61875a346b50cea7e63b2220
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338556"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="0d902-104">Microsoft 보안 점수에 대한 계획</span><span class="sxs-lookup"><span data-stu-id="0d902-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0d902-105">Microsoft 보안 점수는 보안 센터의 Microsoft 365 https://security.microsoft.com/securescore [있습니다.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="0d902-105">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="0d902-106">제안된 변경 내용</span><span class="sxs-lookup"><span data-stu-id="0d902-106">Proposed changes</span></span>

<span data-ttu-id="0d902-107">Microsoft 보안 점수가 보안 자세를 [](microsoft-secure-score.md) 보다 잘 대표하고 사용성을 개선할 수 있도록 조만히 변경하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d902-107">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="0d902-108">점수와 가능한 최대 점수가 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d902-108">Your score and the maximum possible score may change.</span></span>

### <a name="july-2021"></a><span data-ttu-id="0d902-109">2021년 7월</span><span class="sxs-lookup"><span data-stu-id="0d902-109">July 2021</span></span>

#### <a name="add-improvement-action-related-to-microsoft-teams"></a><span data-ttu-id="0d902-110">사용자와 관련된 개선 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d902-110">Add improvement action related to Microsoft Teams</span></span>

- <span data-ttu-id="0d902-111">전화 접속 사용자가 모임 대기실을 무시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d902-111">Restrict dial-in users from bypassing a meeting lobby.</span></span>
- <span data-ttu-id="0d902-112">외부 참가자가 모임에서 제어하지 Teams 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="0d902-112">Limit external participants from having control in a Teams meeting.</span></span>
- <span data-ttu-id="0d902-113">익명 사용자가 모임을 시작하지 Teams 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="0d902-113">Restrict anonymous users from starting Teams meetings.</span></span>
- <span data-ttu-id="0d902-114">모임에 대해 로비를 설정해야 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d902-114">Require lobbies to be set up for Teams meetings.</span></span>
- <span data-ttu-id="0d902-115">모임에 참석할 수 있는 사용자를 Teams.</span><span class="sxs-lookup"><span data-stu-id="0d902-115">Configure which users are allowed to be present in Teams meetings.</span></span>

#### <a name="add-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="0d902-116">끝점용 Microsoft Defender와 관련된 개선 작업 추가</span><span class="sxs-lookup"><span data-stu-id="0d902-116">Add improvement action related to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="0d902-117">MacOS용 Endpoint 센서 데이터 수집에 대한 Microsoft Defender 수정</span><span class="sxs-lookup"><span data-stu-id="0d902-117">Fix Microsoft Defender for Endpoint sensor data collection for macOS</span></span>
- <span data-ttu-id="0d902-118">MacOS용 끝점 장애 통신에 대한 Microsoft Defender 수정</span><span class="sxs-lookup"><span data-stu-id="0d902-118">Fix Microsoft Defender for Endpoint impaired communications for macOS</span></span>
- <span data-ttu-id="0d902-119">macOS에서 최소 암호 길이를 15자 이상으로 설정</span><span class="sxs-lookup"><span data-stu-id="0d902-119">Set minimum password length to 15 or more characters in macOS</span></span>
- <span data-ttu-id="0d902-120">macOS에서 '암호 기록 적용'을 '24개 이상의 암호'로 설정</span><span class="sxs-lookup"><span data-stu-id="0d902-120">Set 'Enforce password history' to '24 or more password(s)' in macOS</span></span>
- <span data-ttu-id="0d902-121">macOS에서 '최대 암호 사용 기간'을 '90일 이하로 설정하고 0일이 아는 경우'으로 설정</span><span class="sxs-lookup"><span data-stu-id="0d902-121">Set 'Maximum password age' to '90 or fewer days, but not 0' in macOS</span></span>
- <span data-ttu-id="0d902-122">macOS에서 계정 잠금 임계값을 5 이상으로 설정</span><span class="sxs-lookup"><span data-stu-id="0d902-122">Set account lockout threshold to 5 or lower in macOS</span></span>
- <span data-ttu-id="0d902-123">MacOS에서 방화벽 켜기</span><span class="sxs-lookup"><span data-stu-id="0d902-123">Turn on Firewall on macOS</span></span>
- <span data-ttu-id="0d902-124">게이트키퍼 사용</span><span class="sxs-lookup"><span data-stu-id="0d902-124">Enable Gatekeeper</span></span>
- <span data-ttu-id="0d902-125">SIP(시스템 무결성 보호) 사용</span><span class="sxs-lookup"><span data-stu-id="0d902-125">Enable System Integrity Protection (SIP)</span></span>
- <span data-ttu-id="0d902-126">FileVault 디스크 암호화 사용</span><span class="sxs-lookup"><span data-stu-id="0d902-126">Enable FileVault Disk Encryption</span></span>
- <span data-ttu-id="0d902-127">macOS에서 화면 도우미가 시작되면 화면 잠금 설정</span><span class="sxs-lookup"><span data-stu-id="0d902-127">Set screen to lock when screensaver starts in macOS</span></span>
- <span data-ttu-id="0d902-128">macOS에서 화면 보호가 20분 이하로 시작되도록 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0d902-128">Ensure screensaver is set to start in 20 minutes or less in macOS</span></span>
- <span data-ttu-id="0d902-129">보안 홈 폴더</span><span class="sxs-lookup"><span data-stu-id="0d902-129">Secure Home Folders</span></span>
- <span data-ttu-id="0d902-130">macOS에 Microsoft Defender 바이러스 백신 실시간 보호 기능 켜기</span><span class="sxs-lookup"><span data-stu-id="0d902-130">Turn on Microsoft Defender Antivirus real-time protection for macOS</span></span>
- <span data-ttu-id="0d902-131">macOS에 Microsoft Defender 바이러스 백신 PUA 보호 설정</span><span class="sxs-lookup"><span data-stu-id="0d902-131">Turn on Microsoft Defender Antivirus PUA protection in block mode for macOS</span></span>
- <span data-ttu-id="0d902-132">macOS에 Microsoft Defender 바이러스 백신 클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="0d902-132">Enable Microsoft Defender Antivirus cloud-delivered protection for macOS</span></span>
- <span data-ttu-id="0d902-133">macOS에 Microsoft Defender 바이러스 백신 정의 업데이트</span><span class="sxs-lookup"><span data-stu-id="0d902-133">Update Microsoft Defender Antivirus definitions for macOS</span></span>
- <span data-ttu-id="0d902-134">Linux용 Endpoint 센서 데이터 수집용 Microsoft Defender 수정</span><span class="sxs-lookup"><span data-stu-id="0d902-134">Fix Microsoft Defender for Endpoint sensor data collection for Linux</span></span>
- <span data-ttu-id="0d902-135">Linux용 끝점 장애 통신에 대한 Microsoft Defender 수정</span><span class="sxs-lookup"><span data-stu-id="0d902-135">Fix Microsoft Defender for Endpoint impaired communications for Linux</span></span>
- <span data-ttu-id="0d902-136">무제한 액세스 계정</span><span class="sxs-lookup"><span data-stu-id="0d902-136">Unrestricted Access Accounts</span></span>
- <span data-ttu-id="0d902-137">Linux에 대한 Microsoft Defender 바이러스 백신 실시간 보호 켜기</span><span class="sxs-lookup"><span data-stu-id="0d902-137">Turn on Microsoft Defender Antivirus real-time protection for Linux</span></span>
- <span data-ttu-id="0d902-138">Linux에 Microsoft Defender 바이러스 백신 차단 모드에서 PUA 보호 설정</span><span class="sxs-lookup"><span data-stu-id="0d902-138">Turn on Microsoft Defender Antivirus PUA protection in block mode for Linux</span></span>
- <span data-ttu-id="0d902-139">Linux에 Microsoft Defender 바이러스 백신 클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="0d902-139">Enable Microsoft Defender Antivirus cloud-delivered protection for Linux</span></span>
- <span data-ttu-id="0d902-140">Linux Microsoft Defender 바이러스 백신 정의 업데이트</span><span class="sxs-lookup"><span data-stu-id="0d902-140">Update Microsoft Defender Antivirus definitions for Linux</span></span>



## <a name="related-resources"></a><span data-ttu-id="0d902-141">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="0d902-141">Related resources</span></span>

- [<span data-ttu-id="0d902-142">Microsoft 보안 점수 개요</span><span class="sxs-lookup"><span data-stu-id="0d902-142">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="0d902-143">보안 상태 평가</span><span class="sxs-lookup"><span data-stu-id="0d902-143">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="0d902-144">Microsoft 보안 점수 기록 추적 및 목표 충족</span><span class="sxs-lookup"><span data-stu-id="0d902-144">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="0d902-145">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="0d902-145">What's new</span></span>](microsoft-secure-score-whats-new.md)

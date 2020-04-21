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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583718"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="2db84-104">Microsoft 보안 점수가 어떻게 제공 됩니까?</span><span class="sxs-lookup"><span data-stu-id="2db84-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="2db84-105">Microsoft의 보안 [점수](microsoft-secure-score.md) 를 보안 환경을 보다 효율적으로 대표 하 고 유용성을 향상 시키기 위해 곧 몇 가지 사항을 변경 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db84-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="2db84-106">점수와 가능한 최대 점수가 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db84-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="2db84-107">그러나 보안 환경을 변경 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2db84-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="2db84-108">최근 변경 내용에 대 한 자세한 내용은 [Microsoft 보안 점수의 새로운 기능](microsoft-secure-score.md#whats-new) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2db84-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="2db84-109">4 월 21 일 2020</span><span class="sxs-lookup"><span data-stu-id="2db84-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="2db84-110">신뢰할 수 있는 측정에 대 한 기대치를 충족 하지 않는 개선 작업을 제거 하거나 보안 환경을 효과적으로 표현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2db84-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="2db84-111">Microsoft 보안 점수가 의미 있고 모든 개선 조치를 측정할 수 있으며 안정성을 유지 하려면 다음과 같은 개선 작업을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db84-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="2db84-112">문서에 IRM 보호 적용</span><span class="sxs-lookup"><span data-stu-id="2db84-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="2db84-113">데이터 손실 방지 정책 적용</span><span class="sxs-lookup"><span data-stu-id="2db84-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-to-preview"></a><span data-ttu-id="2db84-114">미리 보기에 Azure AD 개선 작업 추가</span><span class="sxs-lookup"><span data-stu-id="2db84-114">Adding Azure AD improvement action to preview</span></span>

<span data-ttu-id="2db84-115">[Microsoft 보안 점수 preview 릴리스에](microsoft-secure-score-preview.md)다음 Azure Active Directory 개선 작업을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db84-115">Adding the following Azure Active Directory improvement action to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="2db84-116">사용자가 관리 되지 않는 응용 프로그램에 동의 하도록 허용 하지 않습니다 (현재 릴리스된 버전에서 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="2db84-116">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-to-preview"></a><span data-ttu-id="2db84-117">미리 보기에 Azure ATP 개선 작업 추가</span><span class="sxs-lookup"><span data-stu-id="2db84-117">Adding Azure ATP improvement actions to preview</span></span>

<span data-ttu-id="2db84-118">[Microsoft 보안 점수 preview 릴리스에](microsoft-secure-score-preview.md)다음과 같은 Azure Advanced Threat Protection 개선 작업을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db84-118">Adding the following Azure Advanced Threat Protection improvement actions to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="2db84-119">도메인 컨트롤러에서 인쇄 스풀러 서비스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="2db84-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="2db84-120">가장을 방지 하도록 보안 되지 않은 Kerberos 위임 수정</span><span class="sxs-lookup"><span data-stu-id="2db84-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="2db84-121">Microsoft 랩를 사용 하 여 로컬 관리자 암호 보호 및 관리</span><span class="sxs-lookup"><span data-stu-id="2db84-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="2db84-122">중요 한 엔터티에 대 한 측면 이동 경로 위험 감소</span><span class="sxs-lookup"><span data-stu-id="2db84-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="2db84-123">중요 한 그룹에서 유휴 계정 제거</span><span class="sxs-lookup"><span data-stu-id="2db84-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="2db84-124">엔터티에서 보안 되지 않은 SID 기록 특성 제거</span><span class="sxs-lookup"><span data-stu-id="2db84-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="2db84-125">보안 되지 않은 계정 특성 확인</span><span class="sxs-lookup"><span data-stu-id="2db84-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="2db84-126">일반 텍스트 자격 증명 노출 중지</span><span class="sxs-lookup"><span data-stu-id="2db84-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="2db84-127">레거시 프로토콜 통신 중지</span><span class="sxs-lookup"><span data-stu-id="2db84-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="2db84-128">약한 암호화 사용 중지</span><span class="sxs-lookup"><span data-stu-id="2db84-128">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a><span data-ttu-id="2db84-129">Microsoft Defender ATP Threat for TVM (& 취약성 관리) 보안 권장 사항 미리 보기</span><span class="sxs-lookup"><span data-stu-id="2db84-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in preview</span></span>

<span data-ttu-id="2db84-130">이제 TVM에서 제공 하는 모든 릴리스된 보안 권장 사항을 [Microsoft 보안 성과의 미리 보기 릴리스로](microsoft-secure-score-preview.md)도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db84-130">All released security recommendations supplied by TVM will now also be available the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md).</span></span>

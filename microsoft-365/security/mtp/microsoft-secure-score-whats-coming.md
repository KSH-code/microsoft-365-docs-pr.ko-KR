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
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541110"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="58f08-104">Microsoft 보안 점수가 어떻게 제공 됩니까?</span><span class="sxs-lookup"><span data-stu-id="58f08-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="58f08-105">Microsoft의 보안 점수를 보안 환경을 보다 효율적으로 대표 하 고 유용성을 향상 시키기 위해 곧 몇 가지 사항을 변경 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58f08-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="58f08-106">점수와 가능한 최대 점수가 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f08-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="58f08-107">그러나 보안 환경을 변경 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="58f08-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="58f08-108">최근 변경 내용에 대 한 자세한 내용은 [Microsoft 보안 점수의 새로운 기능](microsoft-secure-score.md#whats-new) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58f08-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="58f08-109">4 월 21 일 2020</span><span class="sxs-lookup"><span data-stu-id="58f08-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="58f08-110">신뢰할 수 있는 측정에 대 한 기대치를 충족 하지 않는 개선 작업을 제거 하거나 보안 환경을 효과적으로 표현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58f08-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="58f08-111">Microsoft 보안 점수가 의미 있고 모든 개선 조치를 측정할 수 있으며 안정성을 유지 하려면 다음과 같은 개선 작업을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="58f08-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="58f08-112">문서에 IRM 보호 적용</span><span class="sxs-lookup"><span data-stu-id="58f08-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="58f08-113">데이터 손실 방지 정책 적용</span><span class="sxs-lookup"><span data-stu-id="58f08-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a><span data-ttu-id="58f08-114">Preview 버전에서 Azure AD 개선 작업 추가</span><span class="sxs-lookup"><span data-stu-id="58f08-114">Adding Azure AD improvement action in the preview version</span></span>

- <span data-ttu-id="58f08-115">사용자가 관리 되지 않는 응용 프로그램에 동의 하도록 허용 하지 않습니다 (현재 릴리스된 버전에서 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="58f08-115">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a><span data-ttu-id="58f08-116">Preview 버전에서 Azure ATP 개선 작업 추가</span><span class="sxs-lookup"><span data-stu-id="58f08-116">Adding Azure ATP improvement actions in the preview version</span></span>

- <span data-ttu-id="58f08-117">도메인 컨트롤러에서 인쇄 스풀러 서비스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="58f08-117">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="58f08-118">가장을 방지 하도록 보안 되지 않은 Kerberos 위임 수정</span><span class="sxs-lookup"><span data-stu-id="58f08-118">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="58f08-119">Microsoft 랩를 사용 하 여 로컬 관리자 암호 보호 및 관리</span><span class="sxs-lookup"><span data-stu-id="58f08-119">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="58f08-120">중요 한 엔터티에 대 한 측면 이동 경로 위험 감소</span><span class="sxs-lookup"><span data-stu-id="58f08-120">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="58f08-121">중요 한 그룹에서 유휴 계정 제거</span><span class="sxs-lookup"><span data-stu-id="58f08-121">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="58f08-122">엔터티에서 보안 되지 않은 SID 기록 특성 제거</span><span class="sxs-lookup"><span data-stu-id="58f08-122">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="58f08-123">보안 되지 않은 계정 특성 확인</span><span class="sxs-lookup"><span data-stu-id="58f08-123">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="58f08-124">일반 텍스트 자격 증명 노출 중지</span><span class="sxs-lookup"><span data-stu-id="58f08-124">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="58f08-125">레거시 프로토콜 통신 중지</span><span class="sxs-lookup"><span data-stu-id="58f08-125">Stop legacy protocols communication</span></span>
- <span data-ttu-id="58f08-126">약한 암호화 사용 중지</span><span class="sxs-lookup"><span data-stu-id="58f08-126">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a><span data-ttu-id="58f08-127">Preview 버전에서의 Microsoft Defender ATP 위협 & TVM (취약성 관리) 보안 권장 사항에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="58f08-127">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in the preview version</span></span>

- <span data-ttu-id="58f08-128">이제 TVM에서 제공 하는 모든 릴리스된 보안 권장 사항을 Microsoft 보안 점수 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58f08-128">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>

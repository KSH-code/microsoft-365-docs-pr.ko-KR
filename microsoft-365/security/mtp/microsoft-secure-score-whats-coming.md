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
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372006"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="98055-104">Microsoft 보안 점수가 어떻게 제공 됩니까?</span><span class="sxs-lookup"><span data-stu-id="98055-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="98055-105">Microsoft의 보안 점수를 보안 환경을 보다 효율적으로 대표 하 고 유용성을 향상 시키기 위해 곧 몇 가지 사항을 변경 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98055-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="98055-106">점수와 가능한 최대 점수가 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98055-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="98055-107">그러나 보안 환경을 변경 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="98055-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="98055-108">최근 변경 내용에 대 한 자세한 내용은 [Microsoft 보안 점수의 새로운 기능](microsoft-secure-score.md#whats-new) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98055-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="98055-109">16 월 여섯째 2020</span><span class="sxs-lookup"><span data-stu-id="98055-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="98055-110">신뢰할 수 있는 측정에 대 한 기대치를 충족 하지 않는 개선 작업을 제거 하거나 보안 환경을 효과적으로 표현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98055-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="98055-111">Microsoft 보안 점수가 의미 있고 모든 개선 조치를 측정할 수 있으며 안정성을 유지 하려면 다음과 같은 개선 작업을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="98055-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="98055-112">비즈니스용 OneDrive에 사용자 문서 저장</span><span class="sxs-lookup"><span data-stu-id="98055-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="98055-113">Office 365 ATP 안전한 첨부 파일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="98055-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="98055-114">Url을 확인 하기 위한 Office 365 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="98055-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="98055-115">사서함 위임 허용 안 함</span><span class="sxs-lookup"><span data-stu-id="98055-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="98055-116">사이트 및 문서에 대 한 익명 게스트 공유 링크 허용</span><span class="sxs-lookup"><span data-stu-id="98055-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="98055-117">Cloud App Security Console 켜기</span><span class="sxs-lookup"><span data-stu-id="98055-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="98055-118">외부 공유 링크에 대 한 만료 시간 구성</span><span class="sxs-lookup"><span data-stu-id="98055-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="98055-119">Azure AD 개선 작업에 대 한 보안 기본값 지원</span><span class="sxs-lookup"><span data-stu-id="98055-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="98055-120">Microsoft 보안 점수는 [AZURE AD에서 보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 지원 하기 위해 개선 작업을 업데이트 하 여 일반적인 공격에 대 한 미리 구성 된 보안 설정으로 조직을 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98055-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="98055-121">이는 다음과 같은 개선 작업에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98055-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="98055-122">모든 사용자가 보안 액세스를 위해 multi-factor authentication을 완료할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="98055-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="98055-123">관리 역할에 대 한 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="98055-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="98055-124">정책을 사용 하 여 레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="98055-124">Enable policy to block legacy authentication</span></span>

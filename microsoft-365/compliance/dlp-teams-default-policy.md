---
title: Microsoft Teams의 기본 데이터 손실 방지 정책에 대한 자세한 정보(미리 보기)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams의 기본 데이터 손실 방지 정책에 대해 자세히 알아보기
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826249"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="511ac-103">Microsoft Teams의 기본 데이터 손실 방지 정책에 대한 자세한 정보(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="511ac-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="511ac-104">[DLP(데이터](data-loss-prevention-policies.md) 손실 방지) 기능은 비공개 채널 메시지를 포함하여 Microsoft Teams 채팅 및 채널 메시지를 포함하기 위해 확장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="511ac-104">[Data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="511ac-105">이 릴리스의 일부로 규정 준수 센터에 처음 고객을 위한 기본 DLP 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="511ac-105">As a part of this release, we created a default DLP policy for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="511ac-106">적용 대상</span><span class="sxs-lookup"><span data-stu-id="511ac-106">Applies to</span></span>

<span data-ttu-id="511ac-107">하나 이상의 라이선스가 부여된 테넌트 및 활성 Teams 사용자가 있는 모든 테넌트</span><span class="sxs-lookup"><span data-stu-id="511ac-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="511ac-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="511ac-108">ME5,</span></span> 
- <span data-ttu-id="511ac-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="511ac-109">MA5,</span></span> 
- <span data-ttu-id="511ac-110">E5/A5 규정 준수,</span><span class="sxs-lookup"><span data-stu-id="511ac-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="511ac-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="511ac-111">IP+G,</span></span> 
- <span data-ttu-id="511ac-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="511ac-112">OE5,</span></span> 
- <span data-ttu-id="511ac-113">O365 고급 규정 준수</span><span class="sxs-lookup"><span data-stu-id="511ac-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="511ac-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="511ac-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="511ac-115">기본 정책은 어떤 작업을 하나요?</span><span class="sxs-lookup"><span data-stu-id="511ac-115">What does the default policy do?</span></span>

<span data-ttu-id="511ac-116">기본 DLP 정책은 조직 내부 및 외부적으로 공유되는 모든 신용 카드 번호를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="511ac-116">The default DLP policy tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="511ac-117">이 정책은 테넌트의 모든 사용자에 대해 기본적으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="511ac-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="511ac-118">최종 사용자를 위한 정책 팁은 생성하지 않지만 경고 이벤트를 생성하며, 관리자에게 낮은 심각도 전자 메일(정책에 추가)을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="511ac-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="511ac-119">관리자는 준수 센터에 로그인하여 활동을 보고 정책 세부 정보를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="511ac-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="511ac-120">관리자는 데이터 손실 방지 정책 페이지의 준수 센터에서 [>](https://compliance.microsoft.com/compliancesettings) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="511ac-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="511ac-121">![기본 Teams DLP 정책](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="511ac-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="511ac-122">기본 정책 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="511ac-122">Edit or delete the default policy</span></span>

<span data-ttu-id="511ac-123">더 [나은 성능을 위해](create-test-tune-dlp-policy.md#tune-a-dlp-policy)기본 정책을 편집하거나 삭제하려면 **DLP** 준수 관리 권한이 있는 계정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="511ac-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="511ac-124">자세한 내용은 사용 권한을 [참조하세요.](create-test-tune-dlp-policy.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="511ac-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>


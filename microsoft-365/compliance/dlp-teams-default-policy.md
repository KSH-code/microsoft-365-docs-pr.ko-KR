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
description: 2013의 기본 데이터 손실 방지 정책에 대해 Microsoft Teams
ms.openlocfilehash: c6b7413fdd4017fe1211e804c00a2e9c0684468d
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149121"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="e68dc-103">Microsoft Teams의 기본 데이터 손실 방지 정책에 대한 자세한 정보(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e68dc-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="e68dc-104">[개인 채널 메시지를](dlp-learn-about-dlp.md) 포함하여 Microsoft Teams 및 채널 메시지를 포함하기 위해 데이터 손실 방지 기능이 확장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68dc-104">[Data loss prevention](dlp-learn-about-dlp.md) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="e68dc-105">이 릴리스의 일부로 규정 준수 센터에 처음 Microsoft Teams 대한 기본 DLP 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68dc-105">As a part of this release, we created a default DLP policy for Microsoft Teams for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="e68dc-106">적용 대상</span><span class="sxs-lookup"><span data-stu-id="e68dc-106">Applies to</span></span>

<span data-ttu-id="e68dc-107">하나 이상의 라이선스가 부여된 테넌트 및 활성 사용자 Teams</span><span class="sxs-lookup"><span data-stu-id="e68dc-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="e68dc-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="e68dc-108">ME5,</span></span> 
- <span data-ttu-id="e68dc-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="e68dc-109">MA5,</span></span> 
- <span data-ttu-id="e68dc-110">E5/A5 규정 준수,</span><span class="sxs-lookup"><span data-stu-id="e68dc-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="e68dc-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="e68dc-111">IP+G,</span></span> 
- <span data-ttu-id="e68dc-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="e68dc-112">OE5,</span></span> 
- <span data-ttu-id="e68dc-113">O365 고급 규정 준수</span><span class="sxs-lookup"><span data-stu-id="e68dc-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="e68dc-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="e68dc-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="e68dc-115">기본 정책은 어떤 작업을 하나요?</span><span class="sxs-lookup"><span data-stu-id="e68dc-115">What does the default policy do?</span></span>

<span data-ttu-id="e68dc-116">기본 DLP 정책은 Teams 내부 및 외부적으로 공유되는 모든 신용 카드 번호를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="e68dc-116">The default DLP policy for Teams tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="e68dc-117">이 정책은 테넌트의 모든 사용자에 대해 기본적으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68dc-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="e68dc-118">최종 사용자를 위한 정책 팁은 생성하지 않지만 경고 이벤트를 생성하며, 관리자에게 낮은 심각도 전자 메일(정책에 추가)을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="e68dc-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="e68dc-119">관리자는 준수 센터에 로그인하여 활동을 보고 정책 세부 정보를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68dc-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="e68dc-120">관리자는 데이터 손실 방지 정책 페이지의 준수 센터에서 [>](https://compliance.microsoft.com/compliancesettings) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68dc-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="e68dc-121">![기본 Teams DLP 정책](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="e68dc-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="e68dc-122">기본 정책 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="e68dc-122">Edit or delete the default policy</span></span>

<span data-ttu-id="e68dc-123">더 [나은 성능을 위해](create-test-tune-dlp-policy.md#tune-a-dlp-policy)기본 정책을 편집하거나 삭제하려면 **DLP** 준수 관리 권한이 있는 계정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e68dc-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="e68dc-124">자세한 내용은 사용 권한을 [참조하세요.](create-test-tune-dlp-policy.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="e68dc-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>


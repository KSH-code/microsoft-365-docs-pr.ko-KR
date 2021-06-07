---
title: 보안 및 Office 365 센터에서 Microsoft 365 규정 준수 센터로 리디렉션
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: 보안 및 준수 센터 사용자를 Office 365 규정 준수 센터로 Microsoft 365 대해 자세히 알아보습니다.
ms.collection: M365-security-compliance
ms.openlocfilehash: fb667e8f19b26cbe229b3aceffe194a86133c261
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772482"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="868ed-103">보안 및 Office 365 센터에서 Microsoft 365 규정 준수 센터로 리디렉션</span><span class="sxs-lookup"><span data-stu-id="868ed-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="868ed-104">이 문서에서는 Office 365 보안 및 준수 센터(protection.office.com)에서 Microsoft 365 준수 센터(compliance.microsoft.com)로의 준수 솔루션에 액세스하는 사용자에 대해 자동 리디렉션이 작동하는 방식에 대해 compliance.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="868ed-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="868ed-105">예상할 일</span><span class="sxs-lookup"><span data-stu-id="868ed-105">What to expect</span></span>

<span data-ttu-id="868ed-106">자동 리디렉션은 Office 365 및 규정 준수(보안 및 준수)에서 다음 준수 관련 솔루션에 액세스하는 모든 사용자에 대해 기본적으로 protection.office.com.</span><span class="sxs-lookup"><span data-stu-id="868ed-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="868ed-107">DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="868ed-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="868ed-108">분류</span><span class="sxs-lookup"><span data-stu-id="868ed-108">Classification</span></span>
- <span data-ttu-id="868ed-109">정보 거버넌스</span><span class="sxs-lookup"><span data-stu-id="868ed-109">Information governance</span></span>
- <span data-ttu-id="868ed-110">레코드 관리</span><span class="sxs-lookup"><span data-stu-id="868ed-110">Records management</span></span>
- <span data-ttu-id="868ed-111">커뮤니케이션 규정 준수(이전의 '감독')</span><span class="sxs-lookup"><span data-stu-id="868ed-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="868ed-112">사용자는 Microsoft 365 규정 준수 센터(compliance.microsoft.com)에서 동일한 준수 솔루션으로 compliance.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="868ed-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

>[!NOTE]
><span data-ttu-id="868ed-113">Office 365 보안 및 준수 센터에 포함된 다른 규정 준수 솔루션의 경우 사용자는 Microsoft 365 및 준수 센터에서 이러한 솔루션을 Office 365 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="868ed-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="868ed-114">이러한 규정 준수 솔루션에 대한 자동 리디렉션은 곧 제공될 예정입니다.\*</span><span class="sxs-lookup"><span data-stu-id="868ed-114">The automatic redirection for these compliance solutions will be available soon.\*</span></span>

<span data-ttu-id="868ed-115">이 기능과 관련 컨트롤은 Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="868ed-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="868ed-116">보안 기능에 대한 리디렉션을 사용하도록 설정하려면 자세한 내용은 [Microsoft Defender에서](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) Office 365 보안 센터로 Microsoft 365 리디렉션을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="868ed-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="868ed-117">이전 포털을 사용하여 다시 돌아갈 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="868ed-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="868ed-118">문제가 사용자에게 작동하지 않는 경우 또는 Microsoft 365 준수 센터 포털을 통해 완료할 수 없는 경우 모든 사용자에 대해 자동 리디렉션을 일시적으로 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="868ed-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

>[!IMPORTANT]
><span data-ttu-id="868ed-119">Microsoft 365 규정 준수 센터는 현재 Office 365 보안 및 준수 센터에서 관리되는 규정 준수 솔루션에 대한 대체 관리 포털입니다.</span><span class="sxs-lookup"><span data-stu-id="868ed-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="868ed-120">모든 Microsoft 365 규정 준수 솔루션은 규정 준수 센터에서만 Microsoft 365 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="868ed-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="868ed-121">규정 준수 센터로의 리디렉션을 Microsoft 365 단기 솔루션이 여야 합니다.\*</span><span class="sxs-lookup"><span data-stu-id="868ed-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.\*</span></span>

<span data-ttu-id="868ed-122">모든 사용자에 대해 Office 365 보안 및 준수 센터(protection.microsoft.com)로 다시 전환하기 위해 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="868ed-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="868ed-123">전역 관리자로 [](https://compliance.microsoft.com) Microsoft 365 Azure Active Directory에서 규정 준수 관리자 권한이 있는 계정을 사용하여 규정 준수 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="868ed-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="868ed-124">준수 **설정**  >  **리디렉션으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="868ed-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="868ed-125">자동 리디렉션 설정을 끄기 로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="868ed-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="868ed-126">메시지가 **표시될** 때 사용 안 을 선택하고 피드백을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="868ed-126">Select **Disable** and share feedback when prompted.</span></span>

<span data-ttu-id="868ed-127">사용하지 않도록 설정하면 사용자는 더 이상 compliance.microsoft.com 라우팅되지 Office 365 보안 및 규정 준수 센터(protection.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="868ed-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="868ed-128">전역 또는 규정 준수 관리자가 이 설정을 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="868ed-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="868ed-129">관련 정보</span><span class="sxs-lookup"><span data-stu-id="868ed-129">Related information</span></span>

- [<span data-ttu-id="868ed-130">Microsoft 365 준수 센터 개요</span><span class="sxs-lookup"><span data-stu-id="868ed-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)

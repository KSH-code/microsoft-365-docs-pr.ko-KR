---
title: Microsoft 365 Lighthouse 사용자 페이지 개요
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 사용자 페이지를 사용하여 MSP(관리 Microsoft 365 Lighthouse 공급자)의 경우 사용자 페이지에 대해 자세히 알아보십시오.
ms.openlocfilehash: 795e387850bd2945c4019cbb467de87fecc15f86
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395314"
---
# <a name="microsoft-365-lighthouse-users-page-overview"></a><span data-ttu-id="1b559-103">Microsoft 365 Lighthouse 사용자 페이지 개요</span><span class="sxs-lookup"><span data-stu-id="1b559-103">Microsoft 365 Lighthouse Users page overview</span></span> 

> [!NOTE]
> <span data-ttu-id="1b559-104">이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="1b559-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="1b559-105">조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="1b559-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="1b559-106">Microsoft 365 Lighthouse 창에서 사용자를 선택하여 사용자 페이지를 열어  테넌트 계정에서 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b559-106">Microsoft 365 Lighthouse lets you manage users across tenant accounts by selecting **Users** in the left navigation pane to open the Users page.</span></span> <span data-ttu-id="1b559-107">이 페이지에서 사용자를 검색하고 사용자 계정의 보안 상태를 평가하고 이에 대한 행동을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b559-107">From this page, you can search for users and assess and act on the security state of your user accounts.</span></span> <span data-ttu-id="1b559-108">또한 위험한 사용자에 대한 인사이트와 다단계 인증 및 셀프 서비스 암호 재설정 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b559-108">You can also view insights into risky users and the status of multifactor authentication and self-service password reset.</span></span>  
  
## <a name="search-users-tab"></a><span data-ttu-id="1b559-109">사용자 검색 탭</span><span class="sxs-lookup"><span data-stu-id="1b559-109">Search users tab</span></span>  
  
<span data-ttu-id="1b559-110">사용자 검색 탭에서 테넌트 전체에서 빠르게 특정 사용자를 검색하고 계정 암호 다시 설정과 같은 기본 사용자 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b559-110">From the Search users tab, you can quickly search across tenants for specific users and perform basic user management actions such as resetting an account password.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="사용자 검색 탭의 스크린샷.":::

## <a name="risky-users-tab"></a><span data-ttu-id="1b559-112">위험한 사용자 탭</span><span class="sxs-lookup"><span data-stu-id="1b559-112">Risky users tab</span></span>

<span data-ttu-id="1b559-113">위험 사용자 탭에는 위험한 동작에 대해 플래그가 지정된 테넌트의 사용자 계정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b559-113">The Risky Users tab shows user accounts across your tenants that have been flagged for risky behavior.</span></span> <span data-ttu-id="1b559-114">검색된 위험에 대한 자세한 정보를 보거나 사용자의 암호를 다시 설정하거나 로그인을 차단하여 위험을 완화하려면 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b559-114">Select any of the users to view more information on a detected risk or to mitigate a risk by resetting a user's password or blocking sign-in.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-risky-users-tab.png" alt-text="위험한 사용자 탭의 스크린샷.":::

## <a name="multifactor-authentication-tab"></a><span data-ttu-id="1b559-116">다단계 인증 탭</span><span class="sxs-lookup"><span data-stu-id="1b559-116">Multifactor Authentication tab</span></span>

<span data-ttu-id="1b559-117">다단계 인증 탭에서는 테넌트 전체의 MFA(다단계 인증) 사용 상태에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b559-117">The Multifactor Authentication tab provides detailed information on the status of multifactor authentication (MFA) enablement across your tenants.</span></span> <span data-ttu-id="1b559-118">MFA를 요구하는 조건부 액세스 정책과 아직 MFA에 등록되지 않은 사용자를 포함하여 해당 테넌트에 대한 자세한 내용을 확인하려면 목록에서 테넌트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b559-118">Select any tenant in the list to see more details for that tenant, including which Conditional Access policies requiring MFA are already configured and which users have not yet registered for MFA.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-mfa-tab.png" alt-text="다단계 인증 탭의 스크린샷.":::

## <a name="password-reset-tab"></a><span data-ttu-id="1b559-120">암호 재설정 탭</span><span class="sxs-lookup"><span data-stu-id="1b559-120">Password reset tab</span></span>

<span data-ttu-id="1b559-121">암호 재설정 탭에는 테넌트 전체의 셀프 서비스 암호 재설정 사용 상태에 대한 자세한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b559-121">The Password reset tab shows detailed information on the status of self-service password reset enablement across your tenants.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-password-reset-tab.png" alt-text="암호 재설정 탭의 스크린샷.":::

## <a name="related-content"></a><span data-ttu-id="1b559-123">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="1b559-123">Related content</span></span>

<span data-ttu-id="1b559-124">[Microsoft 365 Lighthouse 준수 페이지](m365-lighthouse-device-compliance-page-overview.md) 개요(문서)</span><span class="sxs-lookup"><span data-stu-id="1b559-124">[Microsoft 365 Lighthouse device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="1b559-125">[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="1b559-125">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>

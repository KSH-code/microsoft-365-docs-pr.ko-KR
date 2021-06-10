---
title: 보안 및 Office 365 센터에서 새 보안 및 준수 센터로 계정 Microsoft 365 리디렉션
description: Defender for Office 365 Defender로 Microsoft 365.
keywords: Microsoft 365 Defender, Microsoft 365 Defender 시작, 보안 센터 리디렉션
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842524"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a><span data-ttu-id="65ebf-104">보안 및 Office 365 센터에서 Defender로 Microsoft 365 리디렉션</span><span class="sxs-lookup"><span data-stu-id="65ebf-104">Redirecting accounts from Office 365 Security and Compliance Center to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="65ebf-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="65ebf-105">**Applies to:**</span></span>

- <span data-ttu-id="65ebf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65ebf-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="65ebf-107">Office 365용 Defender</span><span class="sxs-lookup"><span data-stu-id="65ebf-107">Defender for Office 365</span></span>

<span data-ttu-id="65ebf-108">이 문서에서는 이전 Office 365 보안 및 준수 센터(protection.office.com)에서 Microsoft 365 Defender(security.microsoft.com Microsoft 365)로 계정을 라우팅하는 방법을 security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="65ebf-108">This article explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Office 365 Security and Compliance Center (protection.office.com), to Microsoft 365 Defender (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="65ebf-109">예상할 일</span><span class="sxs-lookup"><span data-stu-id="65ebf-109">What to expect</span></span>
<span data-ttu-id="65ebf-110">자동 리디렉션을 사용하도록 설정하고 활성화하면 Office 365 보안 및 준수(protection.office.com)의 보안 관련 기능에 액세스하는 사용자는 자동으로 Microsoft 365 Defender( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="65ebf-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to Microsoft 365 Defender (https://security.microsoft.com).</span></span>  

<span data-ttu-id="65ebf-111">변경된 내용을 자세히 알아보시고 Microsoft [Defender for Office 365 Defender에서 Microsoft 365.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="65ebf-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="65ebf-112">자동 리디렉션을 설정하면 사용자가 Microsoft 365 및 준수 센터에서 보안 기능을 사용할 때 Office 365 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-112">With automatic redirection turned on, users will be routed to Microsoft 365 Defender when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="65ebf-113">여기에는 위협 관리 섹션 및 위협 관리 대시보드 및 보고서의 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="65ebf-114">보안 Office 365 관련이 없는 보안 및 준수 센터의 항목은 Microsoft 365 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to Microsoft 365 Defender.</span></span>

<span data-ttu-id="65ebf-115">규정 준수 관련 항목은 Microsoft 365 규정 준수 센터에서 찾을 수 있으며, 메일 흐름 관련 항목은 Exchange 관리 센터에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="65ebf-116">규정 준수 관련 기능 또는 둘 다를 충족하는 기능 등 다른 모든 기능은 리디렉션의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="65ebf-117">Office 365 경고는 리디렉션 없이 Microsoft 365 및 Office 365 및 준수 센터 둘 다에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-117">Office 365 security alerts appear in both Microsoft 365 Defender and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="65ebf-118">포털 리디렉션 설정</span><span class="sxs-lookup"><span data-stu-id="65ebf-118">Set up portal redirection</span></span>
<span data-ttu-id="65ebf-119">다음을 통해 Microsoft 365 Defender로 라우팅 계정을 security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="65ebf-119">To start routing accounts to Microsoft 365 Defender at security.microsoft.com:</span></span>

1. <span data-ttu-id="65ebf-120">전역 관리자 또는 Azure Active Directory에 보안 관리자 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="65ebf-121">[Defender에](https://security.microsoft.com/) Microsoft 365 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-121">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>
3. <span data-ttu-id="65ebf-122">전자 **메일 설정**  >  **포털 리디렉션으로**  >  **& 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="65ebf-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="65ebf-123">자동 리디렉션 설정을 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="65ebf-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="65ebf-124">**Defender에** 자동 리디렉션을 적용하려면 Microsoft 365 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-124">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

> [!NOTE]
> <span data-ttu-id="65ebf-125">리디렉션을 사용하도록 설정한 후 이 설정이 적용되는 동안 활성 세션의 계정은 세션에서출되지 않습니다. 현재 세션을 종료하고 다시 로그인한 후에만 Microsoft 365 Defender로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="65ebf-126">이전 포털을 사용하여 다시 돌아갈 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="65ebf-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="65ebf-127">문제가 작동하지 않는 경우 또는 Microsoft 365 Defender를 통해 완료할 수 없는 것이 있는 경우 포털 피드백 옵션을 사용하여 해당 정보를 듣고 싶을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-127">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="65ebf-128">리디렉션에 문제가 발생하면 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="65ebf-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="65ebf-129">이전 포털로 되버리기:</span><span class="sxs-lookup"><span data-stu-id="65ebf-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="65ebf-130">[전역 관리자로](https://security.microsoft.com/) Microsoft 365 Azure Active Directory의 보안 관리자 권한 및 계정으로 Defender에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-130">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="65ebf-131">전자 **메일 설정**  >  **포털 리디렉션으로**  >  **& 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="65ebf-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="65ebf-132">자동 리디렉션 설정을 끄기 로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="65ebf-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="65ebf-133">메시지가 **표시될** & 공유하지 않도록 설정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="65ebf-134">이 설정은 어떤 경우든 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="65ebf-135">사용하지 않도록 설정하면 계정이 더 이상 security.microsoft.com 라우팅되지 않습니다. 또한 이전 포털(securitycenter.windows.com 또는 securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="65ebf-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal—securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="65ebf-136">관련 정보</span><span class="sxs-lookup"><span data-stu-id="65ebf-136">Related information</span></span>
- [<span data-ttu-id="65ebf-137">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="65ebf-137">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="65ebf-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65ebf-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="65ebf-139">Microsoft는 보안 운영을 현대화하기 위해 통합 SIEM 및 XDR을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65ebf-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="65ebf-140">XDR 및 SIEM 인포그래픽</span><span class="sxs-lookup"><span data-stu-id="65ebf-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="65ebf-141">The New Defender</span><span class="sxs-lookup"><span data-stu-id="65ebf-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="65ebf-142">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65ebf-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="65ebf-143">Microsoft 보안 포털 및 관리 센터</span><span class="sxs-lookup"><span data-stu-id="65ebf-143">Microsoft security portals and admin centers</span></span>](portals.md)

---
title: Office 365용 Microsoft Defender에서 새 Microsoft 365 보안 센터로 계정 리디렉션
description: Office 365용 Defender에서 Microsoft 365 보안 센터로 리디렉션하는 방법
keywords: Microsoft 365 보안 센터, Microsoft 365 보안 센터 시작, 보안 센터 리디렉션
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 30fa10e23fd6a0c92bd5a56c797d3b7ff5b4bfd6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416825"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="dc54e-104">Office 365용 Microsoft Defender에서 Microsoft 365 보안 센터로 계정 리디렉션</span><span class="sxs-lookup"><span data-stu-id="dc54e-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="dc54e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="dc54e-105">**Applies to:**</span></span>

- <span data-ttu-id="dc54e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc54e-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="dc54e-107">Office 365용 Defender</span><span class="sxs-lookup"><span data-stu-id="dc54e-107">Defender for Office 365</span></span>

<span data-ttu-id="dc54e-108">이 문서에서는 이전 Microsoft 보안 및 준수 센터(protection.office.com 또는 securitycenter.microsoft.com)에서 Microsoft 365 보안 센터(security.microsoft.com)로 자동 리디렉션을 사용하도록 설정하여 계정을 Microsoft 365 보안 센터로 라우팅하는 방법에 대해 security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="dc54e-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

>[!NOTE]
> <span data-ttu-id="dc54e-109">Office 365 E5 및 Office P2용 Microsoft Defender 고객에게만 포털 리디렉션 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-109">Portal redirection capability is available for Office 365 E5 and Microsoft Defender for Office P2 customers only</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="dc54e-110">예상할 일</span><span class="sxs-lookup"><span data-stu-id="dc54e-110">What to expect</span></span>
<span data-ttu-id="dc54e-111">자동 리디렉션을 사용하도록 설정하고 활성화하면 Office 365 보안 및 규정 준수(protection.office.com)의 보안 관련 기능에 액세스하는 사용자가 Microsoft 365 보안 센터() 로 자동으로 라우팅됩니다. https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="dc54e-111">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="dc54e-112">변경된 내용을 자세히 알아보시고, Microsoft 365 보안 센터에서 [Office 365용 Microsoft Defender를 사용할 수 있습니다.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="dc54e-112">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="dc54e-113">자동 리디렉션을 설정하면 사용자가 Office 365 보안 및 준수 센터의 보안 기능을 사용할 때 Microsoft 365 보안 센터로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-113">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="dc54e-114">여기에는 위협 관리 섹션 및 위협 관리 대시보드 및 보고서의 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-114">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="dc54e-115">보안과 관련이 없는 Office 365 보안 및 준수 센터의 항목은 Microsoft 365 보안 센터로 리디렉션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-115">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="dc54e-116">준수 관련 항목은 Microsoft 365 규정 준수 센터에서 찾을 수 있으며, 메일 흐름 관련 항목은 Exchange 관리 센터에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-116">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="dc54e-117">규정 준수 관련 기능 또는 둘 다를 충족하는 기능 등 다른 모든 기능은 리디렉션의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-117">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="dc54e-118">Office 365 보안 경고는 리디렉션 없이 Microsoft 365 보안 센터와 Office 365 보안 및 준수 센터 둘 다에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-118">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="dc54e-119">포털 리디렉션 설정</span><span class="sxs-lookup"><span data-stu-id="dc54e-119">Set up portal redirection</span></span>
<span data-ttu-id="dc54e-120">다음을 통해 Microsoft 365 보안 센터로 계정 라우팅을 security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="dc54e-120">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="dc54e-121">전역 관리자 또는 Azure Active Directory에 보안 관리자 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-121">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="dc54e-122">[](https://security.microsoft.com/) Microsoft 365 보안 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-122">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="dc54e-123">설정 전자  >  **메일 및 & 포털**  >  **리디렉션으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="dc54e-123">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="dc54e-124">자동 리디렉션 설정을 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="dc54e-124">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="dc54e-125">Microsoft  365 보안 센터 포털에 자동 리디렉션을 적용하려면 사용 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-125">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="dc54e-126">리디렉션을 사용하도록 설정한 후 이 설정이 적용되는 동안 활성 세션의 계정은 세션에서출되지 않습니다. 현재 세션을 종료하고 다시 로그인한 후에만 Microsoft 365 보안 센터로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-126">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="dc54e-127">이전 포털을 사용하여 다시 돌아갈 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="dc54e-127">Can I go back to using the former portal?</span></span>
<span data-ttu-id="dc54e-128">문제가 작동하지 않는 경우 또는 Microsoft 365 보안 센터 포털을 통해 완료할 수 없는 경우 포털 피드백 옵션을 사용하여 해당 정보를 듣고 싶을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-128">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="dc54e-129">리디렉션에 문제가 발생하면 비공개 미리 보기를 통해 직접 PM 친구에게 연락하거나 피드백 제출 보내기 양식을 통해 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="dc54e-129">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="dc54e-130">이전 포털로 되버리기:</span><span class="sxs-lookup"><span data-stu-id="dc54e-130">To revert to the former portal:</span></span>

1. <span data-ttu-id="dc54e-131">[전역 관리자로](https://security.microsoft.com/) Microsoft 365 보안 센터에 로그인하거나 Azure Active Directory에서 보안 관리자 권한을 사용하여 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-131">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="dc54e-132">설정 **끝점**  >  **일반 포털**  >    >  **리디렉션으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="dc54e-132">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="dc54e-133">자동 리디렉션 설정을 끄기 로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="dc54e-133">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="dc54e-134">메시지가 **표시될** & 공유하지 않도록 설정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-134">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="dc54e-135">이 설정은 어떤 경우든 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-135">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="dc54e-136">사용하지 않도록 설정하면 계정이 더 이상 security.microsoft.com 라우팅되지 않습니다. securitycenter.windows.com 또는 이전 포털에 다시 securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="dc54e-136">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="dc54e-137">관련 정보</span><span class="sxs-lookup"><span data-stu-id="dc54e-137">Related information</span></span>
- [<span data-ttu-id="dc54e-138">Microsoft 365 보안 센터 개요</span><span class="sxs-lookup"><span data-stu-id="dc54e-138">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="dc54e-139">Microsoft 365 보안 센터의 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dc54e-139">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="dc54e-140">Microsoft는 보안 운영을 현대화하기 위해 통합 SIEM 및 XDR을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc54e-140">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="dc54e-141">XDR 및 SIEM 인포그래픽</span><span class="sxs-lookup"><span data-stu-id="dc54e-141">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="dc54e-142">The New Defender</span><span class="sxs-lookup"><span data-stu-id="dc54e-142">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="dc54e-143">About Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc54e-143">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="dc54e-144">Microsoft 보안 포털 및 관리 센터</span><span class="sxs-lookup"><span data-stu-id="dc54e-144">Microsoft security portals and admin centers</span></span>](portals.md)
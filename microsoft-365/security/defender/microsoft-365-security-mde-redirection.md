---
title: 끝점용 Microsoft Defender에서 Microsoft 365 보안 센터로 계정 리디렉션
description: 끝점용 Defender에서 Microsoft 365 보안 센터로 계정 및 세션을 리디렉션하는 방법
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: db458015d8434843ec64f3c2c00d640d4c4d8ff2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760179"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a><span data-ttu-id="c8175-104">끝점용 Microsoft Defender에서 Microsoft 365 보안 센터로 계정 리디렉션</span><span class="sxs-lookup"><span data-stu-id="c8175-104">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c8175-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c8175-105">**Applies to:**</span></span>
- <span data-ttu-id="c8175-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8175-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="c8175-107">엔드포인트용 Defender</span><span class="sxs-lookup"><span data-stu-id="c8175-107">Defender for Endpoint</span></span>

<span data-ttu-id="c8175-108">SIEM 및 XDR(Extended detection and response)을 통해 위협 방지에 대한 Microsoft의 도메인 간 접근 방식에 맞춰 Microsoft Defender Advanced Threat Protection을 끝점용 Microsoft Defender로 변경하고 이를 단일 통합 포털인 Microsoft 365 보안 센터로 통합했습니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - the Microsoft 365 security center.</span></span>

<span data-ttu-id="c8175-109">이 가이드에서는 이전의 Microsoft Defender for Endpoint 포털(securitycenter.windows.com 또는 securitycenter.microsoft.com)에서 Microsoft 365 보안 센터 포털(security.microsoft.com)으로 자동 리디렉션을 사용하도록 설정하여 계정을 Microsoft 365 보안 센터로 라우팅하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-109">This guide explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to the Microsoft 365 security center portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="c8175-110">Microsoft 365 보안 센터의 끝점용 Microsoft [Defender는 Microsoft Defender](./mssp-access.md)보안 센터에서 액세스 권한을 부여하는 방법과 동일한 방식으로 관리되는 보안 서비스 공급자(MSSP)에 대한 액세스 권한을 부여할 수 있도록 지원합니다. [](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)</span><span class="sxs-lookup"><span data-stu-id="c8175-110">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="c8175-111">예상할 일</span><span class="sxs-lookup"><span data-stu-id="c8175-111">What to expect</span></span>
<span data-ttu-id="c8175-112">자동 리디렉션을 사용하도록 설정하면 securitycenter.windows.com 또는 securitycenter.microsoft.com 에서 이전 Microsoft Defender for Endpoint 포털에 액세스하는 계정은 microsoft 365 보안 센터 포털의 security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c8175-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to the Microsoft 365 security center portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="c8175-113">변경된 내용을 자세히 알아보시고, Microsoft 365 보안 센터의 [끝점용 Microsoft Defender를 자세히 알아보실 수 있습니다.](microsoft-365-security-center-mde.md)</span><span class="sxs-lookup"><span data-stu-id="c8175-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in the Microsoft 365 security center](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="c8175-114">여기에는 전자 메일 알림의 링크, SIEM API 호출에서 반환된 링크 등 이전 securitycenter.windows.com 포털을 향한 링크를 포함하여 브라우저를 통해 이전 포털에 직접 액세스하기 위한 리디렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="c8175-115">전자 메일 알림 또는 SIEM API의 외부 링크에는 현재 두 포털에 대한 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="c8175-116">리디렉션을 사용하도록 설정하면 이전 링크가 결국 제거될 때까지 두 링크가 Microsoft 365 보안 센터를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-116">Once redirection is enabled, both links will point to the Microsoft 365 security center until the old link is eventually removed.</span></span> <span data-ttu-id="c8175-117">Microsoft 365 보안 센터를 중심으로 하는 새 링크를 채택하는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-117">We encourage you to adopt the new link pointing to the Microsoft 365 security center.</span></span>

<span data-ttu-id="c8175-118">링크 및 라우팅에 대한 자세한 내용은 아래 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8175-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="c8175-119">SIEM API 라우팅</span><span class="sxs-lookup"><span data-stu-id="c8175-119">SIEM API routing</span></span>

|<span data-ttu-id="c8175-120">**속성**</span><span class="sxs-lookup"><span data-stu-id="c8175-120">**Property**</span></span>  |<span data-ttu-id="c8175-121">**리디렉션이 해제된 경우 대상**</span><span class="sxs-lookup"><span data-stu-id="c8175-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="c8175-122">**리디렉션이 ON인 경우 대상**</span><span class="sxs-lookup"><span data-stu-id="c8175-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="c8175-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="c8175-123">LinkToWDATP</span></span> | <span data-ttu-id="c8175-124">알림 페이지의 securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="c8175-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="c8175-125">알림 페이지의 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="c8175-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="c8175-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="c8175-127">인시던트 securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="c8175-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="c8175-128">인시던트 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="c8175-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="c8175-129">LinkToMTP</span></span> | <span data-ttu-id="c8175-130">알림 페이지의 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="c8175-131">알림 페이지의 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="c8175-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="c8175-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="c8175-133">인시던트 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="c8175-134">인시던트 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="c8175-135">전자 메일 알림</span><span class="sxs-lookup"><span data-stu-id="c8175-135">Email alert notifications</span></span>

|<span data-ttu-id="c8175-136">**속성**</span><span class="sxs-lookup"><span data-stu-id="c8175-136">**Property**</span></span>  |<span data-ttu-id="c8175-137">**리디렉션이 해제된 경우 대상**</span><span class="sxs-lookup"><span data-stu-id="c8175-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="c8175-138">**리디렉션이 ON인 경우 대상**</span><span class="sxs-lookup"><span data-stu-id="c8175-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="c8175-139">경고 페이지</span><span class="sxs-lookup"><span data-stu-id="c8175-139">Alert page</span></span>  | <span data-ttu-id="c8175-140">알림 페이지의 securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="c8175-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="c8175-141">알림 페이지의 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="c8175-142">인시던트 페이지</span><span class="sxs-lookup"><span data-stu-id="c8175-142">Incident page</span></span>  |<span data-ttu-id="c8175-143">인시던트 securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="c8175-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="c8175-144">인시던트 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="c8175-145">보안 센터 포털의 경고 페이지</span><span class="sxs-lookup"><span data-stu-id="c8175-145">Alert page in security center portal</span></span> | <span data-ttu-id="c8175-146">알림 페이지의 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="c8175-147">알림 페이지의 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="c8175-148">보안 센터 포털의 인시던트 페이지</span><span class="sxs-lookup"><span data-stu-id="c8175-148">Incident page in security center portal</span></span> | <span data-ttu-id="c8175-149">인시던트 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="c8175-150">인시던트 security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8175-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="c8175-151">이 방식은 언제 적용하나요?</span><span class="sxs-lookup"><span data-stu-id="c8175-151">When does this take effect?</span></span> 
<span data-ttu-id="c8175-152">사용하도록 설정하면 일부 계정에 대해 이 업데이트가 거의 즉시 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="c8175-153">그러나 리디렉션이 조직의 모든 계정에 전파하는 데 더 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="c8175-154">이 설정이 적용된 동안 활성 세션의 계정은 세션에서출되지 않습니다. 현재 세션을 종료하고 다시 로그인한 후에만 Microsoft 365 보안 센터로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="c8175-155">포털 리디렉션 설정</span><span class="sxs-lookup"><span data-stu-id="c8175-155">Set up portal redirection</span></span>
<span data-ttu-id="c8175-156">Microsoft 365 보안 센터로 계정 라우팅을 시작:</span><span class="sxs-lookup"><span data-stu-id="c8175-156">To start routing accounts to the Microsoft 365 security center:</span></span>
1. <span data-ttu-id="c8175-157">전역 관리자 또는 Azure Active Directory에 보안 관리자 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c8175-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="c8175-158">[](https://security.microsoft.com/) Microsoft 365 보안 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-158">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>

3. <span data-ttu-id="c8175-159">설정 **끝점** 일반 포털  >    >    >  **리디렉션으로 이동하거나** [여기를 클릭합니다.](https://security.microsoft.com/preferences2/portal_redirection)</span><span class="sxs-lookup"><span data-stu-id="c8175-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="c8175-160">자동 리디렉션 설정을 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="c8175-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="c8175-161">Microsoft  365 보안 센터 포털에 자동 리디렉션을 적용하려면 사용 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-161">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c8175-162">이 설정을 사용하도록 설정하면 활성 사용자 세션이 종료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="c8175-163">이 설정이 적용되는 동안 활성 세션에 있는 계정은 현재 세션을 종료하고 다시 로그인한 후에만 Microsoft 365 보안 센터로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-163">Accounts who are in an active session while this setting is applied will only be directed to the Microsoft 365 security center after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="c8175-164">이 설정을 사용하도록 설정하거나 사용하지 않도록 설정하려면 전역 관리자 또는 Azure Active Directory의 보안 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="c8175-165">이전 포털을 사용하여 다시 돌아갈 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c8175-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="c8175-166">문제가 작동하지 않는 경우 또는 Microsoft 365 보안 센터 포털을 통해 완료할 수 없는 경우 해당 정보를 듣고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-166">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it.</span></span> <span data-ttu-id="c8175-167">리디렉션과 관련한 문제가 발생하는 경우 피드백 제출 보내기 양식을 사용하여 알려주는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="c8175-168">이전의 Microsoft Defender for Endpoint 포털로 되 되 관리:</span><span class="sxs-lookup"><span data-stu-id="c8175-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="c8175-169">[전역 관리자로](https://security.microsoft.com/) Microsoft 365 보안 센터에 로그인하거나 Azure Active Directory에서 보안 관리자 권한을 사용하여 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-169">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="c8175-170">설정 **끝점** 일반 포털  >    >    >  **리디렉션으로 이동하거나** 여기에서 [페이지를 열 수 있습니다.](https://security.microsoft.com/preferences2/portal_redirection)</span><span class="sxs-lookup"><span data-stu-id="c8175-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="c8175-171">자동 리디렉션 설정을 끄기 로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="c8175-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="c8175-172">메시지가 **표시될** & 공유하지 않도록 설정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="c8175-173">이 설정은 어떤 경우든 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="c8175-174">사용하지 않도록 설정하면 계정이 더 이상 security.microsoft.com 라우팅되지 않습니다. securitycenter.windows.com 또는 이전 포털에 다시 securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c8175-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="c8175-175">관련 정보</span><span class="sxs-lookup"><span data-stu-id="c8175-175">Related information</span></span>
- [<span data-ttu-id="c8175-176">Microsoft 365 보안 센터 개요</span><span class="sxs-lookup"><span data-stu-id="c8175-176">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="c8175-177">Microsoft 365 보안 센터의 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c8175-177">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="c8175-178">Microsoft는 보안 운영을 현대화하기 위해 통합 SIEM 및 XDR을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c8175-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="c8175-179">XDR 및 SIEM 인포그래픽</span><span class="sxs-lookup"><span data-stu-id="c8175-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="c8175-180">The New Defender</span><span class="sxs-lookup"><span data-stu-id="c8175-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="c8175-181">About Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8175-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="c8175-182">Microsoft 보안 포털 및 관리 센터</span><span class="sxs-lookup"><span data-stu-id="c8175-182">Microsoft security portals and admin centers</span></span>](portals.md)
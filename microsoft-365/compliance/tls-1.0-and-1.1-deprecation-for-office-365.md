---
title: TLS 1.0 및 1.1을 Microsoft 365
description: TLS 1.0 및 1.1 사용 중지 및 Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332681"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="8449b-103">TLS 1.0 및 1.1을 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8449b-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8449b-104">COVID-19로 인해 상업 고객의 경우 TLS 1.0 및 1.1의 비활성화를 일시적으로 중지했습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="8449b-105">공급망이 조정되고 특정 국가가 백업을 시작하면 2020년 10월 15일 TLS 1.2 적용 롤아웃이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="8449b-106">몇 주와 몇 개월에 한해 출시가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="8449b-107">2018년 10월 31일 현재 TLS(전송 계층 보안) 1.0 및 1.1 프로토콜은 Microsoft 365 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="8449b-108">최종 사용자에게는 최소한의 영향만 미미합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="8449b-109">이 변경은 2017년 12월에 첫 번째 공개 발표와 함께 2년 넘게 공개되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="8449b-110">이 문서에서는 Office 365 서비스 관련 Office 365 로컬 클라이언트에 대해 다루고 Office 365 Web Apps 및 Office 및 Office Online Server/Office TLS 문제에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="8449b-111">이 SharePoint OneDrive TLS 1.2를 지원하도록 .NET을 업데이트하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="8449b-112">자세한 내용은 [클라이언트에서 TLS 1.2를 사용하도록 설정하는 방법을 참조하세요.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="8449b-112">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="8449b-113">Office 365 및 TLS 개요</span><span class="sxs-lookup"><span data-stu-id="8449b-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="8449b-114">Office 클라이언트는 WINHTTP(Windows 웹 서비스)를 사용하여 TLS 프로토콜을 통해 트래픽을 보내고 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="8449b-115">로컬 Office 웹 서비스에서 TLS 1.2를 사용할 수 있는 경우 클라이언트에서 TLS 1.2를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="8449b-116">TLS Office SSL 프로토콜은 운영 체제의 일부가 아닌 운영 체제의 일부이기 때문에 모든 Office 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="8449b-117">On Windows 8 and later versions</span><span class="sxs-lookup"><span data-stu-id="8449b-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="8449b-118">TLS 1.2 트래픽을 거부하도록 구성된 네트워크 장치가 없는 경우 기본적으로 TLS 1.2 및 1.1 프로토콜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="8449b-119">On Windows 7</span><span class="sxs-lookup"><span data-stu-id="8449b-119">On Windows 7</span></span>

<span data-ttu-id="8449b-120">KB 3140245 업데이트가 없는 경우 TLS [1.1 및 1.2 프로토콜을 사용할 수](https://support.microsoft.com/help/3140245) 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="8449b-121">이 업데이트는 이 문제를 해결하고 다음 레지스트리 하위 키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="8449b-122">Windows 이 업데이트가 없는 사용자 7명은 2018년 10월 31일 현재 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="8449b-123">[KB 3140245에는](https://support.microsoft.com/help/3140245) WINHTTP 설정을 변경하여 TLS 프로토콜을 사용하도록 설정하는 방법에 대한 세부 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="8449b-124">추가 정보</span><span class="sxs-lookup"><span data-stu-id="8449b-124">More information</span></span>

<span data-ttu-id="8449b-125">KB 문서에서 설명하는 **DefaultSecureProtocols** 레지스트리 키의 값에 따라 사용할 수 있는 네트워크 프로토콜이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="8449b-126">DefaultSecureProtocols 값</span><span class="sxs-lookup"><span data-stu-id="8449b-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="8449b-127">프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="8449b-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="8449b-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="8449b-128">0x00000008</span></span>|<span data-ttu-id="8449b-129">기본적으로 SSL 2.0 사용</span><span class="sxs-lookup"><span data-stu-id="8449b-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="8449b-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="8449b-130">0x00000020</span></span>|<span data-ttu-id="8449b-131">기본적으로 SSL 3.0 사용</span><span class="sxs-lookup"><span data-stu-id="8449b-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="8449b-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="8449b-132">0x00000080</span></span>|<span data-ttu-id="8449b-133">기본적으로 TLS 1.0 사용</span><span class="sxs-lookup"><span data-stu-id="8449b-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="8449b-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="8449b-134">0x00000200</span></span>|<span data-ttu-id="8449b-135">기본적으로 TLS 1.1 사용</span><span class="sxs-lookup"><span data-stu-id="8449b-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="8449b-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="8449b-136">0x00000800</span></span>|<span data-ttu-id="8449b-137">기본적으로 TLS 1.2 사용</span><span class="sxs-lookup"><span data-stu-id="8449b-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="8449b-138">Office 및 TLS 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="8449b-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="8449b-139">에서 [KB 4057306 TLS 1.2의](https://support.microsoft.com/help/4057306)필수 사용 준비를 Office 365.</span><span class="sxs-lookup"><span data-stu-id="8449b-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="8449b-140">이 문서는 IT 관리자를 위한 일반 문서로, TLS 1.2 변경에 대한 공식 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="8449b-141">다음 표에는 2018년 10월 31일 이후의 Office 365 클라이언트의 적절한 레지스트리 키 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="8449b-142">2018년 10월 31일 이후 Office 365 서비스용 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="8449b-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="8449b-143">16진수 값</span><span class="sxs-lookup"><span data-stu-id="8449b-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="8449b-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="8449b-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="8449b-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="8449b-145">0x00000A80</span></span>|
|<span data-ttu-id="8449b-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="8449b-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="8449b-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="8449b-147">0x00000A00</span></span>|
|<span data-ttu-id="8449b-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="8449b-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="8449b-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="8449b-149">0x00000880</span></span>|
|<span data-ttu-id="8449b-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="8449b-150">TLS 1.2</span></span>|<span data-ttu-id="8449b-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="8449b-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="8449b-152">**DefaultSecureProtocols** 키를 사용하여 설정할 수 있는 SSL 2.0 및 3.0 프로토콜을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="8449b-153">SSL 2.0 및 3.0은 기한이 지난 비보안 프로토콜로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="8449b-154">최상의 방법은 SSL 2.0 및 SSL 3.0 사용을 종료하는 것입니다. 그러나 이를 위한 결정은 궁극적으로 제품 요구 사항을 가장 잘 충족하는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="8449b-155">SSL 3.0 취약성에 대한 자세한 내용은 [KB 3009008을 참조하세요.](https://support.microsoft.com/help/3009008)</span><span class="sxs-lookup"><span data-stu-id="8449b-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="8449b-156">프로그래머 모드에서 기본 Windows 계산기를 사용하여 동일한 참조 레지스트리 키 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="8449b-157">자세한 내용은 [KB 3140245 업데이트를 참조하여 에서 WinHTTP의 기본 보안 프로토콜로 TLS 1.1 및 TLS 1.2를 사용하도록](https://support.microsoft.com/help/3140245)Windows.</span><span class="sxs-lookup"><span data-stu-id="8449b-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="8449b-158">Windows 7[업데이트(KB 3140245)가](https://support.microsoft.com/help/3140245)설치되어 있지 않은지와 관계없이 DefaultSecureProtocols 레지스트리 하위 키는 존재하지 않습니다. 수동으로 또는 GPO(그룹 정책 개체)를 통해 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="8449b-159">즉, 사용하도록 설정되거나 제한된 보안 프로토콜을 사용자 지정할 필요 없이 이 키가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="8449b-160">7 SP1(Windows[3140245)](https://support.microsoft.com/help/3140245)업데이트만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="8449b-161">TLS 1.2를 .NET Framework 업데이트 및 구성</span><span class="sxs-lookup"><span data-stu-id="8449b-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="8449b-162">TLS 1.2를 사용하려면 TLS Microsoft 365 또는 TLS 1.1을 통해 Microsoft 365 응용 프로그램을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="8449b-163">.NET 4.5는 기본적으로 TLS 1.1로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="8449b-164">.NET 구성을 업데이트하려면 [클라이언트에서 TLS(전송 계층 보안) 1.2를](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)사용하도록 설정하는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="8449b-165">추가 정보</span><span class="sxs-lookup"><span data-stu-id="8449b-165">More information</span></span>

<span data-ttu-id="8449b-166">자세한 내용은 에서 [TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비를 Office 365.</span><span class="sxs-lookup"><span data-stu-id="8449b-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="references"></a><span data-ttu-id="8449b-167">참조</span><span class="sxs-lookup"><span data-stu-id="8449b-167">References</span></span>

<span data-ttu-id="8449b-168">다음 리소스는 클라이언트가 TLS 1.2 이상 버전을 사용하고 있는지와 TLS 1.0 및 1.1을 사용하지 않도록 설정하는 데 도움이 되는 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-168">The following resources provide guidance to help make sure that your clients are using TLS 1.2 or a later version and to disable TLS 1.0 and 1.1:</span></span>

- <span data-ttu-id="8449b-169">Office 365에 연결하는 Windows 7 클라이언트의 경우 Windows의 WinHTTP에서 TLS 1.2가 기본 보안 프로토콜인지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8449b-169">For Windows 7 clients that connect to Office 365, make sure that TLS 1.2 is the default secure protocol in WinHTTP in Windows.</span></span> <span data-ttu-id="8449b-170">자세한 내용은 KB 3140245 - 업데이트 - 에서 WinHTTP의 기본 보안 프로토콜로 [TLS 1.1 및 TLS 1.2를](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)사용하도록 Windows.</span><span class="sxs-lookup"><span data-stu-id="8449b-170">For more information, see [KB 3140245 - Update to enable TLS 1.1 and TLS 1.2 as default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).</span></span>
- <span data-ttu-id="8449b-171">TLS 1.0 및 1.1 종속성 제거를 통해 약한 TLS 사용을 해결 방법은 [Microsoft에서 TLS 1.2 지원을 참조하세요.](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)</span><span class="sxs-lookup"><span data-stu-id="8449b-171">To address weak TLS usage by removing TLS 1.0 and 1.1 dependencies, see [TLS 1.2 support at Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).</span></span>
- <span data-ttu-id="8449b-172">[새로운 IIS 기능](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/)을 사용하면 취약한 보안 프로토콜로 서비스에 연결하는 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 및 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334)에서 클라이언트를 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-172">[New IIS functionality](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) makes it easier to find clients on [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) and [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) that connect to the service by using weak security protocols.</span></span>
- <span data-ttu-id="8449b-173">[TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266)문제를 해결하는 방법에 대한 자세한 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-173">Get more information about how to [solve the TLS 1.0 problem](https://www.microsoft.com/download/details.aspx?id=55266).</span></span>
- <span data-ttu-id="8449b-174">보안에 접근하는 방식에 대한 일반적인 정보는 [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365)로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="8449b-174">For general information about our approach to security, go to the [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365).</span></span>
- [<span data-ttu-id="8449b-175">TLS 1.0/1.1 사용 중단 준비 - Office 365 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="8449b-175">Preparing for TLS 1.0/1.1 Deprecation - Office 365 Skype for Business</span></span>](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [<span data-ttu-id="8449b-176">Exchange Server TLS 지침, 1부: TLS 1.2 준비</span><span class="sxs-lookup"><span data-stu-id="8449b-176">Exchange Server TLS guidance, part 1: Getting Ready for TLS 1.2</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [<span data-ttu-id="8449b-177">Exchange Server TLS 지침 2부: TLS 1.2 사용 및 이를 사용하지 않는 클라이언트 식별</span><span class="sxs-lookup"><span data-stu-id="8449b-177">Exchange Server TLS guidance Part 2: Enabling TLS 1.2 and Identifying Clients Not Using It</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [<span data-ttu-id="8449b-178">Exchange Server TLS 지침 3부: TLS 1.0/1.1 끄기</span><span class="sxs-lookup"><span data-stu-id="8449b-178">Exchange Server TLS guidance Part 3: Turning Off TLS 1.0/1.1</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [<span data-ttu-id="8449b-179">Office Online Server에서 TLS 1.1 및 TLS 1.2 지원 사용</span><span class="sxs-lookup"><span data-stu-id="8449b-179">Enable TLS 1.1 and TLS 1.2 support in Office Online Server</span></span>](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)


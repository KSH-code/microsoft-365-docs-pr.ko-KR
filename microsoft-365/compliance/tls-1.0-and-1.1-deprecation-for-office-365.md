---
title: Microsoft 365에 대해 TLS 1.0 및 1.1을 사용 안 하게
description: Microsoft 365에 대한 TLS 1.0 및 1.1 사용 중지 및 비활성화에 대해 설명
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
ms.openlocfilehash: 3d44e178d351942b4a178ddc1954ddd839665639
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919304"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="ec8dd-103">Microsoft 365에 대해 TLS 1.0 및 1.1을 사용 안 하게</span><span class="sxs-lookup"><span data-stu-id="ec8dd-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec8dd-104">COVID-19로 인해 상업 고객의 경우 TLS 1.0 및 1.1의 비활성화를 일시적으로 중지했습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="ec8dd-105">공급망이 조정되고 특정 국가가 백업을 시작하면 2020년 10월 15일 TLS 1.2 적용 롤아웃이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="ec8dd-106">몇 주와 몇 개월에 한해 출시가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="ec8dd-107">2018년 10월 31일 현재, Microsoft 365 서비스에서는 TLS(전송 계층 보안) 1.0 및 1.1 프로토콜이 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="ec8dd-108">최종 사용자에게는 최소한의 영향만 미미합니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="ec8dd-109">이 변경은 2017년 12월에 첫 번째 공개 발표와 함께 2년 넘게 공개되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="ec8dd-110">이 문서는 Office 365 서비스와 관련한 Office 365 로컬 클라이언트에 대해 다루기 위한 것이지만 Office 및 Office Online Server/Office Web Apps의 사내 TLS 문제에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="ec8dd-111">SharePoint 및 OneDrive의 경우 TLS 1.2를 지원하도록 .NET을 업데이트하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="ec8dd-112">자세한 내용은 [클라이언트에서 TLS 1.2를 사용하도록 설정하는 방법을 참조하세요.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="ec8dd-112">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="ec8dd-113">Office 365 및 TLS 개요</span><span class="sxs-lookup"><span data-stu-id="ec8dd-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="ec8dd-114">Office 클라이언트는 WINHTTP(Windows 웹 서비스)를 사용하여 TLS 프로토콜을 통해 트래픽을 보내고 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="ec8dd-115">로컬 컴퓨터의 웹 서비스에서 TLS 1.2를 사용할 수 있는 경우 Office 클라이언트는 TLS 1.2를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="ec8dd-116">TLS 및 SSL 프로토콜은 Office 클라이언트와 관련이 없는 운영 체제의 일부로 모든 Office 클라이언트에서 TLS 프로토콜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="ec8dd-117">Windows 8 이상 버전</span><span class="sxs-lookup"><span data-stu-id="ec8dd-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="ec8dd-118">TLS 1.2 트래픽을 거부하도록 구성된 네트워크 장치가 없는 경우 기본적으로 TLS 1.2 및 1.1 프로토콜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="ec8dd-119">Windows 7의 경우</span><span class="sxs-lookup"><span data-stu-id="ec8dd-119">On Windows 7</span></span>

<span data-ttu-id="ec8dd-120">KB 3140245 업데이트가 없는 경우 TLS [1.1 및 1.2 프로토콜을 사용할 수](https://support.microsoft.com/help/3140245) 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="ec8dd-121">이 업데이트는 이 문제를 해결하고 다음 레지스트리 하위 키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="ec8dd-122">이 업데이트가 없는 Windows 7 사용자는 2018년 10월 31일 현재 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="ec8dd-123">[KB 3140245에는](https://support.microsoft.com/help/3140245) WINHTTP 설정을 변경하여 TLS 프로토콜을 사용하도록 설정하는 방법에 대한 세부 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="ec8dd-124">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ec8dd-124">More information</span></span>

<span data-ttu-id="ec8dd-125">KB 문서에서 설명하는 **DefaultSecureProtocols** 레지스트리 키의 값에 따라 사용할 수 있는 네트워크 프로토콜이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="ec8dd-126">DefaultSecureProtocols 값</span><span class="sxs-lookup"><span data-stu-id="ec8dd-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="ec8dd-127">프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="ec8dd-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="ec8dd-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="ec8dd-128">0x00000008</span></span>|<span data-ttu-id="ec8dd-129">기본적으로 SSL 2.0 사용</span><span class="sxs-lookup"><span data-stu-id="ec8dd-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="ec8dd-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="ec8dd-130">0x00000020</span></span>|<span data-ttu-id="ec8dd-131">기본적으로 SSL 3.0 사용</span><span class="sxs-lookup"><span data-stu-id="ec8dd-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="ec8dd-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="ec8dd-132">0x00000080</span></span>|<span data-ttu-id="ec8dd-133">기본적으로 TLS 1.0 사용</span><span class="sxs-lookup"><span data-stu-id="ec8dd-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="ec8dd-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="ec8dd-134">0x00000200</span></span>|<span data-ttu-id="ec8dd-135">기본적으로 TLS 1.1 사용</span><span class="sxs-lookup"><span data-stu-id="ec8dd-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="ec8dd-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="ec8dd-136">0x00000800</span></span>|<span data-ttu-id="ec8dd-137">기본적으로 TLS 1.2 사용</span><span class="sxs-lookup"><span data-stu-id="ec8dd-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="ec8dd-138">Office 클라이언트 및 TLS 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="ec8dd-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="ec8dd-139">[KB 4057306 Office 365에서 TLS 1.2의](https://support.microsoft.com/help/4057306)필수 사용 준비를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="ec8dd-140">이 문서는 IT 관리자를 위한 일반 문서로, TLS 1.2 변경에 대한 공식 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="ec8dd-141">다음 표에는 2018년 10월 31일 이후 Office 365 클라이언트의 적절한 레지스트리 키 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="ec8dd-142">2018년 10월 31일 이후 Office 365 서비스에 대한 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="ec8dd-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="ec8dd-143">16진수 값</span><span class="sxs-lookup"><span data-stu-id="ec8dd-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="ec8dd-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="ec8dd-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="ec8dd-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="ec8dd-145">0x00000A80</span></span>|
|<span data-ttu-id="ec8dd-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="ec8dd-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="ec8dd-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="ec8dd-147">0x00000A00</span></span>|
|<span data-ttu-id="ec8dd-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="ec8dd-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="ec8dd-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="ec8dd-149">0x00000880</span></span>|
|<span data-ttu-id="ec8dd-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="ec8dd-150">TLS 1.2</span></span>|<span data-ttu-id="ec8dd-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="ec8dd-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="ec8dd-152">**DefaultSecureProtocols** 키를 사용하여 설정할 수 있는 SSL 2.0 및 3.0 프로토콜을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="ec8dd-153">SSL 2.0 및 3.0은 기한이 지난 비보안 프로토콜로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="ec8dd-154">최상의 방법은 SSL 2.0 및 SSL 3.0 사용을 종료하는 것입니다. 그러나 이를 위한 결정은 궁극적으로 제품 요구 사항을 가장 잘 충족하는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="ec8dd-155">SSL 3.0 취약성에 대한 자세한 내용은 [KB 3009008을 참조하세요.](https://support.microsoft.com/help/3009008)</span><span class="sxs-lookup"><span data-stu-id="ec8dd-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="ec8dd-156">프로그래머 모드에서 기본 Windows 계산기를 사용하여 동일한 참조 레지스트리 키 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="ec8dd-157">자세한 내용은 [KB 3140245 업데이트를 참조하여 Windows의 WinHTTP에서 기본 보안 프로토콜로 TLS 1.1 및 TLS 1.2를](https://support.microsoft.com/help/3140245)사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="ec8dd-158">Windows 7[업데이트(KB 3140245)가](https://support.microsoft.com/help/3140245)설치되어 있는지와 관계없이 DefaultSecureProtocols 레지스트리 하위 키는 존재하지 않습니다. 수동으로 또는 GPO(그룹 정책 개체)를 통해 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="ec8dd-159">즉, 사용하도록 설정되거나 제한된 보안 프로토콜을 사용자 지정할 필요 없이 이 키가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="ec8dd-160">Windows 7 SP1([KB 3140245) 업데이트만](https://support.microsoft.com/help/3140245)필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="ec8dd-161">TLS 1.2를 .NET Framework 업데이트 및 구성</span><span class="sxs-lookup"><span data-stu-id="ec8dd-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="ec8dd-162">TLS 1.2를 사용하려면 TLS 1.0 또는 TLS 1.1을 통해 Microsoft 365 API를 호출하는 응용 프로그램을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="ec8dd-163">.NET 4.5는 기본적으로 TLS 1.1로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="ec8dd-164">.NET 구성을 업데이트하려면 [클라이언트에서 TLS(전송 계층 보안) 1.2를](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)사용하도록 설정하는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="ec8dd-165">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ec8dd-165">More information</span></span>

<span data-ttu-id="ec8dd-166">자세한 내용은 [Office 365에서 TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec8dd-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
---
title: Office 365용 TLS 1.0 및 1.1 사용 중단
description: Office 365의 TLS 1.0 및 1.1 사용되지 않습니다.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777060"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="117ea-103">Office 365용 TLS 1.0 및 1.1 사용 중단</span><span class="sxs-lookup"><span data-stu-id="117ea-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="117ea-104">COVID-19로 인해 상업 고객의 경우 TLS 1.0 및 1.1의 사용 중단이 일시적으로 중단되었습니다. 그러나 공급망이 조정되고 특정 국가가 백업될 때 TLS 적용이 2020년 10월 15일부터 다시 설정되고 있으며, 다음 주와 몇 개월 동안 롤아웃이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to COVID-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to begin October 15, 2020, and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="117ea-105">2018년 10월 31일 현재, Office 365 서비스에 대해 TLS(전송 계층 보안) 1.0 및 1.1 프로토콜은 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="117ea-106">최종 사용자에게는 최소한의 영향이 있을 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="117ea-107">이 변경은 2년 이상 공개되고 2017년 12월에 첫 번째 공개 발표가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="117ea-108">이 문서는 Office 365 서비스와 관련한 Office 365 로컬 클라이언트에 대해 다루기 위한 것일 뿐 아니라 Office 및 Office Online Server/Office Web Apps의 온라인 TLS 문제에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="117ea-109">Office 및 TLS 개요</span><span class="sxs-lookup"><span data-stu-id="117ea-109">Office and TLS overview</span></span>

<span data-ttu-id="117ea-110">Office 클라이언트는 WINHTTP(Windows 웹 서비스)를 사용하여 TLS 프로토콜을 통해 트래픽을 보내고 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="117ea-111">로컬 컴퓨터의 웹 서비스가 TLS 1.2를 사용할 수 있는 경우 Office 클라이언트는 TLS 1.2를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="117ea-112">TLS 및 SSL 프로토콜은 Office 클라이언트와 관련이 없는 운영 체제의 일부이기에 따라 모든 Office 클라이언트는 TLS 프로토콜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="117ea-113">Windows 8 이상 버전</span><span class="sxs-lookup"><span data-stu-id="117ea-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="117ea-114">TLS 1.2 트래픽을 거부하도록 구성된 네트워크 장치가 없는 경우 기본적으로 TLS 1.2 및 1.1 프로토콜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="117ea-115">Windows 7의 경우</span><span class="sxs-lookup"><span data-stu-id="117ea-115">On Windows 7</span></span>

<span data-ttu-id="117ea-116">KB [3140245 업데이트가 없는 경우 TLS 1.1 및 1.2 프로토콜을 사용할 수](https://support.microsoft.com/help/3140245) 없습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="117ea-117">업데이트는 이 문제를 해결하고 다음 레지스트리 하위 키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="117ea-118">이 업데이트가 없는 Windows 7 사용자는 2018년 10월 31일 현재 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="117ea-119">[KB 3140245에는](https://support.microsoft.com/help/3140245) TLS 프로토콜을 사용하도록 WINHTTP 설정을 변경하는 방법에 대한 세부 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="117ea-120">추가 정보</span><span class="sxs-lookup"><span data-stu-id="117ea-120">More information</span></span>

<span data-ttu-id="117ea-121">KB 문서에서 설명하는 **DefaultSecureProtocols** 레지스트리 키의 값에 따라 사용할 수 있는 네트워크 프로토콜이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="117ea-122">DefaultSecureProtocols 값</span><span class="sxs-lookup"><span data-stu-id="117ea-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="117ea-123">프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="117ea-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="117ea-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="117ea-124">0x00000008</span></span>|<span data-ttu-id="117ea-125">기본적으로 SSL 2.0 사용</span><span class="sxs-lookup"><span data-stu-id="117ea-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="117ea-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="117ea-126">0x00000020</span></span>|<span data-ttu-id="117ea-127">기본적으로 SSL 3.0 사용</span><span class="sxs-lookup"><span data-stu-id="117ea-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="117ea-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="117ea-128">0x00000080</span></span>|<span data-ttu-id="117ea-129">기본적으로 TLS 1.0 사용</span><span class="sxs-lookup"><span data-stu-id="117ea-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="117ea-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="117ea-130">0x00000200</span></span>|<span data-ttu-id="117ea-131">기본적으로 TLS 1.1 사용</span><span class="sxs-lookup"><span data-stu-id="117ea-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="117ea-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="117ea-132">0x00000800</span></span>|<span data-ttu-id="117ea-133">기본적으로 TLS 1.2 사용</span><span class="sxs-lookup"><span data-stu-id="117ea-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="117ea-134">Office 클라이언트 및 TLS 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="117ea-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="117ea-135">[Office 365에서 TLS 1.2의 필수 사용을 준비하는 KB 4057306을](https://support.microsoft.com/help/4057306)참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="117ea-136">이 문서는 IT 관리자를 위한 일반 문서로, TLS 1.2 변경에 대한 공식 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="117ea-137">다음 표에는 2018년 10월 31일 이후 Office 365 클라이언트의 적절한 레지스트리 키 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="117ea-138">2018년 10월 31일 이후 Office 365 서비스에 대한 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="117ea-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="117ea-139">16진수 값</span><span class="sxs-lookup"><span data-stu-id="117ea-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="117ea-140">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="117ea-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="117ea-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="117ea-141">0x00000A80</span></span>|
|<span data-ttu-id="117ea-142">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="117ea-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="117ea-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="117ea-143">0x00000A00</span></span>|
|<span data-ttu-id="117ea-144">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="117ea-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="117ea-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="117ea-145">0x00000880</span></span>|
|<span data-ttu-id="117ea-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="117ea-146">TLS 1.2</span></span>|<span data-ttu-id="117ea-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="117ea-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="117ea-148">**DefaultSecureProtocols** 키를 사용하여 설정할 수도 있는 SSL 2.0 및 3.0 프로토콜은 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="117ea-149">SSL 2.0 및 3.0은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="117ea-150">최상의 방법은 SSL 2.0 및 SSL 3.0 사용을 종료하는 것입니다. 그러나 이를 위한 결정은 궁극적으로 제품 요구 사항을 가장 잘 충족하는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="117ea-151">SSL 3.0 취약성에 대한 자세한 내용은 [KB 3009008을 참조하십시오.](https://support.microsoft.com/help/3009008)</span><span class="sxs-lookup"><span data-stu-id="117ea-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="117ea-152">프로그래머 모드에서 기본 Windows 계산기를 사용하여 동일한 참조 레지스트리 키 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="117ea-153">자세한 내용은 [Windows의 WinHTTP에서 TLS 1.1 및 TLS 1.2를 기본 보안 프로토콜로 사용하도록 설정하려면 KB 3140245 업데이트를 참조하세요.](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="117ea-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="117ea-154">Windows 7[업데이트(KB 3140245)가](https://support.microsoft.com/help/3140245)설치되어 있는지와 관계없이 DefaultSecureProtocols 레지스트리 하위 키가 존재하지 않습니다. 수동으로 또는 GPO(그룹 정책 개체)를 통해 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="117ea-155">즉, 사용하도록 설정되거나 제한된 보안 프로토콜을 사용자 지정할 필요 없이 이 키가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="117ea-156">Windows 7[SP1(KB 3140245) 업데이트만](https://support.microsoft.com/help/3140245)필요합니다.</span><span class="sxs-lookup"><span data-stu-id="117ea-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

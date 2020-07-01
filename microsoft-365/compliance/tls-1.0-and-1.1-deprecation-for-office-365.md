---
title: Office 365 TLS 1.0 및 1.1의 중단
description: Office 365에 대 한 TLS 1.0 및 1.1의 중단에 대해 설명 합니다.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 611b6970c3ecb95f4cdf046b96a5e3aa9155391d
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937346"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="4ea7f-103">Office 365 TLS 1.0 및 1.1의 중단</span><span class="sxs-lookup"><span data-stu-id="4ea7f-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>

<span data-ttu-id="4ea7f-104">2018 년 10 월 31 일까 지, Office 365 서비스에 대해 TLS (전송 계층 보안) 1.0 및 1.1 프로토콜이 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-104">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="4ea7f-105">최종 사용자에 대 한 영향은 최소한으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-105">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="4ea7f-106">이 변경 내용은 12 월 2017의 첫 번째 공개 알림을 사용 하 여 거의 2 년 동안 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-106">This change was publicized for almost two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="4ea7f-107">이 문서는 office 365 서비스와 관련 하 여 Office 365 로컬 클라이언트에만 적용 되는 것이 좋지만 Office 및 Office Online Server/Office Web Apps에 온-프레미스 TLS 문제에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-107">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="4ea7f-108">Office 및 TLS 개요</span><span class="sxs-lookup"><span data-stu-id="4ea7f-108">Office and TLS overview</span></span>

<span data-ttu-id="4ea7f-109">Office 클라이언트는 WINHTTP (Windows web service)를 사용 하 여 TLS 프로토콜을 통해 트래픽을 주고 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-109">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="4ea7f-110">로컬 컴퓨터의 웹 서비스가 TLS 1.2를 사용할 수 있는 경우 Office 클라이언트에서 TLS 1.2을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-110">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="4ea7f-111">TLS 및 SSL 프로토콜은 Office 클라이언트와 관련 되지 않고 운영 체제에 포함 되므로 모든 Office 클라이언트에서 TLS 프로토콜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-111">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="4ea7f-112">Windows 8 이상 버전</span><span class="sxs-lookup"><span data-stu-id="4ea7f-112">On Windows 8 and later versions</span></span>

<span data-ttu-id="4ea7f-113">Tls 1.2 트래픽을 거부 하도록 구성 된 네트워크 장치가 없으면 기본적으로 TLS 1.2 및 1.1 프로토콜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-113">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="4ea7f-114">Windows 7</span><span class="sxs-lookup"><span data-stu-id="4ea7f-114">On Windows 7</span></span>

<span data-ttu-id="4ea7f-115">TLS 1.1 및 1.2 프로토콜은 [5003140245](https://support.microsoft.com/help/3140245) 업데이트 없이 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-115">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="4ea7f-116">이 업데이트는이 문제를 해결 하 고 다음 레지스트리 하위 키를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-116">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="4ea7f-117">이 업데이트가 없는 Windows 7 사용자는 2018 년 10 월 31 일의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-117">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="4ea7f-118">이 [3140245](https://support.microsoft.com/help/3140245) 는 TLS 프로토콜을 사용 하도록 WINHTTP 설정을 변경 하는 방법에 대 한 세부 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-118">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="4ea7f-119">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4ea7f-119">More information</span></span>

<span data-ttu-id="4ea7f-120">기술 자료 문서에 설명 된 **Defaultsecureprotocols** 레지스트리 키의 값은 사용할 수 있는 네트워크 프로토콜을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-120">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="4ea7f-121">DefaultSecureProtocols 값</span><span class="sxs-lookup"><span data-stu-id="4ea7f-121">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="4ea7f-122">프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="4ea7f-122">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="4ea7f-123">0x00000008</span><span class="sxs-lookup"><span data-stu-id="4ea7f-123">0x00000008</span></span>|<span data-ttu-id="4ea7f-124">기본적으로 SSL 2.0 사용</span><span class="sxs-lookup"><span data-stu-id="4ea7f-124">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="4ea7f-125">0x00000020</span><span class="sxs-lookup"><span data-stu-id="4ea7f-125">0x00000020</span></span>|<span data-ttu-id="4ea7f-126">기본적으로 SSL 3.0 사용</span><span class="sxs-lookup"><span data-stu-id="4ea7f-126">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="4ea7f-127">0x00000080</span><span class="sxs-lookup"><span data-stu-id="4ea7f-127">0x00000080</span></span>|<span data-ttu-id="4ea7f-128">기본적으로 TLS 1.0 사용</span><span class="sxs-lookup"><span data-stu-id="4ea7f-128">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="4ea7f-129">0x00000200</span><span class="sxs-lookup"><span data-stu-id="4ea7f-129">0x00000200</span></span>|<span data-ttu-id="4ea7f-130">기본적으로 TLS 1.1 사용</span><span class="sxs-lookup"><span data-stu-id="4ea7f-130">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="4ea7f-131">0x00000800</span><span class="sxs-lookup"><span data-stu-id="4ea7f-131">0x00000800</span></span>|<span data-ttu-id="4ea7f-132">기본적으로 TLS 1.2 사용</span><span class="sxs-lookup"><span data-stu-id="4ea7f-132">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="4ea7f-133">Office 클라이언트 및 TLS 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="4ea7f-133">Office clients and TLS registry keys</span></span>

<span data-ttu-id="4ea7f-134">[Office 365에서 TLS 1.2의 필수 사용을 위해 4057306을 준비 하는](https://support.microsoft.com/help/4057306)것을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-134">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="4ea7f-135">이 문서는 IT 관리자를 위한 일반적인 문서로, TLS 1.2 변경 사항에 대 한 공식적인 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-135">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="4ea7f-136">다음 표에서는 2018 년 10 월 31 일 이후에 Office 365 클라이언트의 해당 레지스트리 키 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-136">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="4ea7f-137">설정 된 Office 365 서비스에 대 한 사용 프로토콜 (2018 년 10 월 31 일)</span><span class="sxs-lookup"><span data-stu-id="4ea7f-137">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="4ea7f-138">16 진수 값</span><span class="sxs-lookup"><span data-stu-id="4ea7f-138">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="4ea7f-139">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="4ea7f-139">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="4ea7f-140">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="4ea7f-140">0x00000A80</span></span>|
|<span data-ttu-id="4ea7f-141">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="4ea7f-141">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="4ea7f-142">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="4ea7f-142">0x00000A00</span></span>|
|<span data-ttu-id="4ea7f-143">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="4ea7f-143">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="4ea7f-144">0x00000880</span><span class="sxs-lookup"><span data-stu-id="4ea7f-144">0x00000880</span></span>|
|<span data-ttu-id="4ea7f-145">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="4ea7f-145">TLS 1.2</span></span>|<span data-ttu-id="4ea7f-146">0x00000800</span><span class="sxs-lookup"><span data-stu-id="4ea7f-146">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="4ea7f-147">**Defaultsecureprotocols** 키를 사용해 서도 설정할 수 있는 SSL 2.0 및 3.0 프로토콜은 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-147">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="4ea7f-148">SSL 2.0 및 3.0는 더 이상 사용 되지 않는 프로토콜로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-148">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="4ea7f-149">SSL 2.0 및 SSL 3.0의 사용을 종료 하는 것이 가장 좋지만, 이러한 방법은 제품 요구 사항에 가장 적합 한 결정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-149">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="4ea7f-150">SSL 3.0 취약성에 대 한 자세한 내용은 [kb(3009008](https://support.microsoft.com/help/3009008)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-150">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="4ea7f-151">프로그래머용 모드에서 기본 Windows 계산기를 사용 하 여 동일한 참조 레지스트리 키 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-151">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="4ea7f-152">자세한 내용은 [Windows의 WinHTTP에서 tls 1.1 및 tls 1.2을 기본 보안 프로토콜로 사용 하도록 설정 하려면-프로토콜 3140245 업데이트](https://support.microsoft.com/help/3140245)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-152">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="4ea7f-153">Windows 7 업데이트 ([KB 3140245](https://support.microsoft.com/help/3140245))가 설치 되어 있는지 여부에 관계 없이 DefaultSecureProtocols 레지스트리 하위 키가 존재 하지 않으므로 수동으로 또는 GPO (그룹 정책 개체)를 통해 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-153">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="4ea7f-154">즉, 사용할 수 있거나 제한 되는 보안 프로토콜을 사용자 지정 해야 하는 경우가 아니면이 키가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-154">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="4ea7f-155">Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) 업데이트만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea7f-155">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

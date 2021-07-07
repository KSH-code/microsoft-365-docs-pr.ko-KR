---
title: 엔드포인트용 Microsoft Defender(Windows가 아닌 플랫폼)
description: 비영리 플랫폼용 Microsoft Defender for Endpoint Windows 자세히 알아보기
keywords: 비 windows, mac, macos, linux, android
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4793f3c84ddda0db7f4d67ac96cb31a6e2108c57
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327002"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a><span data-ttu-id="76223-104">엔드포인트용 Microsoft Defender(Windows가 아닌 플랫폼)</span><span class="sxs-lookup"><span data-stu-id="76223-104">Microsoft Defender for Endpoint for non-Windows platforms</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="76223-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="76223-105">**Applies to:**</span></span>
- [<span data-ttu-id="76223-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="76223-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="76223-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76223-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="76223-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="76223-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76223-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="76223-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="76223-110">Microsoft는 macOS, Linux, Android 및 iOS로 Windows Windows 업계를 선도하는 엔드포인트 보안 기능을 확장하기 위한 여정을 해오고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-110">Microsoft has been on a journey to extend its industry leading endpoint security capabilities beyond Windows and Windows Server to macOS, Linux, Android, and iOS.</span></span>

<span data-ttu-id="76223-111">조직은 다양한 플랫폼 및 장치에서 위협에 직면해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-111">Organizations face threats across a variety of platforms and devices.</span></span> <span data-ttu-id="76223-112">당사의 팀은 고객이 다른 환경을 보호하고 보호할 수 있도록 *Microsoft* 뿐만 아니라 *Microsoft에서도* 보안 솔루션을 구축하기 위해 최선을 다하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-112">Our teams have committed to building security solutions not just *for* Microsoft, but also *from* Microsoft to enable our customers to protect and secure their heterogenous environments.</span></span> <span data-ttu-id="76223-113">고객 의견을 경청하고 고객과 긴밀히 협력하여 요구 사항을 충족하는 솔루션을 구축하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-113">We're listening to customer feedback and partnering closely with our customers to build solutions that meet their needs.</span></span>

<span data-ttu-id="76223-114">끝점용 Microsoft Defender를 통해 고객은 Microsoft Defender 보안 센터 및 비 Windows Windows 플랫폼에서 Microsoft Defender 보안 센터 및 비영리 플랫폼의 모든 위협 및 경고에 대한 통합된 보기를 통해 해당 환경에서 일어나는 일에 대한 전체적인 그림을 얻을 수 있으므로 위협을 보다 신속하게 평가하고 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-114">With Microsoft Defender for Endpoint, customers benefit from a unified view of all threats and alerts in the Microsoft Defender Security Center, across Windows and non-Windows platforms, enabling them to get a full picture of what's happening in their environment, which empowers them to more quickly assess and respond to threats.</span></span>

## <a name="microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="76223-115">Microsoft Defender for Endpoint(macOS용)</span><span class="sxs-lookup"><span data-stu-id="76223-115">Microsoft Defender for Endpoint on macOS</span></span> 

<span data-ttu-id="76223-116">MacOS의 끝점용 Microsoft Defender는 세 가지 최신 릴리스 버전의 macOS에 대한 바이러스 백신EDR 엔드포인트 감지 및 응답(취약성 관리) 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76223-116">Microsoft Defender for Endpoint on macOS offers antivirus, endpoint detection and response (EDR), and vulnerability management capabilities for the three latest released versions of macOS.</span></span> <span data-ttu-id="76223-117">고객은 파트너 및 Jamf를 통해 솔루션을 Microsoft Endpoint Manager 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-117">Customers can deploy and manage the solution through Microsoft Endpoint Manager and Jamf.</span></span> <span data-ttu-id="76223-118">macOS의 Microsoft Office 응용 프로그램과 마찬가지로 Microsoft 자동 업데이트는 Mac 업데이트에서 끝점용 Microsoft Defender를 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76223-118">Just like with Microsoft Office applications on macOS, Microsoft Auto Update is used to manage Microsoft Defender for Endpoint on Mac updates.</span></span> <span data-ttu-id="76223-119">주요 기능 및 이점에 대한 자세한 내용은 공지 사항을 [읽어 하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)</span><span class="sxs-lookup"><span data-stu-id="76223-119">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS).</span></span>

<span data-ttu-id="76223-120">시작하는 방법에 대한 자세한 내용은 macOS 설명서의 Endpoint용 Defender를 [참조하세요.](microsoft-defender-endpoint-mac.md)</span><span class="sxs-lookup"><span data-stu-id="76223-120">For more details on how to get started, visit the Defender for Endpoint on macOS [documentation](microsoft-defender-endpoint-mac.md).</span></span>

>[!NOTE]
><span data-ttu-id="76223-121">다음 기능은 현재 macOS 끝점에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-121">The following capabilities are not currently supported on macOS endpoints:</span></span>
>- <span data-ttu-id="76223-122">데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="76223-122">Data loss prevention</span></span>
>- <span data-ttu-id="76223-123">라이브 응답</span><span class="sxs-lookup"><span data-stu-id="76223-123">Live response</span></span>
>- <span data-ttu-id="76223-124">SIEM</span><span class="sxs-lookup"><span data-stu-id="76223-124">SIEM</span></span>


## <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="76223-125">엔드포인트용 Microsoft Defender(Linux용)</span><span class="sxs-lookup"><span data-stu-id="76223-125">Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="76223-126">Linux의 끝점용 Microsoft Defender는 Linux 서버에 대한 예방용(AV), 끝점 EDR 및 응답(취약성 관리) 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76223-126">Microsoft Defender for Endpoint on Linux offers preventative (AV), endpoint detection and response (EDR), and vulnerability management capabilities for Linux servers.</span></span> <span data-ttu-id="76223-127">여기에는 에이전트를 구성 및 관리하고, 검색을 시작하고, 위협을 관리하는 전체 명령줄 환경이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="76223-127">This includes a full command line experience to configure and manage the agent, initiate scans, and manage threats.</span></span> <span data-ttu-id="76223-128">가장 일반적인 여섯 가지 Linux 서버 배포인 RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS 이상 LTS, SLES 12+, 데비안 9+, Oracle Linux 7.2의 최신 버전을 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-128">We support recent versions of the six most common Linux Server distributions: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS, or higher LTS, SLES 12+, Debian 9+, and Oracle Linux 7.2.</span></span> <span data-ttu-id="76223-129">Linux의 끝점용 Microsoft Defender는 Puppet, Ansible 또는 기존 Linux 구성 관리 도구를 사용하여 배포 및 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-129">Microsoft Defender for Endpoint on Linux can be deployed and configured using Puppet, Ansible, or using your existing Linux configuration management tool.</span></span> <span data-ttu-id="76223-130">주요 기능 및 이점에 대한 자세한 내용은 공지 사항을 [읽어 하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)</span><span class="sxs-lookup"><span data-stu-id="76223-130">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux).</span></span>

<span data-ttu-id="76223-131">시작하는 방법에 대한 자세한 내용은 Linux 설명서의 Microsoft Defender for Endpoint를 [참조하세요.](microsoft-defender-endpoint-linux.md)</span><span class="sxs-lookup"><span data-stu-id="76223-131">For more details on how to get started, visit the Microsoft Defender for Endpoint on Linux [documentation](microsoft-defender-endpoint-linux.md).</span></span>

>[!NOTE]
><span data-ttu-id="76223-132">다음 기능은 현재 Linux 끝점에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-132">The following capabilities are not currently supported on Linux endpoints:</span></span>
>- <span data-ttu-id="76223-133">데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="76223-133">Data loss prevention</span></span>
>- <span data-ttu-id="76223-134">라이브 응답</span><span class="sxs-lookup"><span data-stu-id="76223-134">Live response</span></span>
>- <span data-ttu-id="76223-135">SIEM</span><span class="sxs-lookup"><span data-stu-id="76223-135">SIEM</span></span>



## <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="76223-136">Microsoft Defender for Endpoint(Android용)</span><span class="sxs-lookup"><span data-stu-id="76223-136">Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="76223-137">Android의 끝점용 Microsoft Defender는 Android 6.0 이상을 실행하는 장치에 대한 모바일 위협 방어 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="76223-137">Microsoft Defender for Endpoint on Android is our mobile threat defense solution for devices running Android 6.0 and higher.</span></span> <span data-ttu-id="76223-138">Android Enterprise(작업 프로필) 및 장치 관리자 모드가 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="76223-138">Both Android Enterprise (Work Profile) and Device Administrator modes are supported.</span></span> <span data-ttu-id="76223-139">Android에서는 피싱 방지, 안전하지 않은 연결 차단 및 사용자 지정 표시기 설정을 포함하는 웹 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76223-139">On Android, we offer web protection, which includes anti-phishing, blocking of unsafe connections, and setting of custom indicators.</span></span> <span data-ttu-id="76223-140">이 솔루션은 맬웨어 및 잠재적으로 원치 않는 응용 프로그램(PUA)을 검색하고, 맬웨어 및 조건부 액세스와의 통합을 Microsoft Endpoint Manager 위반 방지 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76223-140">The solution scans for malware and potentially unwanted applications (PUA) and offers additional breach prevention capabilities through integration with Microsoft Endpoint Manager and Conditional Access.</span></span> <span data-ttu-id="76223-141">주요 기능 및 이점에 대한 자세한 내용은 공지 사항을 [읽어 하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)</span><span class="sxs-lookup"><span data-stu-id="76223-141">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android).</span></span>

<span data-ttu-id="76223-142">시작하는 방법에 대한 자세한 내용은 Android의 끝점용 Microsoft Defender 설명서를 [참조하세요.](microsoft-defender-endpoint-android.md)</span><span class="sxs-lookup"><span data-stu-id="76223-142">For more details on how to get started, visit the Microsoft Defender for Endpoint on Android [documentation](microsoft-defender-endpoint-android.md).</span></span>

## <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="76223-143">Microsoft Defender for Endpoint(iOS용)</span><span class="sxs-lookup"><span data-stu-id="76223-143">Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="76223-144">iOS의 끝점용 Microsoft Defender는 iOS 11.0 이상을 실행하는 장치에 대한 모바일 위협 방어 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="76223-144">Microsoft Defender for Endpoint on iOS is our mobile threat defense solution for devices running iOS 11.0 and higher.</span></span> <span data-ttu-id="76223-145">감독된 디바이스와 관리되지 않는 장치가 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="76223-145">Both Supervised and Unsupervised devices are supported.</span></span> <span data-ttu-id="76223-146">iOS에서는 피싱 방지, 안전하지 않은 연결 차단 및 사용자 지정 표시기 설정이 포함된 웹 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76223-146">On iOS, we offer web protection which includes anti-phishing, blocking unsafe connections, and setting custom indicators.</span></span> <span data-ttu-id="76223-147">주요 기능 및 이점에 대한 자세한 내용은 공지 사항을 [읽어 하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="76223-147">For more information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span> 

<span data-ttu-id="76223-148">시작 방법에 대한 자세한 내용은 iOS 설명서의 Microsoft Defender for Endpoint를 [참조하세요.](microsoft-defender-endpoint-ios.md)</span><span class="sxs-lookup"><span data-stu-id="76223-148">For more details on how to get started, visit the Microsoft Defender for Endpoint on iOS [documentation](microsoft-defender-endpoint-ios.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="76223-149">라이선스 요구사항</span><span class="sxs-lookup"><span data-stu-id="76223-149">Licensing requirements</span></span> 

<span data-ttu-id="76223-150">적격 라이선스 사용자는 최대 5개의 동시 장치에서 끝점용 Microsoft Defender를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-150">Eligible Licensed Users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span> <span data-ttu-id="76223-151">Microsoft Defender for Endpoint는 CSP(Microsoft Defender for Endpoint)에서 클라우드 솔루션 공급자 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-151">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="76223-152">고객은 독립 실행형 Microsoft Defender for Endpoint 라이선스를 통해 macOS의 끝점용 Microsoft Defender를 Microsoft 365 A5/E5 또는 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-152">Customers can obtain Microsoft Defender for Endpoint on macOS through a standalone Microsoft Defender for Endpoint license, as part of Microsoft 365 A5/E5, or Microsoft 365 Security.</span></span>

<span data-ttu-id="76223-153">최근에 발표된 Android 및 iOS용 끝점용 Microsoft Defender 기능은 적격 라이선스 사용자에 대한 5개의 적격 디바이스의 일부로 위에서 언급한 혜택에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-153">Recently announced capabilities of Microsoft Defender for Endpoint on Android and iOS are included in the above mentioned offers as part of the five qualified devices for eligible licensed users.</span></span>

<span data-ttu-id="76223-154">Linux의 끝점용 Defender는 상업 및 교육 고객에게 모두 사용할 수 있는 Endpoint Server SKU용 Defender를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76223-154">Defender for Endpoint on Linux is available through the Defender for Endpoint Server SKU that is available for both commercial and education customers.</span></span>

<span data-ttu-id="76223-155">가격 책정 및 추가 자격 요구 사항은 계정 팀 또는 CSP에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="76223-155">Please contact your account team or CSP for pricing and additional eligibility requirements.</span></span>

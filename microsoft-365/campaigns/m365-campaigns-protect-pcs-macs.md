---
title: 관리되지 않는 Windows 10 PC 및 Mac 보호
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365를 통해 관리되지 않는 장치 또는 BYOD(Bring Your Own Devices)를 보호합니다.
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044387"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="21874-103">관리되지 않는 Windows 10 PC 및 Mac 보호</span><span class="sxs-lookup"><span data-stu-id="21874-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="21874-104">Microsoft Intune에 등록하여 Windows 10 PC 및 Mac을 관리할 수 있습니다. 이를 통해 환경의 데이터에 액세스하기 전에 정상 및 안전을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21874-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="21874-105">그러나 많은 캠페인과 중소기업에는 조직에서 관리하지 않는 BYOD(자체 장치)를 가져오는 직원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21874-105">However, many campaigns and small businesses include staff who bring their own devices (BYOD), which will not be managed by the organization.</span></span> <span data-ttu-id="21874-106">이러한 관리되지 않는 PC 및 Mac의 경우 이 문서를 사용하여 최소 보안 기능이 구성되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="21874-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span>

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="21874-107">Windows 10 또는 Mac을 실행하는 컴퓨터 보호</span><span class="sxs-lookup"><span data-stu-id="21874-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="21874-108">Windows 10 PC 또는 Mac이 조직에서 관리되지 않는 경우 이러한 보안 기능을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21874-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="21874-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="21874-109">Windows 10</span></span>](#tab/Windows10)

<span data-ttu-id="21874-110">**장치 암호화 켜기**</span><span class="sxs-lookup"><span data-stu-id="21874-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="21874-111">장치 암호화는 광범위한 Windows 장치에서 사용할 수 있으며 데이터를 암호화하여 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21874-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="21874-112">장치 암호화를 켜면 권한이 부여된 개인만 장치 및 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21874-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="21874-113">지침은 [장치 암호화](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 켜기 기능을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21874-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="21874-114">장치에서 장치 암호화를 사용할 수 없는 경우 대신 표준 [BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 암호화를 켜면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21874-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="21874-115">(BitLocker는 Windows 10 Home 버전에서 사용할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="21874-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 

<span data-ttu-id="21874-116">**Windows 보안으로 디바이스 보호**</span><span class="sxs-lookup"><span data-stu-id="21874-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="21874-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span><span class="sxs-lookup"><span data-stu-id="21874-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="21874-118">Windows 10을 처음 시작하면 Windows 보안이 설정되어 있으며 맬웨어(악성 소프트웨어), 바이러스 및 보안 위협을 검사하여 PC 보호를 적극적으로 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21874-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="21874-119">Windows 보안은 실시간 보호를 사용하여 PC에서 다운로드하거나 실행한 모든 것을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="21874-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="21874-120">Windows 업데이트는 Windows 보안에 대한 업데이트를 자동으로 다운로드하여 PC를 안전하게 유지하고 위협으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="21874-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="21874-121">이전 버전의 Windows가 있는 경우 Microsoft Security Essentials Windows 보안으로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="21874-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="21874-122">자세한 내용은 [Windows 보안으로 내 장치를 보호하는 도움말을 참조하세요.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)</span><span class="sxs-lookup"><span data-stu-id="21874-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="21874-123">**Windows 방화벽 켜기**</span><span class="sxs-lookup"><span data-stu-id="21874-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="21874-124">다른 방화벽이 켜져 있는 경우에도 항상 Windows 방화벽을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21874-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="21874-125">Windows 방화벽을 끄면 장치(및 네트워크가 있는 경우)가 무단 액세스에 더 취약해집니다.</span><span class="sxs-lookup"><span data-stu-id="21874-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="21874-126">지침은 [Windows 방화벽](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) 켜기 또는 끄기 참조</span><span class="sxs-lookup"><span data-stu-id="21874-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mac"></a>[<span data-ttu-id="21874-127">Mac</span><span class="sxs-lookup"><span data-stu-id="21874-127">Mac</span></span>](#tab/Mac)

<span data-ttu-id="21874-128">**FileVault를 사용하여 Mac 디스크 암호화**</span><span class="sxs-lookup"><span data-stu-id="21874-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="21874-129">디스크 암호화는 장치를 분실하거나 도난당한 경우 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="21874-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="21874-130">FileVault 전체 디스크 암호화를 사용하면 시작 디스크의 정보에 무단으로 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21874-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="21874-131">지침은 [FileVault를 사용하여 Mac의](https://support.apple.com/HT204837) 시작 디스크를 암호화하세요.</span><span class="sxs-lookup"><span data-stu-id="21874-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="21874-132">**맬웨어로부터 mac 보호**</span><span class="sxs-lookup"><span data-stu-id="21874-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="21874-133">Mac에 신뢰할 수 있는 바이러스 백신 소프트웨어를 설치하고 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="21874-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="21874-134">선택 항목 목록은 다음 문서를 [참조하세요. 최상의 Mac 바이러스 백신 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="21874-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="21874-135">신뢰할 수 있는 원본에서만 소프트웨어를 사용하여 맬웨어의 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21874-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="21874-136">보안 및 개인 정보 & 설정을 사용하면 Mac에 설치된 소프트웨어 원본을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21874-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="21874-137">자세한 내용은 [맬웨어로부터 Mac을 보호하세요.](https://support.apple.com/kb/PH25087)</span><span class="sxs-lookup"><span data-stu-id="21874-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="21874-138">**방화벽 보호 켜기**</span><span class="sxs-lookup"><span data-stu-id="21874-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="21874-139">방화벽 설정을 사용하여 인터넷 또는 네트워크에 연결되어 있는 경우 다른 컴퓨터에서 시작한 원치 않는 연락처로부터 Mac을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="21874-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="21874-140">이러한 보호가 없는 경우 Mac은 무단 액세스에 더 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21874-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="21874-141">지침은 [응용 프로그램 방화벽에](https://support.apple.com/HT201642) 대해 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21874-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>

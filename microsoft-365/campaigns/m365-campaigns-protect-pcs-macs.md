---
title: 관리 되지 않는 Windows 10 Pc 및 Mac 보호
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 for 캠페인을 통해 피싱 및 기타 공격 으로부터 보호 합니다.
ms.openlocfilehash: 8b83fa9c145f2c17347fc4c2983c64d4003f46c8
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183374"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="d5f56-103">관리 되지 않는 Windows 10 Pc 및 Mac 보호</span><span class="sxs-lookup"><span data-stu-id="d5f56-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="d5f56-104">이를 Microsoft Intune에 등록 하 여 Windows 10 Pc 및 Mac을 관리할 수 있으며,이를 통해 해당 환경의 데이터에 액세스 하기 전에 이러한 장치를 안전 하 고 안전한 상태로 유지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-104">You can manage Windows 10 PCs and Macs by enrolling these into Microsoft Intune, which allows you to ensure these are healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="d5f56-105">그러나 많은 캠페인 및 소규모 기업에는 조직에서 관리할 수 없는 byod (자체 장치)를 제공 하는 인력이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-105">However, many campaigns and small businesses include staff that bring their own devices (byod) which will not be managed by the organization.</span></span> <span data-ttu-id="d5f56-106">이러한 관리 되지 않는 Pc 및 Mac에 대해이 문서를 사용 하 여 최소 보안 기능이 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-106">For these unmanaged PCs and Macs, use this article to ensure minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="d5f56-107">Windows 10 또는 Mac을 실행 하는 컴퓨터 보호</span><span class="sxs-lookup"><span data-stu-id="d5f56-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="d5f56-108">조직에서 Windows 10 PC 또는 Mac을 관리 하지 않는 경우 이러한 보안 기능을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10tabwindows10"></a>[<span data-ttu-id="d5f56-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d5f56-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="d5f56-110">**장치 암호화 켜기**</span><span class="sxs-lookup"><span data-stu-id="d5f56-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="d5f56-111">다양 한 범위의 Windows 장치에서 장치 암호화를 사용할 수 있으며 암호화를 통해 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="d5f56-112">장치 암호화를 켜면 승인 된 사용자만 장치 및 데이터에 액세스할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="d5f56-113">자세한 내용은 [장치 암호화 설정을](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f56-113">See [turn on device encryption](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="d5f56-114">장치에서 장치 암호화를 사용할 수 없는 경우 표준 [BitLocker 암호화](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) 를 대신 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-114">If device encryption is not available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="d5f56-115">BitLocker는 Windows 10 Home edition에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-115">(BitLocker is not available on Windows 10 Home edition.)</span></span> 



<span data-ttu-id="d5f56-116">**Windows 보안을 사용 하 여 장치 보호**</span><span class="sxs-lookup"><span data-stu-id="d5f56-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="d5f56-117">Windows 10이 있는 경우 Windows 보안을 사용 하 여 최신 바이러스 백신 보호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-117">If you have Windows 10, you’ll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="d5f56-118">Windows 10을 처음 시작 하면 Windows 보안이 켜 지 며 맬웨어 (악의적인 소프트웨어), 바이러스 및 보안 위협을 검사 하 여 PC를 보호 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="d5f56-119">Windows 보안에서는 실시간 보호를 사용 하 여 PC에서 다운로드 하거나 실행 한 모든 항목을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="d5f56-120">Windows Update는 Windows 보안 업데이트를 자동으로 다운로드 하 여 PC를 안전 하 게 유지 하 고 위협 으로부터 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="d5f56-121">이전 버전의 Windows가 있고 Microsoft 보안 Essentials를 사용 하는 경우 Windows 보안으로 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it’s a good idea to move to Windows Security.</span></span> <span data-ttu-id="d5f56-122">자세한 내용은 [Windows 보안으로 내 장치 보호를](https://support.microsoft.com/en-us/help/17464/windows-10-help-protect-my-device-with-windows-security) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f56-122">See [help protect my device with Windows Security](https://support.microsoft.com/en-us/help/17464/windows-10-help-protect-my-device-with-windows-security) for more information.</span></span>

<span data-ttu-id="d5f56-123">**Windows 방화벽 설정**</span><span class="sxs-lookup"><span data-stu-id="d5f56-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="d5f56-124">다른 방화벽이 설정 된 경우에도 항상 Windows 방화벽을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="d5f56-125">Windows 방화벽을 끄면 장치 (및 네트워크)가 무단으로 액세스 하는 데 더 취약 해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="d5f56-126">지침은 [Windows 방화벽 켜기 또는 끄기](https://support.microsoft.com/en-us/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f56-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/en-us/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mactabmac"></a>[<span data-ttu-id="d5f56-127">Mac</span><span class="sxs-lookup"><span data-stu-id="d5f56-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="d5f56-128">**FileVault을 사용 하 여 Mac 디스크 암호화**</span><span class="sxs-lookup"><span data-stu-id="d5f56-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="d5f56-129">디스크 암호화는 장치를 분실 하거나 도난당 한 경우 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="d5f56-130">FileVault 전체 디스크 암호화는 시작 디스크의 정보에 대 한 무단 액세스를 방지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="d5f56-131">지침은 [FileVault을 사용 하 여 Mac에서 시동 디스크 암호화를](https://support.apple.com/HT204837) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f56-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="d5f56-132">**맬웨어 로부터 mac 보호**</span><span class="sxs-lookup"><span data-stu-id="d5f56-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="d5f56-133">Mac에서 신뢰할 수 있는 바이러스 백신 소프트웨어를 설치 하 고 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-133">Microsoft recommends you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="d5f56-134">선택 사항 목록은 다음 문서를 참조 하십시오 ( [최상의 Mac 바이러스 백신 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)).</span><span class="sxs-lookup"><span data-stu-id="d5f56-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="d5f56-135">신뢰할 수 있는 원본의 소프트웨어만 사용 하 여 맬웨어의 위험을 줄일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="d5f56-136">보안 & 개인 정보 기본 설정의 설정을 사용 하 여 Mac에 설치 된 소프트웨어의 출처를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="d5f56-137">자세한 내용은 [맬웨어 로부터 Mac 보호](https://support.apple.com/kb/PH25087) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f56-137">See [protect your Mac from malware](https://support.apple.com/kb/PH25087) for more information.</span></span>

<span data-ttu-id="d5f56-138">**방화벽 보호 설정**</span><span class="sxs-lookup"><span data-stu-id="d5f56-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="d5f56-139">방화벽 설정을 사용 하 여 인터넷 이나 네트워크에 연결 되어 있을 때 다른 컴퓨터가 시작한 원치 않는 대화 상대 로부터 Mac을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you’re connected to the Internet or a network.</span></span> <span data-ttu-id="d5f56-140">이 보호를 사용 하지 않으면 Mac이 무단으로 액세스 하는 데 더 취약 해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f56-140">Without this protection your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="d5f56-141">지침은 [응용 프로그램 방화벽 정보](https://support.apple.com/HT201642) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f56-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>

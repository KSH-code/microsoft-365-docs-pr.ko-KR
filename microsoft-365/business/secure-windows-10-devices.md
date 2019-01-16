---
title: Windows 10 장치 보안
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: '기본 및 Windows 10 장치 보호 하기 위해 다른 설정 하는 방법에 대 한 설명 합니다. '
ms.openlocfilehash: 0bdf6a56d880cb84f4a4f50550539d97c006ba49
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870277"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="07341-103">Windows 10 장치 보안</span><span class="sxs-lookup"><span data-stu-id="07341-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="07341-p101">여기서 구성하는 설정은 Windows 10의 기본 장치 정책에 해당합니다. Windows 10 장치(모바일 장치 및 PC 포함)에서 회사 계정으로 접속하는 모든 사용자에게는 이와 같은 설정이 자동으로 적용됩니다. 설치 중에 기본 정책을 수락하고 특정 사용자 그룹을 대상으로 하는 정책은 나중에 추가하는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="07341-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="07341-107">Windows 10 장치의 보안 설정</span><span class="sxs-lookup"><span data-stu-id="07341-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="07341-p102">모든 설정은 기본적으로 **켜짐**으로 되어 있습니다. 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07341-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="07341-110">설정</span><span class="sxs-lookup"><span data-stu-id="07341-110">Setting</span></span>  <br/> |<span data-ttu-id="07341-111">설명</span><span class="sxs-lookup"><span data-stu-id="07341-111">Description</span></span>  <br/> |
|<span data-ttu-id="07341-112">Windows Defender Antivirus를 사용하여 바이러스 및 기타 위협으로부터 PC를 보호하도록 지원</span><span class="sxs-lookup"><span data-stu-id="07341-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="07341-113">인터넷에 연결하여 발생할 수 있는 위험으로부터 PC를 보호하기 위해 Windows Defender Antivirus가 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07341-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="07341-114">Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호하도록 지원</span><span class="sxs-lookup"><span data-stu-id="07341-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="07341-115">Edge에서 사용자를 악성 사이트와 다운로드로부터 보호하는 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="07341-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="07341-116">이 시간 동안 유휴 상태일 때 장치 화면 끄기</span><span class="sxs-lookup"><span data-stu-id="07341-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="07341-p103">사용자가 유휴 상태일 때 회사 데이터가 안전하게 보호되도록 합니다. 사용자가 커피숍과 같은 공공장소에서 작업하다가 잠시 자리를 비우거나 다른 곳에 주의를 기울인 순간 장치가 타인의 시선에 노출될 수 있습니다. 이 설정은 사용자가 얼마 동안 유휴 상태이면 화면이 꺼지는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07341-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="07341-120">사용자가 Microsoft Store에서 앱을 다운로드할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="07341-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="07341-p104">사용자가 Microsoft Store에서 앱을 다운로드하여 설치할 수 있도록 허용합니다. 앱에는 게임에서 생산성 도구에 이르기까지 다양한 종류가 있습니다. 따라서 기본값은 **켜기**이지만 관리자가 보안을 위해 끌 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="07341-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="07341-123">사용자가 Cortana에 액세스할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="07341-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="07341-p105">Cortana는 매우 유용한 도구입니다. Cortana는 사용자 대신 설정을 끄거나 켜고, 길을 안내해 주고, 약속을 상기시켜 줍니다. 기본값은 **켜기**입니다.  </span><span class="sxs-lookup"><span data-stu-id="07341-p105">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="07341-126">사용자가 Microsoft에서 Windows 팁 및 광고를 받을 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="07341-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="07341-127">Windows 팁은 새로운 기능이 출시된 경우 사용자에게 이를 안내하는 등 매우 유용하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07341-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="07341-128">자동으로 Windows 10 장치를 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="07341-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="07341-129">Windows 10 장치가 자동으로 최신 상태로 업데이트되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="07341-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   


---
title: Windows 10 장치 보안
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 회사 또는 학교 계정에 로그인 할 때 Windows 10 장치에서 수신 하는 기본 장치 정책의 설정을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 85448507835b6310ca4136849be6a40caf6bb919
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289080"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="c66ac-103">Windows 10 장치 보안</span><span class="sxs-lookup"><span data-stu-id="c66ac-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="c66ac-104">이 문서는 Microsoft 365 Business Premium에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66ac-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="c66ac-105">여기서 구성하는 설정은 Windows 10의 기본 장치 정책에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c66ac-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="c66ac-106">모바일 장치 및 Pc를 포함 하 여 Windows 10 장치에 연결 하는 모든 사용자에 게는 해당 작업 계정으로 로그인 하 여 자동으로 이러한 설정이 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66ac-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="c66ac-107">설치 중에 기본 정책을 수락하고 특정 사용자 그룹을 대상으로 하는 정책은 나중에 추가하는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66ac-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="c66ac-108">Windows 10 장치의 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c66ac-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="c66ac-p102">모든 설정은 기본적으로 **켜짐**으로 되어 있습니다. 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66ac-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c66ac-111">설정</span><span class="sxs-lookup"><span data-stu-id="c66ac-111">Setting</span></span>  <br/> |<span data-ttu-id="c66ac-112">설명</span><span class="sxs-lookup"><span data-stu-id="c66ac-112">Description</span></span>  <br/> |
|<span data-ttu-id="c66ac-113">Windows Defender Antivirus를 사용하여 바이러스 및 기타 위협으로부터 PC를 보호하도록 지원</span><span class="sxs-lookup"><span data-stu-id="c66ac-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="c66ac-114">인터넷에 연결하여 발생할 수 있는 위험으로부터 PC를 보호하기 위해 Windows Defender Antivirus가 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66ac-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="c66ac-115">Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호하도록 지원</span><span class="sxs-lookup"><span data-stu-id="c66ac-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="c66ac-116">Edge에서 사용자를 악성 사이트와 다운로드로부터 보호하는 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="c66ac-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="c66ac-117">BitLocker를 사용하여 PC의 파일 및 폴더를 무단 액세스로부터 보호</span><span class="sxs-lookup"><span data-stu-id="c66ac-117">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="c66ac-118">Bitlocker는 컴퓨터 하드 드라이브를 암호화하여 데이터를 보호하고, 컴퓨터가 분실되거나 도난당한 경우 데이터 노출을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="c66ac-118">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="c66ac-119">자세한 내용은 [BITLOCKER FAQ](https://go.microsoft.com/fwlink/?linkid=871000)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c66ac-119">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="c66ac-120">이 시간 동안 유휴 상태일 때 장치 화면 끄기</span><span class="sxs-lookup"><span data-stu-id="c66ac-120">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="c66ac-p104">사용자가 유휴 상태일 때 회사 데이터가 안전하게 보호되도록 합니다. 사용자가 커피숍과 같은 공공장소에서 작업하다가 잠시 자리를 비우거나 다른 곳에 주의를 기울인 순간 장치가 타인들의 시선에 노출될 수 있습니다. 이 설정은 사용자가 얼마 동안 유휴 상태이면 화면이 꺼지는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c66ac-p104">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|
---
title: Windows 장치에서 Office 2013에 대해 최신 인증 사용
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: 2013이 설치된 장치에 대해 최신 인증을 사용하도록 레지스트리 Microsoft Office 방법을 학습합니다.
ms.openlocfilehash: f12511ad6d685647b3b38fd424f1d4611a3119b4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914537"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="e2af9-103">Windows 장치에서 Office 2013에 대해 최신 인증 사용</span><span class="sxs-lookup"><span data-stu-id="e2af9-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="e2af9-104">Office 2013이 설치되어 있는 Windows 장치에 대해 최신 인증을 사용하려면 특정 레지스트리 키를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="e2af9-105">Office 2013 클라이언트에 대해 최신 인증 사용</span><span class="sxs-lookup"><span data-stu-id="e2af9-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="e2af9-106">Office 2016 클라이언트에 대해 이미 최신 인증이 사용되고 있는 경우 Office 2016에 대해 레지스트리 키를 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="e2af9-p101">Microsoft Office 2013이 설치되었고 Windows를 실행 중인 장치(예: 노트북 및 태블릿)에 대해 최신 인증을 사용하려면 다음 레지스트리 키를 설정해야 합니다. 최신 인증을 사용할 각 장치에서 키를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="e2af9-109">**레지스트리 키**</span><span class="sxs-lookup"><span data-stu-id="e2af9-109">**Registry key**</span></span>|<span data-ttu-id="e2af9-110">**유형**</span><span class="sxs-lookup"><span data-stu-id="e2af9-110">**Type**</span></span>|<span data-ttu-id="e2af9-111">**값**</span><span class="sxs-lookup"><span data-stu-id="e2af9-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="e2af9-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="e2af9-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="e2af9-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="e2af9-113">REG_DWORD</span></span>  |<span data-ttu-id="e2af9-114">1</span><span class="sxs-lookup"><span data-stu-id="e2af9-114">1</span></span>  |
|<span data-ttu-id="e2af9-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="e2af9-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="e2af9-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="e2af9-116">REG_DWORD</span></span> |<span data-ttu-id="e2af9-117">1</span><span class="sxs-lookup"><span data-stu-id="e2af9-117">1</span></span> |
   
<span data-ttu-id="e2af9-118">레지스트리 키를 설정한 후 Office 2013 장치 앱이 Microsoft 365에서 [MFA(다단계](set-up-multi-factor-authentication.md) 인증)를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="e2af9-p102">현재 클라이언트 앱에 로그인한 경우 변경 내용을 적용하려면 로그아웃 후 다시 로그인해야 합니다. 그러지 않으면 ADAL ID가 설정될 때까지 MRU 및 로밍 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="e2af9-121">장치에서 최신 인증을 사용하지 않음</span><span class="sxs-lookup"><span data-stu-id="e2af9-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="e2af9-122">장치에서 최신 인증을 사용하지 않으려면 장치의 다음 레지스트리 키를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="e2af9-123">**레지스트리 키**</span><span class="sxs-lookup"><span data-stu-id="e2af9-123">**Registry key**</span></span>|<span data-ttu-id="e2af9-124">**유형**</span><span class="sxs-lookup"><span data-stu-id="e2af9-124">**Type**</span></span>|<span data-ttu-id="e2af9-125">**값**</span><span class="sxs-lookup"><span data-stu-id="e2af9-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="e2af9-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="e2af9-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="e2af9-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="e2af9-127">REG_DWORD</span></span>|<span data-ttu-id="e2af9-128">0</span><span class="sxs-lookup"><span data-stu-id="e2af9-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="e2af9-129">관련 문서</span><span class="sxs-lookup"><span data-stu-id="e2af9-129">Related articles</span></span>
[<span data-ttu-id="e2af9-130">두 번째 확인 방법으로 Office 2013에 로그인</span><span class="sxs-lookup"><span data-stu-id="e2af9-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[<span data-ttu-id="e2af9-131">Outlook에 암호를 입력하라는 메시지가 표시되어 최신 인증을 사용하여 Office 365에 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-131">Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365</span></span>](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)


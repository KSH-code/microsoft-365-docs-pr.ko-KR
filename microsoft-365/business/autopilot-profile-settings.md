---
title: AutoPilot 프로필 설정 정보
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 작업을 자동화할 프로필 사용자 장치에 Windows 가져옵니다 설치 하는 방법을 제어 하는데 도움이 됩니다. 프로필에 기본 포함과 설정 (옵션) Cortana 설치를 건너뜁니다.
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869745"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="ee062-104">AutoPilot 프로필 설정 정보</span><span class="sxs-lookup"><span data-stu-id="ee062-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="ee062-105">작업을 자동화할 프로필 설정</span><span class="sxs-lookup"><span data-stu-id="ee062-105">AutoPilot profile settings</span></span>

<span data-ttu-id="ee062-p102">사용자 장치에 작업을 자동화할 프로필을 사용 하 여 Windows 가져옵니다 설치 하는 방법을 제어할 수 있습니다. 프로필은 다음 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee062-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="ee062-108">**작업을 자동화할 기본 기능 (필수) 자동으로 설정 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="ee062-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="ee062-109">**설정**</span><span class="sxs-lookup"><span data-stu-id="ee062-109">**Setting**</span></span>|<span data-ttu-id="ee062-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="ee062-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee062-111">건너뛰기 Cortana, OneDrive 및 OEM 등록</span><span class="sxs-lookup"><span data-stu-id="ee062-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="ee062-p103">Cortana 및 개인 OneDrive와 같은 소비자 앱의 설치를 건너뜁니다. 장치 사용자가 자신이 장치에 로컬 관리자가 나중에 이러한 설치할 수 있습니다. 장치를 관리 하 여 Microsoft 365 비즈니스에서는 원래 제조업체 등록 건너뛴 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee062-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="ee062-115">회사 브랜드로 경험에 로그인</span><span class="sxs-lookup"><span data-stu-id="ee062-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="ee062-116">회사가 [Office 365 로그인 페이지에 추가 회사 브랜딩](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)하는 경우에 장치 사용자 로그인 할 때 해당 환경에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee062-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="ee062-117">MDM 자동 등록이 구성 된 AAD 계정 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee062-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="ee062-118">사용자 id를 관리 하 여 Azure Active directory를 여는 하 고 사용자가 자신의 Microsoft 365 비즈니스 자격 증명을 가진 Windows 및 Office 365에 로그인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee062-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="ee062-119">**설정 (옵션):**</span><span class="sxs-lookup"><span data-stu-id="ee062-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="ee062-120">**설정**</span><span class="sxs-lookup"><span data-stu-id="ee062-120">**Setting**</span></span>|<span data-ttu-id="ee062-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="ee062-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee062-122">개인정보 보호 설정을 건너뜁니다 (기본적으로 해제)</span><span class="sxs-lookup"><span data-stu-id="ee062-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="ee062-123">이 옵션을 **On**으로 설정 하는 경우가 자신이 처음 로그인 하면 장치 사용자는 장치 및 Windows에 대 한 사용권 계약을 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee062-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="ee062-124">사용자 로컬 관리자가 될 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee062-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="ee062-125">이 옵션을 **On**으로 설정 하는 경우 장치 사용자 Cortana와 같은 모든 개인 앱을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee062-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   

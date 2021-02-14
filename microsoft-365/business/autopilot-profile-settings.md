---
title: AutoPilot 프로필 설정 정보
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 프로필을 사용하면 Windows가 사용자 장치에 설치되는 방법을 제어할 수 있습니다. 프로필에는 Cortana 설치 건너뛰기 같은 기본 및 선택적 설정이 포함되어 있습니다.
ms.openlocfilehash: 100de5e9548f901008d3ae154ac5a237ef265ffb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401037"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="74b24-104">AutoPilot 프로필 설정 정보</span><span class="sxs-lookup"><span data-stu-id="74b24-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="74b24-105">AutoPilot 프로필 설정</span><span class="sxs-lookup"><span data-stu-id="74b24-105">AutoPilot profile settings</span></span>

<span data-ttu-id="74b24-106">AutoPilot 프로필을 사용하여 사용자 장치에 Windows가 설치되는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74b24-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="74b24-107">프로필에는 다음 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74b24-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="74b24-108">**자동 설정되는 AutoPilot 기본 기능(필수)**</span><span class="sxs-lookup"><span data-stu-id="74b24-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="74b24-109">**설정**</span><span class="sxs-lookup"><span data-stu-id="74b24-109">**Setting**</span></span>|<span data-ttu-id="74b24-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="74b24-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="74b24-111">Cortana, OneDrive 및 OEM 등록 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="74b24-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="74b24-112">Cortana 및 개인 OneDrive와 같은 소비자 앱의 설치를 건너뜁.</span><span class="sxs-lookup"><span data-stu-id="74b24-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="74b24-113">사용자가 디바이스의 로컬 관리자인 경우 나중에 이러한 장치를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74b24-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="74b24-114">디바이스는 Microsoft 365 Business Premium에서 관리하기 때문에 원래 제조업체 등록을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="74b24-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="74b24-115">회사 브랜드로 로그인 환경</span><span class="sxs-lookup"><span data-stu-id="74b24-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="74b24-116">회사에 Microsoft [365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page)로그인 페이지에 회사 브랜드 추가 페이지가 있는 경우 장치 사용자는 로그인할 때 해당 환경을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74b24-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="74b24-117">구성된 AAD 계정을 통해 MDM 자동 등록</span><span class="sxs-lookup"><span data-stu-id="74b24-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="74b24-118">사용자 ID는 Azure Active Directory에서 관리되고 사용자는 Microsoft 365 Business Premium 자격 증명을 사용하여 Windows 및 Microsoft 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="74b24-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="74b24-119">**선택적 설정:**</span><span class="sxs-lookup"><span data-stu-id="74b24-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="74b24-120">**설정**</span><span class="sxs-lookup"><span data-stu-id="74b24-120">**Setting**</span></span>|<span data-ttu-id="74b24-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="74b24-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="74b24-122">개인 정보 설정 건너뛰기(기본적으로 해제)</span><span class="sxs-lookup"><span data-stu-id="74b24-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="74b24-123">이 옵션을 **으로** 설정하면 장치 사용자가 처음 로그인할 때 장치 및 Windows에 대한 사용권 계약이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74b24-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="74b24-124">사용자가 로컬 관리자가 되기를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74b24-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="74b24-125">이 옵션을 **으로** 설정하면 디바이스 사용자가 Cortana와 같은 개인 앱을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74b24-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   

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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 프로필은 Windows가 사용자 장치에 설치 되는 방법을 제어 하는 데 도움이 됩니다. 이 프로필에는 Cortana 설치 건너뛰기와 같은 기본 설정과 선택적 설정이 포함 되어 있습니다.
ms.openlocfilehash: 5c2ec3f4c3e0ebc4ea545d11f819c897f414ad52
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627417"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="059de-104">AutoPilot 프로필 설정 정보</span><span class="sxs-lookup"><span data-stu-id="059de-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="059de-105">AutoPilot 프로필 설정</span><span class="sxs-lookup"><span data-stu-id="059de-105">AutoPilot profile settings</span></span>

<span data-ttu-id="059de-106">AutoPilot 프로필을 사용 하 여 사용자 장치에 Windows가 설치 되는 방식을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059de-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="059de-107">프로필에는 다음 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059de-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="059de-108">**자동으로 설정 되는 AutoPilot 기본 기능 (필수):**</span><span class="sxs-lookup"><span data-stu-id="059de-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="059de-109">**설정**</span><span class="sxs-lookup"><span data-stu-id="059de-109">**Setting**</span></span>|<span data-ttu-id="059de-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="059de-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="059de-111">Cortana, OneDrive 및 OEM 등록 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="059de-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="059de-112">Cortana 및 개인 OneDrive와 같은 소비자 앱의 설치를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="059de-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="059de-113">사용자가 장치에서 로컬 관리자 인 경우에는 장치 사용자가 나중에이를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059de-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="059de-114">장치가 Microsoft 365 Business Premium에서 관리 되므로 원래 제조업체 등록은 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="059de-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="059de-115">회사 브랜드의 로그인 환경</span><span class="sxs-lookup"><span data-stu-id="059de-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="059de-116">회사에서 [Microsoft 365 로그인 페이지에 회사 브랜딩 추가](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)를 사용 하는 경우 디바이스 사용자에 게 로그인 할 때 해당 환경이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059de-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="059de-117">구성 된 AAD 계정을 사용 하는 MDM 자동 등록</span><span class="sxs-lookup"><span data-stu-id="059de-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="059de-118">사용자 id는 Azure Active Directory에서 관리 되며, 사용자는 Microsoft 365 Business Premium 자격 증명을 사용 하 여 Windows 및 Microsoft 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="059de-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="059de-119">**선택적 설정:**</span><span class="sxs-lookup"><span data-stu-id="059de-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="059de-120">**설정**</span><span class="sxs-lookup"><span data-stu-id="059de-120">**Setting**</span></span>|<span data-ttu-id="059de-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="059de-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="059de-122">개인 정보 설정 건너뛰기 (기본적으로 해제)</span><span class="sxs-lookup"><span data-stu-id="059de-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="059de-123">이 옵션을 **On**으로 설정 하면 장치 사용자가 처음 로그인 할 때 장치 및 Windows에 대 한 사용권 계약을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="059de-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="059de-124">사용자가 로컬 관리자가 될 수 없음</span><span class="sxs-lookup"><span data-stu-id="059de-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="059de-125">이 옵션을 **On**으로 설정 하면 장치 사용자가 Cortana와 같은 개인 앱을 설치할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059de-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   

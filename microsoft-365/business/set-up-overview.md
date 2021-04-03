---
title: 설정 개요
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 등록에서 도메인 및 사용자 추가, 보안 정책 설정 등 Microsoft 365 Business Premium의 설정 단계를 자세히 알아보십시오.
ms.openlocfilehash: 749acbfdbde92ad97b09dc720c85dd850b76c9cf
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579937"
---
# <a name="overview-of-setup"></a><span data-ttu-id="67512-103">설정 개요</span><span class="sxs-lookup"><span data-stu-id="67512-103">Overview of setup</span></span>

<span data-ttu-id="67512-104">Microsoft 365 Business Premium 설정에 대한 짧은 비디오를 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="67512-104">Watch a short video about Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="67512-105">이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67512-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="67512-106">대부분의 설치 단계는 안내 설치에서 수행될 수 있지만 다른 옵션도 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67512-106">Most of the setup steps can be done in the guided setup, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="67512-107">1단계: 도메인 및 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="67512-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="67512-108">**[도메인을 추가합니다(등록하는](set-up.md#add-your-domain-to-personalize-sign-in)** 동안 도메인을 [구입한](sign-up.md)경우 이 단계는 이미 완료된 것입니다.)</span><span class="sxs-lookup"><span data-stu-id="67512-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

   - <span data-ttu-id="67512-109">**사용자를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="67512-109">**Add users**.</span></span> <span data-ttu-id="67512-110">다음 세 가지 방법으로 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67512-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="67512-111">안내 [설치에서 을(를) 설치합니다.](set-up.md#add-users-in-the-wizard)</span><span class="sxs-lookup"><span data-stu-id="67512-111">In the [guided setup](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="67512-112">디렉터리 동기화를 사용하여 [Azure AD Connect를](../enterprise/set-up-directory-synchronization.md) 사용하여 사용자를 추가합니다(프레미스 Active Directory가 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="67512-112">Use directory synchronization to [add users by using Azure AD Connect](../enterprise/set-up-directory-synchronization.md) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="67512-113">나중에 관리 [센터에서 사용자를](../admin/add-users/add-users.md) 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67512-113">You can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="67512-114">2단계: 보안 정책 설정 및 장치 구성</span><span class="sxs-lookup"><span data-stu-id="67512-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="67512-115">안내 [설치를 사용하여](set-up.md#protect-your-organization) 장치 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="67512-115">Use the [guided setup](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="67512-116">나중에 관리 센터 및 [Intune](/intune/tutorial-walkthrough-intune-portal)포털에서 추가하거나 편집할 수도 있습니다. [](view-policies-and-devices.md)</span><span class="sxs-lookup"><span data-stu-id="67512-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="67512-117">또한 설치 마법사는 기본 위협 방지 및 데이터 손실 방지 설정도 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="67512-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="67512-118">설치 마법사의 보안 설정 외에도 다음 설정을 추가하여 보안을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67512-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="67512-119">**전자 메일 맬웨어 보호**</span><span class="sxs-lookup"><span data-stu-id="67512-119">**Email malware protection**</span></span>
- <span data-ttu-id="67512-120">**Defender for Office 365의 피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="67512-120">**Anti-phishing in Defender for Office 365**</span></span>
- <span data-ttu-id="67512-121">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="67512-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="67512-122">**Azure Information Protection(계획1)**</span><span class="sxs-lookup"><span data-stu-id="67512-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="67512-123">시작을 위해 위협 [](increase-threat-protection.md) 방지 강화 및 준수 [기능 설정 을 참조합니다.](set-up-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="67512-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="67512-124">모범 보안 사례에 대한 로드맵을 확인하여 [Microsoft 365 Business Premium을](/office365/admin/security-and-compliance/secure-your-business-data) 보호하는 상위 10가지 방법도 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="67512-124">See also [top 10 ways to secure your Microsoft 365 Business Premium](/office365/admin/security-and-compliance/secure-your-business-data) for a road-map of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="67512-125">3단계: Windows 10 장치 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="67512-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="67512-126">안내 설치를 완료한 후 조직의 모든 Windows 10 컴퓨터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67512-126">After you complete the guided setup, you will want to protect all the Windows 10 computers in your organization.</span></span>
  
- <span data-ttu-id="67512-127">Windows 10 Pro는 Microsoft 365 Business Premium의 선행 필요합니다. 그러나 Windows 7 Pro, Windows 8 Pro 또는 Windows 8.1 Pro가 있는 경우 구독을 통해 [Windows 10 Pro로](./upgrade-to-windows-pro-creators-update.md)업그레이드할 수 있습니다. [](pre-requisites-for-data-protection.md)</span><span class="sxs-lookup"><span data-stu-id="67512-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business Premium, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).</span></span>
- <span data-ttu-id="67512-128">보안 Windows [10 PC의](secure-win-10-pcs.md) 단계에 따라 Windows 10 장치에 대한 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67512-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="67512-129">Windows 10 장치를 Azure AD에 가입하면 Windows 10 컴퓨터에 대해 설정한 정책이 해당 장치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67512-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="67512-130">자세한 내용은 Microsoft 365 사용자를 위한 Windows 장치 [설정 을 참조하세요.](set-up-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="67512-130">For more information, see [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-microsoft-365-apps-for-business"></a><span data-ttu-id="67512-131">4단계: 비즈니스용 Microsoft 365 앱 설치</span><span class="sxs-lookup"><span data-stu-id="67512-131">Step 4: Install Microsoft 365 Apps for business</span></span>
- <span data-ttu-id="67512-132">설치 마법사를 사용하여 Windows 장치에 Office를 자동으로 설치할 [수 있습니다.](set-up.md#deploy-office-365-client-apps)</span><span class="sxs-lookup"><span data-stu-id="67512-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="67512-133">사용자가 [Windows 및 디바이스용 Office](/office365/admin/setup/install-applications) 앱을 설치할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="67512-133">Let users [install Office apps](/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="67512-134">고급</span><span class="sxs-lookup"><span data-stu-id="67512-134">Advanced</span></span>
- <span data-ttu-id="67512-135">**Autopilot을 사용하여 새 장치 설정**</span><span class="sxs-lookup"><span data-stu-id="67512-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="67512-136">[Windows Autopilot을](add-autopilot-devices-and-profile.md) 사용하여 사용자를 위해 새 **Windows** 10 장치를 자동으로 미리 구성할 [](https://www.microsoft.com/solution-providers/search) 수 있지만 이 작업을 할 수 있는 파트너를 추가하는 것이 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="67512-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="67512-137">[Microsoft](https://go.microsoft.com/fwlink/?linkid=874598)Store로 이동하여 클라우드 기술 전문가에게 구매한 새 디바이스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67512-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="67512-138">**온-프레미스 리소스 액세스**</span><span class="sxs-lookup"><span data-stu-id="67512-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="67512-139">조직에서 Windows Server Active Directory를 사용하는 경우 Microsoft 365 Business Premium을 설정하여 Windows 10 장치를 보호하는 동시에 로컬 인증이 필요한 사내 리소스에 대한 액세스는 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="67512-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="67512-140">도메인에 가입된 [Windows 10 장치를 Microsoft 365 Business Premium에서](manage-windows-devices.md) 관리하도록 설정의 단계에 따라 이 설정을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="67512-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="67512-141">이 방법이 기본 설정 방법으로, 이 상태의 장치를 하이브리드 Azure AD 가입 장치라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67512-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="67512-142">비즈니스에 일부 사내 리소스(예: 파일 공유 및 프린터)가 포함된 로컬 Active Directory가 있는 경우 [Microsoft 365 Business Premium의 Azure AD](access-resources.md)가입 장치에서의 On-premises resources에 액세스의 단계에 따라 Azure AD 가입 장치에 이러한 리소스에 대한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67512-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="67512-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67512-143">See also</span></span>

[<span data-ttu-id="67512-144">Microsoft 365 Business 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="67512-144">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
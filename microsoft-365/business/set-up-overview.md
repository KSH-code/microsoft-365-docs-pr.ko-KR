---
title: 설정 개요
ms.author: sirkkuw
author: Sirkkuw
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business에 대 한 설정 단계 개요입니다.
ms.openlocfilehash: 4be0a8aa1b050ee3e20a045eb2c07666765118ed
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37440540"
---
# <a name="overview-of-setup"></a><span data-ttu-id="355f9-103">설치 개요</span><span class="sxs-lookup"><span data-stu-id="355f9-103">Overview of setup</span></span>

<span data-ttu-id="355f9-104">설정 단계 대부분은 설치 마법사에서 수행할 수 있지만 다른 옵션도 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-104">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>


## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="355f9-105">1 단계: 도메인 및 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="355f9-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="355f9-106">**[도메인 추가](set-up.md#add-your-domain-to-personalize-sign-in)** ( [등록](sign-up.md)중에 도메인을 구매한 경우이 단계는 이미 완료 됨)</span><span class="sxs-lookup"><span data-stu-id="355f9-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="355f9-107">**사용자를 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-107">**Add users**.</span></span> <span data-ttu-id="355f9-108">다음 세 가지 방법 중 하나를 통해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-108">You can do this in any of the three ways:</span></span>
        - <span data-ttu-id="355f9-109">[마법사](set-up.md#add-users-in-the-wizard)에서</span><span class="sxs-lookup"><span data-stu-id="355f9-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="355f9-110">온-프레미스 Active directory가 있는 경우 디렉터리 동기화를 사용 하 여 [AZURE AD Connect를 사용 하 여 사용자를 추가](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) 합니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="355f9-111">나중에 관리 센터에서 [사용자를 추가할](add-users-m365b.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="355f9-112">2 단계: 보안 정책 설정 및 장치 구성</span><span class="sxs-lookup"><span data-stu-id="355f9-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="355f9-113">[설치 마법사](set-up.md#protect-data-and-devices) 를 사용 하 여 장치 및 보안 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-113">Use the [Setup wizard](set-up.md#protect-data-and-devices) to configure device and security policies.</span></span> 
  - <span data-ttu-id="355f9-114">[관리 센터](view-policies-and-devices.md) 및 [Intune 포털](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)에서 나중에 추가 하거나 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="355f9-115">설치 마법사의 보안 설정 외에도 다음 설정을 추가 하 여 보안을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="355f9-116">**전자 메일 맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="355f9-116">**Email malware protection**</span></span>
      - <span data-ttu-id="355f9-117">**ATP (Advanced Threat Protection) 안전한 링크**</span><span class="sxs-lookup"><span data-stu-id="355f9-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="355f9-118">**ATP 안전한 첨부 파일**</span><span class="sxs-lookup"><span data-stu-id="355f9-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="355f9-119">**ATP 피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="355f9-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="355f9-120">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="355f9-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="355f9-121">**Data Loss Prevention (DLP)**</span><span class="sxs-lookup"><span data-stu-id="355f9-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="355f9-122">**Azure Information Protection (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="355f9-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="355f9-123">시작 하려면 [고급 보안 정책을 설정](set-up-advanced-security.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="355f9-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="355f9-124">모범 보안 관행 로드맵에 대해서는 [Microsoft 365 Business의 보안을 위한 상위 10 가지 방법](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) 도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="355f9-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="355f9-125">3 단계: Windows 10 장치 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="355f9-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="355f9-126">Windows 10 장치를 Azure AD에 가입 하면 [2 단계](#step-2-set-up-security-policies-and-configure-devices) 에서 설정한 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="355f9-127">Windows 10 Pro는 Microsoft 365 Business에 대 한 [필수](pre-requisites-for-data-protection.md) 구성 요소 지만, Windows 7 Pro, Windows 8 Pro 또는 Windows 8.1 pro가 있는 경우 구독을 통해 [windows 10 Pro로 업그레이드할](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-127">Windows 10 Pro is a [pre-requisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="355f9-128">[설치 마법사](set-up.md#protect-data-and-devices) 를 사용 하 여 Windows 10 장치에 대 한 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-128">Use the [Setup wizard](set-up.md#protect-data-and-devices) to configure policies for Windows 10 devices.</span></span>

## <a name="stes-4-install-office-365-business"></a><span data-ttu-id="355f9-129">Stes 4: Office 365 Business 설치</span><span class="sxs-lookup"><span data-stu-id="355f9-129">Stes 4: Install Office 365 Business</span></span>
- <span data-ttu-id="355f9-130">[설치 마법사](set-up.md#deploy-office-365-client-apps)를 사용 하 여 Windows 장치에 Office를 자동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="355f9-131">관리 센터에서 Office를 자동으로 [설치](auto-install-or-uninstall-office.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-131">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
- <span data-ttu-id="355f9-132">사용자가 Windows 및 장치용 [Office 앱을 설치할](https://docs.microsoft.com/office365/admin/setup/install-applications) 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-132">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="355f9-133">고급</span><span class="sxs-lookup"><span data-stu-id="355f9-133">Advanced</span></span>
- <span data-ttu-id="355f9-134">**Autopilot을 사용 하 여 새 장치 설정**</span><span class="sxs-lookup"><span data-stu-id="355f9-134">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="355f9-135">[Windows Autopilot](add-autopilot-devices-and-profile.md) 를 사용 하 여 사용자에 대해 **새** Windows 10 장치를 자동으로 미리 구성할 수 있지만,이 작업을 대신 수행할 수 있는 [파트너](https://www.microsoft.com/solution-providers/search) 를 가져오는 것이 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-135">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="355f9-136">[Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) 로 이동 하 여 클라우드 기술 전문가가 사용자를 위해 구입한 새 장치를 설정 하 게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-136">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

- <span data-ttu-id="355f9-137">**온-프레미스 리소스 액세스**</span><span class="sxs-lookup"><span data-stu-id="355f9-137">**Access on-premises resources**</span></span>

     - <span data-ttu-id="355f9-138">조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business를 설정 하 여 Windows 10 장치를 보호 하 되, 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-138">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="355f9-139">이를 설정 하려면 [도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정](manage-windows-devices.md) 의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-139">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="355f9-140">이 상태에서 기본 설정 방법 및 장치를 하이브리드 Azure AD 가입 장치 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-140">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="355f9-141">회사에 일부 온-프레미스 리소스 (예: 파일 공유 및 프린터)가 포함 된 로컬 Active Directory가 있는 경우 여기에 나와 있는 단계에 따라 Azure AD 조인 장치에 이러한 리소스에 대 한 액세스 권한을 부여할 수 [있습니다. Azure AD-가입 된 장치 (Microsoft 365 Business)](access-resources.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="355f9-141">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  
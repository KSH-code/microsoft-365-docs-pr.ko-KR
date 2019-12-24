---
title: 설치 개요
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business의 설치 단계에 대 한 개요입니다.
ms.openlocfilehash: 4aca617015cceb85ca35c8d8ada7b83d1416d959
ms.sourcegitcommit: 178ecb21cacdeaf440f3df2fe6e539e9127fcf15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2019
ms.locfileid: "40850807"
---
# <a name="overview-of-setup"></a><span data-ttu-id="393ef-103">설치 개요</span><span class="sxs-lookup"><span data-stu-id="393ef-103">Overview of setup</span></span>

<span data-ttu-id="393ef-104">Microsoft 365 Business setup에 대 한 간단한 비디오를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="393ef-104">Watch a short video about Microsoft 365 Business setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="393ef-105">이 비디오를 통해 도움이 되는 경우에는 [소규모 기업을 위한 전체 교육 시리즈 및 Microsoft 365에 새로 소개 하](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="393ef-106">대부분의 설치 단계는 설치 마법사에서 수행할 수 있지만 다른 옵션도 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-106">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="393ef-107">1 단계: 도메인 및 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="393ef-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="393ef-108">**[도메인 추가](set-up.md#add-your-domain-to-personalize-sign-in)** ( [등록](sign-up.md)중에 도메인을 구매한 경우이 단계는 이미 완료 됨)</span><span class="sxs-lookup"><span data-stu-id="393ef-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="393ef-109">**사용자를 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-109">**Add users**.</span></span> <span data-ttu-id="393ef-110">다음 세 가지 방법 중 하나를 통해 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="393ef-111">[마법사](set-up.md#add-users-in-the-wizard)에서</span><span class="sxs-lookup"><span data-stu-id="393ef-111">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="393ef-112">온-프레미스 Active directory가 있는 경우 디렉터리 동기화를 사용 하 여 [AZURE AD Connect를 사용 하 여 사용자를 추가](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) 합니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-112">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="393ef-113">나중에 관리 센터에서 [사용자를 추가할](add-users-m365b.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="393ef-114">2 단계: 보안 정책 설정 및 장치 구성</span><span class="sxs-lookup"><span data-stu-id="393ef-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="393ef-115">[설치 마법사](set-up.md#protect-your-organization) 를 사용 하 여 장치 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-115">Use the [Setup wizard](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="393ef-116">[관리 센터](view-policies-and-devices.md) 및 [Intune 포털](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)에서 나중에 추가 하거나 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="393ef-117">또한 설정 마법사는 기본 위협 보호 및 데이터 손실 방지 설정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="393ef-118">설치 마법사의 보안 설정 외에도 다음 설정을 추가 하 여 보안을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="393ef-119">**전자 메일 맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="393ef-119">**Email malware protection**</span></span>
- <span data-ttu-id="393ef-120">**ATP 피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="393ef-120">**ATP anti-phishing**</span></span>
- <span data-ttu-id="393ef-121">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="393ef-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="393ef-122">**Azure Information Protection (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="393ef-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="393ef-123">시작 하려면 [고급 보안 정책 설정을](set-up-advanced-security.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393ef-123">To get started, see [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="393ef-124">모범 보안 관행 로드맵에 대해서는 [Microsoft 365 Business의 보안을 위한 상위 10 가지 방법](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) 도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393ef-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="393ef-125">3 단계: Windows 10 장치 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="393ef-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="393ef-126">설정 마법사를 실행 한 후에는 조직의 모든 Windwos 10 컴퓨터를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-126">After you run the set up wizard, you will want to proctect all the Windwos 10 computers in your organization.</span></span>
  
- <span data-ttu-id="393ef-127">Windows 10 Pro는 Microsoft 365 Business에 대 한 [필수 구성 요소](pre-requisites-for-data-protection.md) 지만, Windows 7 Pro, Windows 8 Pro 또는 Windows 8.1 pro가 있는 경우 구독을 통해 [windows 10 Pro로 업그레이드할](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="393ef-128">Windows 10 용 정책 정책을 설정 하는 windows 10 [pc 보안](secure-win-10-pcs.md) 의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="393ef-129">Windows 10 장치를 Azure AD에 가입 하면 Windows 10 컴퓨터에 대해 설정한 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="393ef-130">자세한 내용은 [Set Up Windows devices For Microsoft 365 Business users](set-up-windows-devices.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393ef-130">For more information, see [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-office-365-business"></a><span data-ttu-id="393ef-131">4 단계: Office 365 Business 설치</span><span class="sxs-lookup"><span data-stu-id="393ef-131">Step 4: Install Office 365 Business</span></span>
- <span data-ttu-id="393ef-132">[설치 마법사](set-up.md#deploy-office-365-client-apps)를 사용 하 여 Windows 장치에 Office를 자동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="393ef-133">사용자가 Windows 및 장치용 [Office 앱을 설치할](https://docs.microsoft.com/office365/admin/setup/install-applications) 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-133">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="393ef-134">고급</span><span class="sxs-lookup"><span data-stu-id="393ef-134">Advanced</span></span>
- <span data-ttu-id="393ef-135">**Autopilot을 사용 하 여 새 장치 설정**</span><span class="sxs-lookup"><span data-stu-id="393ef-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="393ef-136">[Windows Autopilot](add-autopilot-devices-and-profile.md) 를 사용 하 여 사용자에 대해 **새** Windows 10 장치를 자동으로 미리 구성할 수 있지만,이 작업을 대신 수행할 수 있는 [파트너](https://www.microsoft.com/solution-providers/search) 를 가져오는 것이 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="393ef-137">[Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)로 이동한 후 클라우드 기술 전문가에 게 구매한 새 장치를 설치 하도록 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="393ef-138">**온-프레미스 리소스 액세스**</span><span class="sxs-lookup"><span data-stu-id="393ef-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="393ef-139">조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business를 설정 하 여 Windows 10 장치를 보호 하 되, 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="393ef-140">이를 설정 하려면 [도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정](manage-windows-devices.md) 의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="393ef-141">이는 기본 설정 방법 이며,이 상태에 있는 장치를 하이브리드 Azure AD 가입 장치 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="393ef-142">회사에 일부 온-프레미스 리소스 (예: 파일 공유 및 프린터)가 포함 된 로컬 Active Directory가 있는 경우 Azure ad 가입 장치에서 [Microsoft 365 business의 AZURE ad 조인 장치 로부터 온-프레미스 리소스에 액세스](access-resources.md)하 여 이러한 리소스에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393ef-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="393ef-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="393ef-143">See also</span></span>

[<span data-ttu-id="393ef-144">Microsoft 365 Business 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="393ef-144">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)

---
title: 비즈니스용 Windows 10 통해 도메인에 가입된 Microsoft 365 장치를 관리하도록 설정
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 몇 단계만 Microsoft 365 Active-Directory에 가입된 Windows 10 보호할 수 있도록 설정하는 방법을 알아보십시오.
ms.openlocfilehash: f16962dd3c33c3c228da507bc5c4a902d76a8a08
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593896"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="0dd46-103">도메인에 가입된 Windows 10 장치를 관리하도록 Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="0dd46-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="0dd46-104">조직에서 Windows Server Active Directory Windows 사용하는 경우 로컬 인증이 필요한 Windows 10 리소스에 대한 액세스는 유지 관리하면서 Microsoft 365 Business Premium 장치를 보호하도록 Windows 10 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="0dd46-105">이 보호를 설정하기 위해 하이브리드 Azure AD 가입 장치를 **구현할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0dd46-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="0dd46-106">이러한 디바이스는 사용자 장치와 사용자 프레미스 Active Directory 모두에 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0dd46-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="0dd46-107">이 비디오에서는 가장 일반적인 시나리오에 대해 이 설정 방법을 설정하는 단계에 대해 설명합니다. 또한 다음 단계에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="0dd46-108">시작하기 전에 다음 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="0dd46-109">사용자를 Azure AD와 Azure AD 커넥트.</span><span class="sxs-lookup"><span data-stu-id="0dd46-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="0dd46-110">Azure AD 커넥트 OU(조직 구성 단위) 동기화를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="0dd46-111">동기화하는 모든 도메인 사용자에게 동기화할 라이선스가 있는지 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0dd46-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="0dd46-112">단계는 [도메인 사용자를 Microsoft에 동기화를](manage-domain-users.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0dd46-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="0dd46-113">1. Intune에서 MDM 기관 확인</span><span class="sxs-lookup"><span data-stu-id="0dd46-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="0dd46-114">Endpoint Manager [](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) 이동하고 Microsoft Intune 페이지에서 장치 등록을 선택한 다음 개요 페이지에서 **MDM** 기관이  **Intune** 인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="0dd46-115">**MDM 기관이** **없음인** 경우 **MDM** 기관을 클릭하여 **Intune으로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="0dd46-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="0dd46-116">**MDM** 기관이 Microsoft Office 365 장치 등록 장치로 이동한 후 오른쪽의 MDM 기관 추가 대화 상자를 사용하여  >   **Intune MDM** 기관을 추가합니다(MDM 기관 추가 대화 상자는  **MDM** 기관이  Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="0dd46-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="0dd46-117">2. Azure AD가 컴퓨터에 가입할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0dd46-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="0dd46-118">관리 센터 목록에서 관리 센터로 이동하고 Azure Active Directory (Azure Active Directory 표시되지 않는 경우 모두 표시 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **선택)를** 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="0dd46-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="0dd46-119">in the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span><span class="sxs-lookup"><span data-stu-id="0dd46-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="0dd46-120">사용자가 **장치를 Azure AD에 가입할** 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0dd46-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="0dd46-121">모든 사용자를 사용하도록 설정하려면 모두 로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="0dd46-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="0dd46-122">특정 사용자를 사용하도록 설정하려면 특정 사용자 그룹을 사용하도록 설정하려면 **선택으로** 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="0dd46-123">Azure AD에서 동기화된 원하는 도메인 사용자를 보안 그룹에 [추가합니다.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="0dd46-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="0dd46-124">그룹 **선택을** 선택하여 해당 보안 그룹에 대해 MDM 사용자 범위를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="0dd46-125">3. Azure AD가 MDM에 대해 사용하도록 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0dd46-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="0dd46-126">에서 관리 센터로 이동하고 Endpoint Managemen t(표시가 표시되지 않는 경우 모두 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Endpoint Manager** 선택)를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="0dd46-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="0dd46-127">Microsoft Endpoint Manager **관리** 센터에서 장치 **Windows**  >    >  **Windows**  >  **등록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="0dd46-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="0dd46-128">MDM 사용자 범위가 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="0dd46-129">모든 컴퓨터를 등록하려면  사용자가 작업 계정을 추가할 때 Azure AD에 가입된 모든 사용자 컴퓨터와 새 컴퓨터를 자동으로 등록하려면 모두로 Windows.</span><span class="sxs-lookup"><span data-stu-id="0dd46-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="0dd46-130">특정 사용자 **그룹의** 컴퓨터를 등록하도록 일부로 설정</span><span class="sxs-lookup"><span data-stu-id="0dd46-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="0dd46-131">Azure AD에서 동기화된 원하는 도메인 사용자를 보안 그룹에 [추가합니다.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="0dd46-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="0dd46-132">그룹 **선택을** 선택하여 해당 보안 그룹에 대해 MDM 사용자 범위를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="0dd46-133">4. 필요한 리소스 만들기</span><span class="sxs-lookup"><span data-stu-id="0dd46-133">4. Create the required resources</span></span> 

<span data-ttu-id="0dd46-134">하이브리드 [Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) 조인을 구성하는 데 필요한 작업을 수행하는 작업은 [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 모듈에 있는 [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet을 사용하여 간소화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-134">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="0dd46-135">이 cmdlet을 호출하면 필요한 서비스 연결 지점 및 그룹 정책이 만들어지며 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="0dd46-136">PowerShell 인스턴스에서 다음을 호출하여 이 모듈을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="0dd46-137">Azure AD 서버를 실행하는 Windows 서버에 이 모듈을 설치하는 커넥트.</span><span class="sxs-lookup"><span data-stu-id="0dd46-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="0dd46-138">필요한 서비스 연결 지점 및 그룹 정책을 만들기 위해  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="0dd46-139">이 작업을 수행할 Microsoft 365 Business Premium 전역 관리자 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="0dd46-140">리소스를 만들 준비가 되면 다음을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="0dd46-141">첫 번째 명령은 Microsoft 클라우드와 연결을 설정하고 메시지가 표시될 때 전역 관리자 자격 Microsoft 365 Business Premium 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="0dd46-142">5. 그룹 정책 연결</span><span class="sxs-lookup"><span data-stu-id="0dd46-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="0dd46-143">GPMC(그룹 정책 관리 콘솔)에서 정책을 연결하려는 위치를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 기존 *GPO 연결...을* 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="0dd46-144">위 단계에서 만든 정책을 선택한 다음 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0dd46-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="0dd46-145">최신 관리 템플릿 다운로드</span><span class="sxs-lookup"><span data-stu-id="0dd46-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="0dd46-146">기본 Azure AD 자격 증명을 사용하여 자동 **MDM** 등록 사용 정책이 표시되지 않는 경우, Windows 10 버전 1803 이상에 대해 ADMX가 설치되지 않은 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="0dd46-147">이 문제를 해결하기 위해 다음 단계를 수행합니다(참고: 최신 MDM.admx는 역과 호환됨).</span><span class="sxs-lookup"><span data-stu-id="0dd46-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="0dd46-148">다운로드: [2020년 10월 업데이트(Windows 10)에 대한 관리 템플릿(.admx)입니다.](https://www.microsoft.com/download/102157)</span><span class="sxs-lookup"><span data-stu-id="0dd46-148">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="0dd46-149">도메인 컨트롤러에 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-149">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="0dd46-150">관리 템플릿 버전에 따라 **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 2020 Update (20H2)** 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-150">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="0dd46-151">위의 경로에 있는 **정책** 정의 폴더의 이름을 **PolicyDefinitions로 다시 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="0dd46-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="0dd46-152">기본적으로 **C:\Windows\SYSVOL\domain\Policies에** 있는 **PolicyDefinitions** 폴더를 SYSVOL 공유에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-152">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="0dd46-153">전체 도메인에 대해 중앙 정책 저장소를 사용하려면 PolicyDefinitions의 콘텐츠를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="0dd46-154">도메인 컨트롤러가 여러 개 있는 경우 정책을 사용할 수 있도록 SYSVOL이 복제될 때까지 기다렸다가</span><span class="sxs-lookup"><span data-stu-id="0dd46-154">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="0dd46-155">이 절차는 향후 버전의 관리 템플릿도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-155">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="0dd46-156">이제 사용 가능한 기본 Azure AD 자격 증명을 사용하여 자동 **MDM** 등록 사용 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd46-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

## <a name="related-content"></a><span data-ttu-id="0dd46-157">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="0dd46-157">Related content</span></span>

<span data-ttu-id="0dd46-158">[도메인 사용자를 도메인 사용자와](manage-domain-users.md) Microsoft 365 동기화(문서)</span><span class="sxs-lookup"><span data-stu-id="0dd46-158">[Synchronize domain users to Microsoft 365](manage-domain-users.md) (article)</span></span>

<span data-ttu-id="0dd46-159">[관리 센터에서](../admin/create-groups/create-groups.md) 그룹 만들기(문서)</span><span class="sxs-lookup"><span data-stu-id="0dd46-159">[Create a group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>

<span data-ttu-id="0dd46-160">[자습서: 관리되는 도메인에 Azure Active Directory 하이브리드](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) 연결 구성(문서)</span><span class="sxs-lookup"><span data-stu-id="0dd46-160">[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span></span>
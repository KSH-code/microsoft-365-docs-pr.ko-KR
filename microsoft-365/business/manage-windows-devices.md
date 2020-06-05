---
title: 비즈니스를 위해 Microsoft 365에서 관리할 도메인에 가입 된 Windows 10 장치를 사용 하도록 설정
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Microsoft 365에서 일부 단계만 수행 하 여 Active Directory에 가입 된 로컬 Windows 10 장치를 보호 하도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564952"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="c15f4-103">Microsoft 365 Business Premium에서 관리할 도메인에 가입 된 Windows 10 장치를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c15f4-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="c15f4-104">조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business Premium을 설정 하 여 Windows 10 장치를 보호 하 고 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="c15f4-105">이 보호를 설정 하기 위해 **하이브리드 AZURE AD에 가입 된 장치**를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="c15f4-106">이러한 장치는 온-프레미스 Active Directory 및 Azure Active Directory에 모두 가입 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="c15f4-107">이 비디오에서는 다음 단계에서 자세히 설명 되는 가장 일반적인 시나리오에 대해이 설정을 구성 하는 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="c15f4-108">시작 하기 전에 다음 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="c15f4-109">Azure AD Connect를 사용 하 여 Azure AD에 사용자를 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="c15f4-110">Azure AD Connect OU (조직 구성 단위) 동기화를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="c15f4-111">동기화 한 모든 도메인 사용자에 게 Microsoft 365 Business Premium에 대 한 라이선스가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="c15f4-112">단계를 보려면 [도메인 사용자를 Microsoft에 동기화를](manage-domain-users.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c15f4-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="c15f4-113">1. Intune에서 MDM 기관 확인</span><span class="sxs-lookup"><span data-stu-id="c15f4-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="c15f4-114">Portal.azure.com로 이동 하 여 Intune 페이지 검색을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="c15f4-115">Microsoft Intune 페이지에서 **장치 등록** 을 선택 하 고 **개요** 페이지에서 **MDM 기관이** **Intune**인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="c15f4-116">**Mdm 기관이** **없는 경우** **Mdm 기관을** 클릭 하 여 **Intune**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="c15f4-117">**MDM 기관이** **Microsoft office 365**인 경우 **장치**  >  **등록 장치** 를 열고 오른쪽에 있는 **mdm 인증** 추가 대화 상자를 사용 하 여 **Intune mdm** 기관을 추가 합니다 (mdm 기관이 Microsoft Office 365로 설정 된 경우 **MDM Authority** 에만 **mdm 기관 추가** 대화 상자를 사용할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="c15f4-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="c15f4-118">2. Azure AD가 컴퓨터 가입에 사용 되도록 설정 되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c15f4-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="c15f4-119">관리 센터에서를 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 선택 하 고 **Azure active Directory** (azure active directory가 표시 되지 않는 경우에는 모든 경우를 선택 하세요.)를 **관리** 센터 목록에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="c15f4-120">**Azure Active directory 관리 센터**에서 **azure active directory** 로 이동 하 여 **장치** 를 선택한 다음 **장치 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="c15f4-121">**사용자가 AZURE AD에 장치를 연결할 수** 있는지 확인 설정</span><span class="sxs-lookup"><span data-stu-id="c15f4-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="c15f4-122">모든 사용자를 설정 하려면 **모두**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="c15f4-123">특정 사용자를 사용 하도록 설정 하려면 특정 사용자 그룹을 사용 하도록 **선택** 된로 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="c15f4-124">Azure AD에서 동기화 되는 원하는 도메인 사용자를 [보안 그룹](../admin/create-groups/create-groups.md)에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="c15f4-125">**그룹 선택을** 선택 하 여 해당 보안 그룹에 대 한 MDM 사용자 범위를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="c15f4-126">3. MDM에 대해 Azure AD가 사용 되도록 설정 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="c15f4-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="c15f4-127">관리 센터로 이동한 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 후 **끝점 Managemen**t 선택 ( **endpoint Manager** 가 표시 되지 않는 경우 **모두 표시** 선택)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="c15f4-128">**Microsoft Endpoint Manager 관리 센터**에서 **장치**  >  **windows**  >  **windows 등록**  >  **자동 등록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="c15f4-129">MDM 사용자 범위가 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="c15f4-130">모든 컴퓨터를 등록 하려면 사용자가 Windows에 작업 계정을 추가할 때 Azure AD 및 새 컴퓨터에 연결 된 모든 사용자 컴퓨터를 자동으로 등록 하도록 **all** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="c15f4-131">특정 사용자 그룹의 컴퓨터를 등록 하려면 **Some** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="c15f4-132">Azure AD에서 동기화 되는 원하는 도메인 사용자를 [보안 그룹](../admin/create-groups/create-groups.md)에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="c15f4-133">**그룹 선택을** 선택 하 여 해당 보안 그룹에 대 한 MDM 사용자 범위를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="c15f4-134">4. SCP (서비스 연결 지점) 설정</span><span class="sxs-lookup"><span data-stu-id="c15f4-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="c15f4-135">이러한 단계는 [하이브리드 AZURE AD 조인 구성](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)에서 간소화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="c15f4-136">Azure AD Connect와 Microsoft 365 Business Premium 전역 관리자 및 Active Directory 관리자 암호를 사용 하는 데 필요한 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="c15f4-137">Azure AD Connect를 시작한 다음 **구성을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="c15f4-138">**추가 작업** 페이지에서 **장치 옵션 구성을**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="c15f4-139">**개요** 페이지에서 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="c15f4-140">**AZURE AD에 연결** 페이지에서 Microsoft 365 Business Premium에 대 한 전역 관리자의 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="c15f4-141">**장치 옵션** 페이지에서 **하이브리드 Azure AD 조인 구성을**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="c15f4-142">**Scp** 페이지에서 Azure AD CONNECT가 scp를 구성 하도록 하려는 각 포리스트에 대해 다음 단계를 완료 하 **고 다음을 선택 합니다**.</span><span class="sxs-lookup"><span data-stu-id="c15f4-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="c15f4-143">포리스트 이름 옆의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-143">Check the box beside the forest name.</span></span> <span data-ttu-id="c15f4-144">포리스트는 AD 도메인 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="c15f4-145">**인증 서비스** 열에서 드롭다운을 열고 일치 하는 도메인 이름을 선택 합니다 (하나만 옵션 하나만 있어야 함).</span><span class="sxs-lookup"><span data-stu-id="c15f4-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="c15f4-146">**추가** 를 선택 하 여 도메인 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="c15f4-147">**장치 운영** 체제 페이지에서 Windows 10 이상 도메인 가입 장치만을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="c15f4-148">**구성 준비 완료** 페이지에서 **구성을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="c15f4-149">**구성 완료** 페이지에서 **끝내기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="c15f4-150">5. Intune 등록을 위한 GPO 만들기 – ADMX 메서드</span><span class="sxs-lookup"><span data-stu-id="c15f4-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="c15f4-151">하십시오. ADMX 서식 파일</span><span class="sxs-lookup"><span data-stu-id="c15f4-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="c15f4-152">AD server에 로그온 하 고 **서버 관리자**  >  **도구**  >  **그룹 정책 관리**를 검색 하 고 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="c15f4-153">**Domains** (도메인)에서 도메인 이름을 선택 하 고 **그룹 정책 개체** 를 마우스 오른쪽 단추로 클릭 하 여 **새로 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="c15f4-154">새 GPO 이름 (예: "*Cloud_Enrollment*")을 지정 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="c15f4-155">**그룹 정책 개체** 아래의 새 GPO를 마우스 오른쪽 단추로 클릭 하 고 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="c15f4-156">**그룹 정책 관리 편집기**에서 **컴퓨터 구성**  >  **정책**  >  **관리 템플릿**  >  **Windows 구성 요소**  >  **MDM**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="c15f4-157">**기본 Azure AD 자격 증명을 사용 하 여 자동 MDM 등록 사용** 을 마우스 오른쪽 단추로 클릭 한 다음 확인 **사용**을 선택  >  **OK**합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="c15f4-158">편집기 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c15f4-159">**기본 AZURE AD 자격 증명을 사용 하 여 자동 MDM 등록**정책이 표시 되지 않는 경우 [에는 최신 관리 템플릿 가져오기를](#get-the-latest-administrative-templates)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c15f4-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="c15f4-160">6. 그룹 정책 배포</span><span class="sxs-lookup"><span data-stu-id="c15f4-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="c15f4-161">서버 관리자의 **도메인** > 그룹 정책 개체 아래에서 위의 3 단계에서 GPO를 선택 합니다 (예: "Cloud_Enrollment").</span><span class="sxs-lookup"><span data-stu-id="c15f4-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="c15f4-162">GPO의 **범위** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="c15f4-163">GPO의 범위 탭에서 **링크**아래의 도메인에 대 한 링크를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="c15f4-164">GPO를 배포 하려면 **적용** 을 선택 하 고 확인 화면에서 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="c15f4-165">최신 관리 템플릿 가져오기</span><span class="sxs-lookup"><span data-stu-id="c15f4-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="c15f4-166">**기본 AZURE AD 자격 증명을 사용 하 여 자동 MDM 등록**정책이 사용 되지 않는 경우에는 Windows 10, 버전 1803, 버전 1809 또는 버전 1903에 대해 ADMX가 설치 되어 있지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="c15f4-167">이 문제를 해결 하려면 다음 단계를 수행 합니다 (참고: 최신 MDM-admx가 이전 버전과 호환 됨).</span><span class="sxs-lookup"><span data-stu-id="c15f4-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="c15f4-168">다운로드: [Windows 10 용 관리 템플릿 (admx)이 업데이트 (1903)를 2019 수 있습니다](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="c15f4-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="c15f4-169">주 도메인 컨트롤러 (PDC)에 패키지를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="c15f4-170">폴더에 대 한 버전에 따라 탐색: **C:\Program files (x86) \Microsoft Group Policy\Windows 10 5 월 2019 업데이트 (1903) v3이 될 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="c15f4-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="c15f4-171">위의 경로에서 **정책 정의** 폴더의 이름을 **policydefinitions**로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="c15f4-172">**Policydefinitions** 폴더를 **C:\Windows\SYSVOL\domain\Policies**에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="c15f4-173">전체 도메인에 대해 중앙 정책 저장소를 사용 하려는 경우에는 여기에 PolicyDefinitions의 내용을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="c15f4-174">정책을 사용 하려면 주 도메인 컨트롤러를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="c15f4-175">이 절차는 이후 버전 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="c15f4-176">이제 사용 가능한 **기본 AZURE AD 자격 증명을 사용 하 여 자동 MDM 등록** 정책을 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f4-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>


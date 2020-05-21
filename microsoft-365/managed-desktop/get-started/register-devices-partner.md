---
title: 파트너가 장치를 등록하기 위한 단계
description: 파트너가 장치를 등록 하 여 Microsoft Managed Desktop에서 관리할 수 있도록 하는 방법
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1b1a8f03b7a11a0467826281bc2b789140dbcee
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327059"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="a59cb-103">파트너가 장치를 등록하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="a59cb-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="a59cb-104">이 항목에서는 파트너가 장치를 등록 하기 위해 수행 해야 하는 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="a59cb-105">장치를 직접 등록 하는 프로세스는 [Microsoft Managed Desktop의 등록 장치에 직접](register-devices-self.md)기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="a59cb-106">등록 준비</span><span class="sxs-lookup"><span data-stu-id="a59cb-106">Prepare for registration</span></span> 
<span data-ttu-id="a59cb-107">고객에 대 한 등록을 완료 하기 전에 먼저 [파트너 센터](https://partner.microsoft.com/dashboard)에서 해당 사용자와의 관계를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="a59cb-108">해당 프로세스에 대 한 자세한 내용은 [동의 설명서](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a59cb-108">See the [consent documentation](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="a59cb-109">모든 CSP 파트너는 고객을 대신 하 여 고객을 추가할 수 있는 consents 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="a59cb-110">파트너 관계 및 Autopilot 사용 권한에 대 한 자세한 내용은 [Partner Center help](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a59cb-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="a59cb-111">이 문서는 파트너 및 Oem만을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="a59cb-112">자동 등록 프로세스는 [Microsoft Managed Desktop의 등록 장치에서 직접](register-devices-self.md)설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="a59cb-113">파트너 센터를 사용 하 여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="a59cb-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="a59cb-114">고객과의 관계를 설정한 후에는 파트너 센터를 활용 하 여 다음 단계를 수행 하 여 관계가 있는 고객의 Autopilot에 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-114">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="a59cb-115">[파트너 센터로](https://partner.microsoft.com/dashboard) 이동</span><span class="sxs-lookup"><span data-stu-id="a59cb-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="a59cb-116">파트너 센터 메뉴에서 **고객** 을 선택한 다음 해당 장치를 관리할 고객을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="a59cb-117">고객 정보 페이지에서 **장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="a59cb-118">장치에 **프로필 적용** 에서 **장치 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="a59cb-119">그룹 이름으로 **Microsoft365Managed_Autopilot** 입력 한 다음 **찾아보기를** 선택 하 여 고객 목록 (.csv 파일 형식)을 파트너 센터에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-119">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a59cb-120">그룹 이름은 대/소문자 및 특수 문자를 포함 하 여 **Microsoft365Managed_Autopilot** 정확히 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-120">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="a59cb-121">이렇게 하면 새로 등록 된 장치를 Microsoft Managed Desktop Autopilot 프로필에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-121">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="a59cb-122">장치 구입처에서이 .csv 파일을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-122">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="a59cb-123">.Csv 파일을 받지 못한 경우에는 [Windows Autopilot에 장치 추가](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)의 단계를 수행 하 여 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-123">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="a59cb-124">Windows PowerShell 스크립트는 [Microsoft Managed Desktop Admin 포털](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash)에 사용 된 것과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-124">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="a59cb-125">파트너는 [get-windowsautopilotinfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 을 사용 하 여 파트너 센터에서 Microsoft Managed Desktop 장치에 대 한 장치를 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-125">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="a59cb-126">.Csv 파일을 업로드 하는 동안 오류 메시지가 표시 되 면 파일 형식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-126">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="a59cb-127">하드웨어 해시 전용, OEM 이름, 일련 번호 및 모델 (열 순서) 또는 Windows 제품 ID를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-127">You can use the hardware hash only, or the OEM name, serial number, and model (in that column order), or the Windows Product ID.</span></span> <span data-ttu-id="a59cb-128">장치 **추가** 옆의 링크에서 제공 되는 예제 .csv 파일을 사용 하 여 디바이스 목록을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-128">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="a59cb-129">파트너 시나리오의 Autopilot에 대 한 자세한 내용은 [고객의 계정에 장치 추가](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a59cb-129">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="a59cb-130">OEM API를 사용 하 여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="a59cb-130">Register devices by using the OEM API</span></span>

<span data-ttu-id="a59cb-131">고객에 대 한 등록을 완료 하기 전에 먼저 해당 고객과의 관계를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-131">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="a59cb-132">각 고객에 게 제공할 고유한 링크가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-132">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="a59cb-133">[OEM 관계를 설정 하는 방법을](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a59cb-133">See [How to establish OEM relationship](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="a59cb-134">관계를 설정한 후에는 Group 태그 **Microsoft365Managed_Autopilot**를 사용 하 여 고객을 위한 장치 등록을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-134">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a59cb-135">그룹 이름은 대/소문자 및 특수 문자를 포함 하 여 **Microsoft365Managed_Autopilot** 정확히 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-135">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="a59cb-136">이렇게 하면 새로 등록 된 장치를 Microsoft Managed Desktop Autopilot 프로필에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59cb-136">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

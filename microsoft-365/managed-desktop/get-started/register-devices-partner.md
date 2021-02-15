---
title: 파트너가 장치를 등록하기 위한 단계
description: 파트너가 Microsoft Managed Desktop에서 관리할 수 있도록 디바이스를 등록하는 방법
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071446"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="ffee8-103">파트너가 장치를 등록하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="ffee8-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="ffee8-104">이 항목에서는 파트너가 디바이스를 등록하기 위해 따라야 하는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="ffee8-105">직접 디바이스를 등록하는 프로세스는 [Microsoft Managed Desktop의 장치 등록에 설명되어 있습니다.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="ffee8-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="ffee8-106">등록 준비</span><span class="sxs-lookup"><span data-stu-id="ffee8-106">Prepare for registration</span></span> 
<span data-ttu-id="ffee8-107">고객 등록을 완료하기 전에 먼저 파트너 센터에서 고객과 관계를 [설정해야 합니다.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="ffee8-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="ffee8-108">해당 [프로세스에 대한](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 자세한 내용은 동의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffee8-108">See the [consent documentation](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="ffee8-109">모든 CSP 파트너는 고객이 동의하는 한 모든 고객을 대신하여 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="ffee8-110">파트너 관계 및 Autopilot 사용 권한에 대한 자세한 내용은 파트너 센터 도움말을 통해 자세히 [알아보실 수 있습니다.](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="ffee8-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="ffee8-111">이 설명서는 파트너 및 OEM에 한해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="ffee8-112">자체 등록 프로세스는 [Microsoft Managed Desktop의 등록 장치에 직접 문서화되어 있습니다.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="ffee8-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="ffee8-113">파트너 센터를 사용하여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="ffee8-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="ffee8-114">고객과의 관계를 설정한 후 파트너 센터를 활용하여 다음 단계에 따라 관계에 있는 모든 고객을 위해 Autopilot에 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-114">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="ffee8-115">파트너 [센터로 이동](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="ffee8-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="ffee8-116">파트너 **센터** 메뉴에서 고객을 선택한 다음 디바이스를 관리할 고객을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="ffee8-117">고객의 세부 정보 페이지에서 장치를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ffee8-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="ffee8-118">장치에 **프로필 적용** 아래에서 장치 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ffee8-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="ffee8-119">그룹 **Microsoft365Managed_Autopilot** 이름을 입력한 다음 찾아보기를 선택하여 고객 목록(.csv 파일 형식)을 파트너 센터에 업로드합니다. </span><span class="sxs-lookup"><span data-stu-id="ffee8-119">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="ffee8-120">그룹 이름은 **대문자** Microsoft365Managed_Autopilot 문자를 포함하여 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-120">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="ffee8-121">이렇게 하면 새로 등록된 장치를 Microsoft Managed Desktop Autopilot 프로필로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-121">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="ffee8-122">장치 구매와 함께 이 .csv 파일을 받았을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-122">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="ffee8-123">.csv 파일을 받지 않은 경우 [Windows Autopilot에](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)장치 추가의 단계에 따라 직접 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-123">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="ffee8-124">이 Windows PowerShell [Microsoft Managed Desktop Admin 포털에 사용되는 스크립트와 다릅니다.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash)</span><span class="sxs-lookup"><span data-stu-id="ffee8-124">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="ffee8-125">파트너는 [Get-WindowsAutoPilotInfo를](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 사용하여 파트너 센터에서 Microsoft Managed Desktop 장치용 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-125">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="ffee8-126">.csv 파일을 업로드하는 동안 오류 메시지가 표시되어 있는 경우 파일의 형식을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-126">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="ffee8-127">열 순서가 새 장치에서 [Windows Autopilot](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)프로필을 사용하여 고객의 첫 실행 경험을 사용자 지정하는 데 설명된 순서와 일치하는지 확인</span><span class="sxs-lookup"><span data-stu-id="ffee8-127">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="ffee8-128">장치 추가 옆에 있는 링크에서 제공된 샘플 .csv 파일을 사용하여 장치 목록을 만들 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="ffee8-128">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="ffee8-129">파트너 시나리오의 Autopilot에 대한 자세한 내용은 고객 계정에 장치 [추가를 참조하세요.](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)</span><span class="sxs-lookup"><span data-stu-id="ffee8-129">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="ffee8-130">OEM API를 사용하여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="ffee8-130">Register devices by using the OEM API</span></span>

<span data-ttu-id="ffee8-131">고객 등록을 완료하기 전에 먼저 고객과 관계를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-131">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="ffee8-132">각 고객에게 제공할 고유한 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-132">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="ffee8-133">[OEM 관계를 설정하는 방법을 참조합니다.](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)</span><span class="sxs-lookup"><span data-stu-id="ffee8-133">See [How to establish OEM relationship](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="ffee8-134">관계를 설정한 후 그룹 태그 그룹을 사용하여 고객을 위해 디바이스를 등록할 **수 Microsoft365Managed_Autopilot.**</span><span class="sxs-lookup"><span data-stu-id="ffee8-134">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ffee8-135">그룹 이름은 **대/Microsoft365Managed_Autopilot** 문자를 포함하여 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-135">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="ffee8-136">이렇게 하면 새로 등록된 장치를 Microsoft Managed Desktop Autopilot 프로필로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffee8-136">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

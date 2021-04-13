---
title: 파트너가 장치를 등록하기 위한 단계
description: 파트너가 Microsoft Managed Desktop에서 관리할 수 있도록 장치를 등록하는 방법
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689236"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="32cf1-103">파트너가 장치를 등록하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="32cf1-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="32cf1-104">이 문서에서는 파트너가 장치를 등록하기 위해 따라야 하는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-104">This article describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="32cf1-105">장치를 직접 등록하는 프로세스는 [직접 Microsoft Managed Desktop에서 장치 등록에 설명되어 있습니다.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="32cf1-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="32cf1-106">등록 준비</span><span class="sxs-lookup"><span data-stu-id="32cf1-106">Prepare for registration</span></span> 
<span data-ttu-id="32cf1-107">고객 등록을 완료하기 전에 먼저 파트너 센터에서 고객과 [관계를 설정해야 합니다.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="32cf1-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="32cf1-108">해당 [프로세스에 대한](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 자세한 내용은 동의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32cf1-108">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="32cf1-109">모든 CSP 파트너는 고객이 동의하는 한 모든 고객을 대신하여 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="32cf1-110">파트너 관계 및 Autopilot 사용 권한에 대한 자세한 내용은 파트너 센터 [도움말을 통해 자세히 알아보실 수 있습니다.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="32cf1-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="32cf1-111">이 설명서는 파트너 및 OEM에 한해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="32cf1-112">자체 등록 프로세스는 [직접 Microsoft Managed Desktop에서 장치 등록에 설명되어 있습니다.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="32cf1-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="32cf1-113">파트너 센터를 사용하여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="32cf1-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="32cf1-114">고객과의 관계를 설정한 후 파트너 센터를 사용하여 다음 단계에 따라 관계가 있는 모든 고객을 위해 Autopilot에 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-114">Once you have established the relationship with your customers, you can use Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="32cf1-115">파트너 [센터로 이동](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="32cf1-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="32cf1-116">파트너 **센터** 메뉴에서 고객을 선택한 다음 디바이스를 관리할 고객을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="32cf1-117">고객의 세부 정보 페이지에서 장치를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="32cf1-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="32cf1-118">장치에 **프로필 적용에서** 장치 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="32cf1-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="32cf1-119">선택한 장치 프로필에 적절한 그룹 태그를 입력한 다음 찾아보기를 선택하여  고객 목록(.csv 파일 형식)을 파트너 센터에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-119">Enter the appropriate Group Tag for the device profile you've selected (as shown in the following table) and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>

|[<span data-ttu-id="32cf1-120">장치 프로필</span><span class="sxs-lookup"><span data-stu-id="32cf1-120">Device profile</span></span>](../service-description/profiles.md)  |<span data-ttu-id="32cf1-121">그룹 태그</span><span class="sxs-lookup"><span data-stu-id="32cf1-121">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="32cf1-122">민감 데이터</span><span class="sxs-lookup"><span data-stu-id="32cf1-122">Sensitive data</span></span>     |<span data-ttu-id="32cf1-123">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="32cf1-123">**Microsoft365Managed\_SensitiveData**</span></span>    |
|<span data-ttu-id="32cf1-124">파워 사용자</span><span class="sxs-lookup"><span data-stu-id="32cf1-124">Power user</span></span>     | <span data-ttu-id="32cf1-125">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="32cf1-125">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="32cf1-126">Standard</span><span class="sxs-lookup"><span data-stu-id="32cf1-126">Standard</span></span>     | <span data-ttu-id="32cf1-127">**Microsoft365Managed \_ Standard**</span><span class="sxs-lookup"><span data-stu-id="32cf1-127">**Microsoft365Managed\_Standard**</span></span>        |

> [!IMPORTANT]
> <span data-ttu-id="32cf1-128">그룹 이름은 대문자 및 특수 문자를 포함하여 표에 나열된 이름과 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-128">The Group Name must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="32cf1-129">이렇게 하면 새로 등록된 장치를 Microsoft Managed Desktop Autopilot 프로필로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-129">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="32cf1-130">디바이스 구매와 함께 이 .csv 파일을 받았을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-130">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="32cf1-131">.csv 파일을 받지 못하면 [Windows Autopilot에](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)장치 추가의 단계에 따라 직접 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-131">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="32cf1-132">이 Windows PowerShell 스크립트는 [Microsoft Managed Desktop Admin 포털에 사용되는 스크립트와 다릅니다.](./register-devices-self.md#obtain-the-hardware-hash)</span><span class="sxs-lookup"><span data-stu-id="32cf1-132">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md#obtain-the-hardware-hash).</span></span> <span data-ttu-id="32cf1-133">파트너는 [Get-WindowsAutoPilotInfo를](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 사용하여 파트너 센터에서 Microsoft Managed Desktop 장치에 대한 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-133">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="32cf1-134">.csv 파일을 업로드하는 동안 오류 메시지가 표시되어 있는 경우 파일 형식을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-134">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="32cf1-135">열 순서가 새 장치에서 [Windows Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)프로필을 사용하여 고객의 첫 실행 경험을 사용자 지정에 설명된 순서와 일치하는지 확인</span><span class="sxs-lookup"><span data-stu-id="32cf1-135">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="32cf1-136">장치 추가 옆에 있는 링크에서 제공된 샘플 .csv 파일을 사용하여 장치 목록을 만들 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="32cf1-136">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="32cf1-137">파트너 시나리오의 Autopilot에 대한 자세한 내용은 고객 계정에 장치 [추가를 참조하세요.](/partner-center/autopilot#add-devices-to-a-customers-account)</span><span class="sxs-lookup"><span data-stu-id="32cf1-137">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="32cf1-138">OEM API를 사용하여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="32cf1-138">Register devices by using the OEM API</span></span>

<span data-ttu-id="32cf1-139">고객 등록을 완료하기 전에 먼저 고객과 관계를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-139">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="32cf1-140">각 고객에게 제공할 고유한 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-140">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="32cf1-141">[OEM 관계를 설정하는 방법을 참조합니다.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)</span><span class="sxs-lookup"><span data-stu-id="32cf1-141">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="32cf1-142">관계를 설정한 후 선택한 각 장치 프로필에 대해 적절한 그룹 태그를 사용하여 고객을 위해 디바이스를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-142">Once you've established the relationship, you can start registering devices for customers using the appropriate Group Tag for each device profile they've selected:</span></span>


|<span data-ttu-id="32cf1-143">장치 프로필</span><span class="sxs-lookup"><span data-stu-id="32cf1-143">Device profile</span></span>  |<span data-ttu-id="32cf1-144">그룹 태그</span><span class="sxs-lookup"><span data-stu-id="32cf1-144">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="32cf1-145">민감 데이터</span><span class="sxs-lookup"><span data-stu-id="32cf1-145">Sensitive data</span></span>     | <span data-ttu-id="32cf1-146">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="32cf1-146">**Microsoft365Managed\_SensitiveData**</span></span>     |
|<span data-ttu-id="32cf1-147">파워 사용자</span><span class="sxs-lookup"><span data-stu-id="32cf1-147">Power user</span></span>     | <span data-ttu-id="32cf1-148">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="32cf1-148">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="32cf1-149">Standard</span><span class="sxs-lookup"><span data-stu-id="32cf1-149">Standard</span></span>     | <span data-ttu-id="32cf1-150">**Microsoft365Managed \_ Standard**</span><span class="sxs-lookup"><span data-stu-id="32cf1-150">**Microsoft365Managed\_Standard**</span></span>      |

> [!IMPORTANT]
> <span data-ttu-id="32cf1-151">그룹 태그는 대문자 및 특수 문자를 포함하여 표에 나열된 태그와 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-151">The Group Tags must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="32cf1-152">이렇게 하면 새로 등록된 장치를 Microsoft Managed Desktop Autopilot 프로필로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cf1-152">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>
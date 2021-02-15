---
title: Microsoft OneDrive
description: Microsoft Managed Desktop에서 등록된 장치에 대해 OneDrive를 설정하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6cd2c993e0ca9d4c456a2914b866b65b59799afa
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233925"
---
# <a name="microsoft-onedrive"></a><span data-ttu-id="18fb5-104">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="18fb5-104">Microsoft OneDrive</span></span>

<span data-ttu-id="18fb5-105">Microsoft Managed Desktop은 비즈니스용 [OneDrive를](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) 모든 Microsoft Managed Desktop 장치에 대한 클라우드 저장소 서비스로 사용하여 장치가 가능한 한 상태를 저장하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-105">Microsoft Managed Desktop uses [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) as a cloud storage service for all Microsoft Managed Desktop devices to ensure that the devices are as stateless as possible.</span></span> <span data-ttu-id="18fb5-106">사용자는 로그인하는 디바이스에 상관없이 파일을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-106">User will be able to find their files no matter which device they sign into.</span></span> <span data-ttu-id="18fb5-107">예를 들어 Microsoft Managed Desktop 장치를 새 장치로 바꾸면 파일이 새 디바이스에 자동으로 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-107">For example, if you replace a Microsoft Managed Desktop device with a new one, files will automatically sync to the new device.</span></span>

<span data-ttu-id="18fb5-108">Microsoft Managed Devices에서 기본적으로 이러한 설정을 자동으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-108">We automatically configure these settings by default on Microsoft Managed Devices:</span></span>

- <span data-ttu-id="18fb5-109">OneDrive는 사용자 계정으로 자동으로 구성되며 사용자 조작 없이 Windows에 로그인하는 데 사용된 사용자 계정에 자동으로 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-109">OneDrive is silently configured with the user account and automatically signed in (without user interaction) to the user account that was used to sign into Windows.</span></span> <span data-ttu-id="18fb5-110">자세한 내용은 사용자 계정 자동 구성 [- OneDrive를 참조하세요.](https://docs.microsoft.com/onedrive/use-silent-account-configuration)</span><span class="sxs-lookup"><span data-stu-id="18fb5-110">For more information, see [Silently configure user accounts - OneDrive](https://docs.microsoft.com/onedrive/use-silent-account-configuration)</span></span>

- <span data-ttu-id="18fb5-111">사용자가 디스크 공간을 불필요하게 사용하지 않고도 OneDrive의 클라우드 저장소에서 파일에 액세스할 수 있도록 파일 관리 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-111">The Files-On-Demand feature is enabled so that users can access files from their cloud storage in OneDrive without having to use disk space unnecessarily.</span></span> <span data-ttu-id="18fb5-112">자세한 내용은 [Windows 10용 OneDrive On-Demand 파일로 디스크 공간 저장을 참조하세요.](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)</span><span class="sxs-lookup"><span data-stu-id="18fb5-112">For more information, see [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).</span></span>

- <span data-ttu-id="18fb5-113">알려진 폴더 이동 기능은 클라우드에서 사용자의 데이터를 백업할 수 있도록 자동으로 사용하도록 설정되어 모든 장치에서 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-113">The Known Folder Move feature is enabled silently to back up users’ data in the cloud, which gives them access to their files from any device.</span></span> <span data-ttu-id="18fb5-114">자세한 내용은 [OneDrive를](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)사용하여 문서, 사진 및 데스크톱 폴더 백업을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18fb5-114">For more information, see [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).</span></span>

- <span data-ttu-id="18fb5-115">사용자는 알려진 폴더 이동 기능을 사용하지 않도록 설정하거나 알려진 폴더의 위치를 변경하여 Microsoft Managed Desktop 장치에서 일관된 환경을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-115">Users cannot disable the Known Folder Move feature or change the location of known folders to ensure a consistent experience across Microsoft Managed Desktop devices.</span></span>

## <a name="user-experience"></a><span data-ttu-id="18fb5-116">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="18fb5-116">User experience</span></span>

<span data-ttu-id="18fb5-117">Microsoft Managed Desktop 사용자가 새 디바이스를 받으면 디바이스를 설정하는 동안 Azure 자격 증명을 입력하여 첫 실행 환경을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-117">When Microsoft Managed Desktop users receive a new device, they go through a first-run experience by entering their Azure credentials while setting up the device.</span></span> <span data-ttu-id="18fb5-118">이 프로세스가 완료되면 데스크톱에 액세스하고 OneDrive 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-118">After this process is completed, they can access their desktop and have the OneDrive experience.</span></span>

1. <span data-ttu-id="18fb5-119">시스템은 OneDrive가 구성되어 있으며 OneDrive에 자동으로 로그인되어 있는지 사용자에게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-119">The system tells users that OneDrive has been configured and that they have been automatically signed into OneDrive.</span></span>

:::image type="content" source="media/onedrive-sync.png" alt-text="이제 OneDrive를 동기화하고 있으며 OneDrive에서 파일을 편집할 수 있습니다. 파일을 보려면 여기를 클릭하십시오.":::

2. <span data-ttu-id="18fb5-121">시스템은 OneDrive 알려진 폴더 이동이 해당 폴더에 대해 구성되어 있는지 사용자에게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-121">The system tells users that OneDrive Known Folder Move has been configured for them.</span></span>

:::image type="content" source="media/onedrive-folders.png" alt-text="IT 부서를 읽은 알림이 중요한 폴더를 백업했습니다. 이제 폴더가 OneDrive에 백업된 후 다른 장치에서 사용할 수 있습니다.":::

3. <span data-ttu-id="18fb5-123">디바이스를 초기화하거나 다시 초기화할 때 바탕 화면의 중복 아이콘을 방지하기 위해 시스템은 파일 탐색기의 이 보기에 표시된 같이 OneDrive 동기화에서 Microsoft Edge 및 Microsoft Teams 아이콘을 자동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-123">To prevent duplicate icons on the desktop when devices are being reset or reimaged, the system automatically removes Microsoft Edge and Microsoft Teams icons from the OneDrive sync, as shown in this view in File Explorer.</span></span>

:::image type="content" source="media/onedrive-teams.png" alt-text="선택 취소된 확인란 및 마우스로 읽은 마우스 텍스트 읽기가 동기화에서 제외된 Teams 및 Edge 목록을 표시하는 파일 탐색기입니다.":::


## <a name="onedrive-sync-restrictions"></a><span data-ttu-id="18fb5-125">OneDrive 동기화 제한</span><span class="sxs-lookup"><span data-stu-id="18fb5-125">OneDrive sync restrictions</span></span>

<span data-ttu-id="18fb5-126">OneDrive 동기화를 제한해야 하는 경우 Azure Active Directory 조건부 액세스 정책을 사용하여 액세스를 제어하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-126">If you need to restrict OneDrive sync, we recommend that you control access with an Azure Active Directory conditional access policy.</span></span> <span data-ttu-id="18fb5-127">자세한 내용은 OneDrive 동기화 앱에서 조건부 액세스 지원 [사용을 참조하세요.](https://docs.microsoft.com/onedrive/enable-conditional-access)</span><span class="sxs-lookup"><span data-stu-id="18fb5-127">For more information, see [Enable conditional access support in the OneDrive sync app](https://docs.microsoft.com/onedrive/enable-conditional-access).</span></span>

<span data-ttu-id="18fb5-128">조직에서 Azure AD 조건부 액세스 정책을 사용할 수 없는 경우 IT 관리자는 다음 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-128">If you can't use an Azure AD conditional access policy in your organization, your IT Admin should follow these steps:</span></span>

1. <span data-ttu-id="18fb5-129">아직 모르는 경우 Microsoft 365 테넌트 ID 찾기에 설명된 테넌트 [ID를 찾아 봐야 합니다.](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)</span><span class="sxs-lookup"><span data-stu-id="18fb5-129">If you don't already know it, look up your tenant ID, as described in [Find your Microsoft 365 tenant ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).</span></span>
2. <span data-ttu-id="18fb5-130">OneDrive 관리 센터에 로그인한 다음  왼쪽 창에서 동기화를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-130">Sign in to the OneDrive admin center, and then select **Sync** in the left pane.</span></span> <span data-ttu-id="18fb5-131">특정 도메인에 가입된 **PC에서만** 동기화 허용 확인란을 선택한 다음 도메인 목록에 테넌트 ID를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-131">Select the **Allow syncing only on PCs joined to specific domains** check box, and then add the tenant ID to the list of domains.</span></span> <span data-ttu-id="18fb5-132">자세한 내용은 특정 도메인에 가입된 컴퓨터에서만 동기화 [허용을 참조하세요.](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains)</span><span class="sxs-lookup"><span data-stu-id="18fb5-132">For more information, see [Allow syncing only on computers joined to specific domains](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains).</span></span>

> [!NOTE]
> <span data-ttu-id="18fb5-133">이 지침은 Microsoft Managed Desktop의 테넌트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-133">This guidance applies only to tenants in Microsoft Managed Desktop.</span></span> <span data-ttu-id="18fb5-134">이 문서에서 설명하지 않은 다른 설정이 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="18fb5-134">There are other settings in use that aren't discussed in this article.</span></span>

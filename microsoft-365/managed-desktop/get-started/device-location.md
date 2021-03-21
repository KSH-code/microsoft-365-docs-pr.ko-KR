---
title: Windows 10 위치 서비스
description: 장치에 대해 Windows 위치 서비스를 설정하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
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
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929503"
---
# <a name="windows-10-location-service"></a><span data-ttu-id="586c7-104">Windows 10 위치 서비스</span><span class="sxs-lookup"><span data-stu-id="586c7-104">Windows 10 location service</span></span>

<span data-ttu-id="586c7-105">Microsoft Managed Desktop의 장치는 Windows Autopilot을 사용하여 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="586c7-106">이 프로세스를 통해 Azure Active Directory 및 Microsoft Intune을 사용하여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="586c7-107">기본적으로 "첫 실행 경험" 동안 개인 정보 설정에서 이 기능을 사용하도록 설정하지 않으면 장치를 처음 켜면 Windows 10 위치 서비스가 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="586c7-108">이러한 설정은 Microsoft Managed Desktop에서 Autopilot 등록 중에 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="586c7-109">Autopilot을 설정하는 방법에 대한 자세한 내용은 [Autopilot의](esp-first-run.md)첫 실행 환경 및 등록 상태 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="586c7-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="586c7-110">이러한 이유로 Microsoft Managed Desktop 장치는 표준 시간대와 같은 여러 Windows 기능의 기능을 제한하는 장치 위치를 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="586c7-111">Windows 10 위치 서비스에 대한 자세한 내용은 [Windows 10 위치 서비스 및 개인 정보를 참조하세요.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="586c7-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="586c7-112">Microsoft Managed Desktop에 참여하기 위해 위치 서비스를 사용할 수 없지만 사용자 환경은 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="586c7-113">예를 들어 디바이스는 사용자가 다른 표준 시간대로 작업할 때 해당 표준 시간대를 자동으로 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="586c7-114">위치 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="586c7-114">Enable the location service</span></span>

<span data-ttu-id="586c7-115">장치를 Microsoft Managed Desktop 서비스에 등록할 때 위치 서비스를 옵트인하거나 등록 후 서비스를 켜거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="586c7-116">등록 중 옵트인</span><span class="sxs-lookup"><span data-stu-id="586c7-116">Opt in during enrollment</span></span>

<span data-ttu-id="586c7-117">Microsoft Managed Desktop 서비스가 위치 서비스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="586c7-118">등록 시퀀스 중에 디바이스에서 Windows 10 위치 서비스를 사용하도록 허용할지 여부를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="586c7-119">등록 후 위치 서비스 제어</span><span class="sxs-lookup"><span data-stu-id="586c7-119">Control the location service after enrollment</span></span>

<span data-ttu-id="586c7-120">관리 포털을 통해 지원 요청을 제출하여 위치 서비스를 설정하거나 해제할 [수 있습니다.](access-admin-portal.md) [](../working-with-managed-desktop/admin-support.md)</span><span class="sxs-lookup"><span data-stu-id="586c7-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="586c7-121">Microsoft Managed Desktop에서 Windows 10 위치 서비스를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="586c7-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="586c7-122">위치 서비스를 사용하기로 옵트인하는 경우 사용자의 개인 정보 보호에 영향을 주지 않고 필요한 최소 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="586c7-123">자세한 내용은 [Windows 10 위치 서비스 및 개인 정보를 참조하세요.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="586c7-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="586c7-124">Microsoft Managed Desktop은 **Windows** 설정의 위치 개인 정보 설정을 사용하여 이 장치의 위치에 대한 액세스를  **허용하도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="586c7-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="586c7-125">사용자 인터페이스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Windows 설정의 위치 설정":::

> [!NOTE]
> <span data-ttu-id="586c7-127">위치 서비스를 옵트인(opt in)하는 경우 Windows 운영 체제 자체에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="586c7-128">앱은 위치 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="586c7-129">각 사용자는 앱이 자신의 위치에 액세스할 수 있도록 허용할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-129">Each user can choose whether to allow apps to access their location.</span></span>
---
title: Windows 10 위치 서비스
description: 디바이스에 대해 Windows 위치 서비스를 설정하는 방법
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
# <a name="windows-10-location-service"></a><span data-ttu-id="9cdf0-104">Windows 10 위치 서비스</span><span class="sxs-lookup"><span data-stu-id="9cdf0-104">Windows 10 location service</span></span>

<span data-ttu-id="9cdf0-105">디바이스의 Microsoft Managed Desktop Autopilot을 사용하여 Windows 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="9cdf0-106">이 프로세스를 통해 사용자 및 사용자 Azure Active Directory 관리할 Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="9cdf0-107">기본적으로 Windows 10 동안 개인 정보 설정에서 이 기능을 사용하도록 설정하지 않는 한 장치를 처음 켜면 Windows 10 위치 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="9cdf0-108">이러한 설정은 2016년 8월에 Autopilot 등록 중에 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="9cdf0-109">Autopilot을 설정하는 방법에 대한 자세한 내용은 [Autopilot의](esp-first-run.md)첫 실행 환경 및 등록 상태 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="9cdf0-110">따라서 Microsoft Managed Desktop 장치 위치를 얻을 수 없습니다. 이로 인해 표준 시간대와 같은 여러 Windows 기능의 기능이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="9cdf0-111">Windows 10 위치 서비스에 대한 자세한 내용은 Windows 10 위치 서비스 및 개인 정보를 [참조하세요.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="9cdf0-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="9cdf0-112">위치 서비스에 참여하기 위해 위치 서비스를 사용할 Microsoft Managed Desktop 사용자 환경은 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="9cdf0-113">예를 들어 디바이스는 사용자가 다른 표준 시간대로 작업할 때 해당 표준 시간대를 자동으로 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="9cdf0-114">위치 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="9cdf0-114">Enable the location service</span></span>

<span data-ttu-id="9cdf0-115">장치를 Microsoft Managed Desktop 서비스에 등록할 때 위치 서비스를 옵트인하거나 등록 후 서비스를 켜거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="9cdf0-116">등록 중 옵트인</span><span class="sxs-lookup"><span data-stu-id="9cdf0-116">Opt in during enrollment</span></span>

<span data-ttu-id="9cdf0-117">서비스에서 위치 Microsoft Managed Desktop 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="9cdf0-118">등록 시퀀스 중에 디바이스에서 Windows 10 위치 서비스를 사용하도록 허용할지 여부를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="9cdf0-119">등록 후 위치 서비스 제어</span><span class="sxs-lookup"><span data-stu-id="9cdf0-119">Control the location service after enrollment</span></span>

<span data-ttu-id="9cdf0-120">관리 포털을 통해 지원 요청을 제출하여 위치 서비스를 설정하거나 해제할 [수 있습니다.](access-admin-portal.md) [](../working-with-managed-desktop/admin-support.md)</span><span class="sxs-lookup"><span data-stu-id="9cdf0-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="9cdf0-121">Microsoft Managed Desktop 위치 서비스를 구성하는 Windows 10 방법</span><span class="sxs-lookup"><span data-stu-id="9cdf0-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="9cdf0-122">위치 서비스를 사용하기로 옵트인하는 경우 사용자의 개인 정보 보호에 영향을 주지 않고 필요한 최소 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="9cdf0-123">자세한 내용은 Windows 10 [위치 서비스 및 개인 정보를 참조하세요.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="9cdf0-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="9cdf0-124">Microsoft Managed Desktop 설정의  위치 개인 정보 설정을 이 **Windows** 위치에 대한 액세스를 허용하도록 **설정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9cdf0-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="9cdf0-125">사용자 인터페이스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="기본 설정의 Windows 설정":::

> [!NOTE]
> <span data-ttu-id="9cdf0-127">위치 서비스를 사용 옵트인(opt in)하는 경우 이 설정은 Windows 운영 체제 자체에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="9cdf0-128">앱은 위치 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="9cdf0-129">각 사용자는 앱이 자신의 위치에 액세스할 수 있도록 허용할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdf0-129">Each user can choose whether to allow apps to access their location.</span></span>
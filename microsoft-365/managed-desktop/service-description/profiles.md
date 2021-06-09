---
title: 디바이스 프로필 이해
description: 관리자가 디바이스에 할당할 수 있는 다양한 프로필
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
ms.openlocfilehash: 5b5421d2b4001b813d3bcc1e804cae7fb05d0fa7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842005"
---
# <a name="device-profiles"></a><span data-ttu-id="ba872-104">장치 프로필</span><span class="sxs-lookup"><span data-stu-id="ba872-104">Device profiles</span></span>

<span data-ttu-id="ba872-105">장치에 서로 다른 미리 설정된 구성("장치 프로필")을 할당할 수 있습니다. 각 구성은 특정 유형의 사용자 요구에 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-105">You can assign different pre-set configurations ("device profiles") to devices, each optimized for the needs of specific types of users.</span></span> <span data-ttu-id="ba872-106">세 개의 장치 프로필을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-106">Three device profiles are available:</span></span>

- <span data-ttu-id="ba872-107">Standard</span><span class="sxs-lookup"><span data-stu-id="ba872-107">Standard</span></span>
- <span data-ttu-id="ba872-108">중요한 데이터</span><span class="sxs-lookup"><span data-stu-id="ba872-108">Sensitive Data</span></span>
- <span data-ttu-id="ba872-109">파워 사용자</span><span class="sxs-lookup"><span data-stu-id="ba872-109">Power user</span></span>

<span data-ttu-id="ba872-110">장치 프로필은 장치 구성 옵션 계층 구조의 일부로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-110">You can think of device profiles as being part of a hierarchy of device configuration options.</span></span>

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="피라미드로 표시된 장치 구성. 설명은 다음과 같습니다.":::

<span data-ttu-id="ba872-112">기본적으로 모든 Microsoft Managed Desktop 장치에는 표준 보안 기준, 규정 준수 정책, Windows 설정 및 그룹을 포함하는 기초가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-112">Fundamentally, every Microsoft Managed Desktop device has a foundation that includes a standard security baseline, compliance policies, Windows Update settings, and groups.</span></span> <span data-ttu-id="ba872-113">이 Microsoft Managed Desktop 사용하려면 모든 디바이스에 이러한 요소가 모두 포함되어야 합니다. 이러한 요소는 관리자의 요청 없이는 변경할 수 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ba872-113">To work with Microsoft Managed Desktop, every device must include all of these elements, which can't be changed by admins without a request to Microsoft Managed Desktop.</span></span>

<span data-ttu-id="ba872-114">장치 프로필은 한 단계 더 높은 수준에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-114">Device profiles appear at the next higher level.</span></span> <span data-ttu-id="ba872-115">모든 Microsoft Managed Desktop 디바이스에는 하나만 할당된 프로필이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-115">Every Microsoft Managed Desktop device must have one (and only one) profile assigned.</span></span> <span data-ttu-id="ba872-116">관리자는 디바이스가 할당된 프로필을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-116">Admins can choose which profile a device is assigned.</span></span>

<span data-ttu-id="ba872-117">여전히 더 높은 수준에서는 추가 [사용자 지정이 있습니다.](customizing.md)</span><span class="sxs-lookup"><span data-stu-id="ba872-117">At a still higher level are additional [customizations](customizing.md).</span></span> <span data-ttu-id="ba872-118">각 디바이스에는 하나 이상의 사용자 지정이(또는 아니요) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-118">Each device can have one or more (or no) customizations.</span></span> <span data-ttu-id="ba872-119">하위 계층(장치 프로필 또는 기본 구성)을 수정하거나 표준 구성 위에 계층화된 완전히 새로운 요청이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-119">They can either modify a lower-level layer (Device profiles or the foundational configuration),  or be an entirely new request that’s layered on top of the standard configuration.</span></span>

<span data-ttu-id="ba872-120">맨 위에는 네트워크 세부 정보 또는 응용 프로그램과 같은 자체 수정 내용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-120">At the top are your own modifications, such as network details or applications.</span></span> <span data-ttu-id="ba872-121">장치에는 이러한 수정 내용이 있을 수 있습니다. 이러한 수정은 해당 수정 내용에 의해 관리되거나 차단되지 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ba872-121">A device can have any number of these modifications, which aren't managed or blocked by Microsoft Managed Desktop.</span></span>


## <a name="device-profile-details"></a><span data-ttu-id="ba872-122">장치 프로필 세부 정보</span><span class="sxs-lookup"><span data-stu-id="ba872-122">Device profile details</span></span>

<span data-ttu-id="ba872-123">다음 표에는 장치 프로필에 의해 구성된 각 설정의 설정과 해당 기본값이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-123">The following table summarizes the settings and their default values for each setting configured by device profiles.</span></span> <span data-ttu-id="ba872-124">(장면 뒤에서 이러한 설정은 OMA-URIs 사용자 지정 구성 프로필을 사용하여 구성됩니다Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="ba872-124">(Behind the scenes, these settings are configured with OMA-URIs by using Custom Configuration Profiles in Microsoft Endpoint Manager.)</span></span>

<br>

****

|<span data-ttu-id="ba872-125">기능</span><span class="sxs-lookup"><span data-stu-id="ba872-125">Feature</span></span>|<span data-ttu-id="ba872-126">중요한 데이터</span><span class="sxs-lookup"><span data-stu-id="ba872-126">Sensitive Data</span></span>|<span data-ttu-id="ba872-127">Power User</span><span class="sxs-lookup"><span data-stu-id="ba872-127">Power User</span></span>|<span data-ttu-id="ba872-128">Standard</span><span class="sxs-lookup"><span data-stu-id="ba872-128">Standard</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="ba872-129">**외부 웹 Storage**</span><span class="sxs-lookup"><span data-stu-id="ba872-129">**Block External Storage**</span></span>|<span data-ttu-id="ba872-130">예</span><span class="sxs-lookup"><span data-stu-id="ba872-130">Yes</span></span>|<span data-ttu-id="ba872-131">예</span><span class="sxs-lookup"><span data-stu-id="ba872-131">Yes</span></span>|<span data-ttu-id="ba872-132">아니요</span><span class="sxs-lookup"><span data-stu-id="ba872-132">No</span></span>|
|<span data-ttu-id="ba872-133">**[클라우드 차단 수준](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**</span><span class="sxs-lookup"><span data-stu-id="ba872-133">**[Cloud Block Level](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**</span></span>|<span data-ttu-id="ba872-134">높음</span><span class="sxs-lookup"><span data-stu-id="ba872-134">High</span></span>|<span data-ttu-id="ba872-135">높음</span><span class="sxs-lookup"><span data-stu-id="ba872-135">High</span></span>|<span data-ttu-id="ba872-136">높음</span><span class="sxs-lookup"><span data-stu-id="ba872-136">High</span></span>|
|<span data-ttu-id="ba872-137">**Microsoft 계정을 사용하지 않도록 설정**</span><span class="sxs-lookup"><span data-stu-id="ba872-137">**Disable Microsoft Accounts**</span></span>|<span data-ttu-id="ba872-138">예</span><span class="sxs-lookup"><span data-stu-id="ba872-138">Yes</span></span>|<span data-ttu-id="ba872-139">예</span><span class="sxs-lookup"><span data-stu-id="ba872-139">Yes</span></span>|<span data-ttu-id="ba872-140">아니요</span><span class="sxs-lookup"><span data-stu-id="ba872-140">No</span></span>|
|<span data-ttu-id="ba872-141">**개인 정보 보호 OneDrive**</span><span class="sxs-lookup"><span data-stu-id="ba872-141">**Disable personal OneDrive**</span></span>|<span data-ttu-id="ba872-142">예</span><span class="sxs-lookup"><span data-stu-id="ba872-142">Yes</span></span>|<span data-ttu-id="ba872-143">예</span><span class="sxs-lookup"><span data-stu-id="ba872-143">Yes</span></span>|<span data-ttu-id="ba872-144">아니요</span><span class="sxs-lookup"><span data-stu-id="ba872-144">No</span></span>|
|<span data-ttu-id="ba872-145">**권한 상승을 위해 보안 데스크톱으로 전환**</span><span class="sxs-lookup"><span data-stu-id="ba872-145">**Switch to secure desktop for elevation**</span></span>|<span data-ttu-id="ba872-146">아니요</span><span class="sxs-lookup"><span data-stu-id="ba872-146">No</span></span>|<span data-ttu-id="ba872-147">예</span><span class="sxs-lookup"><span data-stu-id="ba872-147">Yes</span></span>|<span data-ttu-id="ba872-148">아니요</span><span class="sxs-lookup"><span data-stu-id="ba872-148">No</span></span>|
|<span data-ttu-id="ba872-149">**끝점 장치 태그용 Microsoft Defender**</span><span class="sxs-lookup"><span data-stu-id="ba872-149">**Microsoft Defender for Endpoint Device Tag**</span></span>|<span data-ttu-id="ba872-150">M365Managed-SensitiveData</span><span class="sxs-lookup"><span data-stu-id="ba872-150">M365Managed-SensitiveData</span></span>|<span data-ttu-id="ba872-151">M365Managed-PowerUser</span><span class="sxs-lookup"><span data-stu-id="ba872-151">M365Managed-PowerUser</span></span>|<span data-ttu-id="ba872-152">M365Managed-Standard</span><span class="sxs-lookup"><span data-stu-id="ba872-152">M365Managed-Standard</span></span>|
|<span data-ttu-id="ba872-153">**디바이스의 관리자인가요?**</span><span class="sxs-lookup"><span data-stu-id="ba872-153">**Admin on the device?**</span></span>|<span data-ttu-id="ba872-154">아니요</span><span class="sxs-lookup"><span data-stu-id="ba872-154">No</span></span>|<span data-ttu-id="ba872-155">예</span><span class="sxs-lookup"><span data-stu-id="ba872-155">Yes</span></span>|<span data-ttu-id="ba872-156">아니요</span><span class="sxs-lookup"><span data-stu-id="ba872-156">No</span></span>|
|<span data-ttu-id="ba872-157">**Autopilot 프로필**</span><span class="sxs-lookup"><span data-stu-id="ba872-157">**Autopilot Profile**</span></span>|<span data-ttu-id="ba872-158">MMD Standard</span><span class="sxs-lookup"><span data-stu-id="ba872-158">MMD Standard</span></span>|<span data-ttu-id="ba872-159">MMD Power User</span><span class="sxs-lookup"><span data-stu-id="ba872-159">MMD Power User</span></span>|<span data-ttu-id="ba872-160">MMD Standard</span><span class="sxs-lookup"><span data-stu-id="ba872-160">MMD Standard</span></span>|
|<span data-ttu-id="ba872-161">**AppLocker**</span><span class="sxs-lookup"><span data-stu-id="ba872-161">**AppLocker**</span></span>|<span data-ttu-id="ba872-162">예</span><span class="sxs-lookup"><span data-stu-id="ba872-162">Yes</span></span>|<span data-ttu-id="ba872-163">아니요</span><span class="sxs-lookup"><span data-stu-id="ba872-163">No</span></span>|<span data-ttu-id="ba872-164">아니요</span><span class="sxs-lookup"><span data-stu-id="ba872-164">No</span></span>|
|<span data-ttu-id="ba872-165">**공용 저장소 차단**</span><span class="sxs-lookup"><span data-stu-id="ba872-165">**Block Public Store**</span></span>|<span data-ttu-id="ba872-166">예</span><span class="sxs-lookup"><span data-stu-id="ba872-166">Yes</span></span>|<span data-ttu-id="ba872-167">예</span><span class="sxs-lookup"><span data-stu-id="ba872-167">Yes</span></span>|<span data-ttu-id="ba872-168">아니요</span><span class="sxs-lookup"><span data-stu-id="ba872-168">No</span></span>|
|

<span data-ttu-id="ba872-169">각 장치 프로필에는 다음 항목도 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-169">Each device profile also involves these items:</span></span>

- <span data-ttu-id="ba872-170">AAD(동적 구성원 Azure Active Directory 그룹)</span><span class="sxs-lookup"><span data-stu-id="ba872-170">A dynamic membership Azure Active Directory (AAD) device group</span></span>
- <span data-ttu-id="ba872-171">정적 구성원 AAD 장치 그룹</span><span class="sxs-lookup"><span data-stu-id="ba872-171">A static membership AAD device group</span></span>
- <span data-ttu-id="ba872-172">구성 Microsoft Endpoint Manager 프로필</span><span class="sxs-lookup"><span data-stu-id="ba872-172">A Microsoft Endpoint Manager Configuration profile</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba872-173">이러한 그룹의 구성원 자격을 직접 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-173">Don’t modify the membership of these groups directly.</span></span> <span data-ttu-id="ba872-174">프로필 다시 재배치에 설명된 인터페이스를 [사용합니다.](../working-with-managed-desktop/change-device-profile.md)</span><span class="sxs-lookup"><span data-stu-id="ba872-174">Use the interface as described in [Reassign profiles](../working-with-managed-desktop/change-device-profile.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="ba872-175">제한 사항</span><span class="sxs-lookup"><span data-stu-id="ba872-175">Limitations</span></span>

<span data-ttu-id="ba872-176">다른 정책과 같은 장치 프로필 및 해당 세부 정보의 예외를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-176">You can request exceptions to the device profiles and their details as you would with any other policy.</span></span> <span data-ttu-id="ba872-177">조직에서 각 장치 프로필("테넌트")Azure Active Directory 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-177">Keep in mind that you can only have one of each device profile in your Azure Active Directory organization ("tenant").</span></span> <span data-ttu-id="ba872-178">예를 들어 중요한 데이터 장치 프로필에서 일부 사용자에 대해 AppLocker를 사용하지 않도록 설정할 것을 요청할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-178">For example, you can't request that the Sensitive data device profile disables AppLocker for only some of your users.</span></span> <span data-ttu-id="ba872-179">중요한 데이터 프로필이 있는 모든 디바이스의 구성이 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-179">All devices with the Sensitive data profile must have the same configuration.</span></span>

<span data-ttu-id="ba872-180">각 디바이스에는 프로필이 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-180">Each device can only have one profile.</span></span> <span data-ttu-id="ba872-181">여러 사용자가 특정 디바이스를 사용하는 경우 해당 장치의 모든 사용자가 동일한 구성을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba872-181">If a given device is used by more than one user, all users on that device will have the same configuration.</span></span>

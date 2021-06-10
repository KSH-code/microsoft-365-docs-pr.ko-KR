---
title: Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어
description: 끝점용 Microsoft Defender에 대한 Walk-through
keywords: 이동식 저장소 미디어
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fba74990d8e4465f957acda83e66e1dc43a317e8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841189"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="07936-104">Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="07936-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="07936-105">Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어를 사용하여 다음 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="07936-106">제외 또는 제외 없이 이동식 저장소에 대한 읽기, 쓰기 또는 실행 액세스 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="07936-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="07936-107">권한</span><span class="sxs-lookup"><span data-stu-id="07936-107">Privilege</span></span> |<span data-ttu-id="07936-108">사용 권한</span><span class="sxs-lookup"><span data-stu-id="07936-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="07936-109">Access</span><span class="sxs-lookup"><span data-stu-id="07936-109">Access</span></span>    |  <span data-ttu-id="07936-110">읽기, 쓰기, 실행</span><span class="sxs-lookup"><span data-stu-id="07936-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="07936-111">작업 모드</span><span class="sxs-lookup"><span data-stu-id="07936-111">Action Mode</span></span>    |    <span data-ttu-id="07936-112">감사, 허용, 방지</span><span class="sxs-lookup"><span data-stu-id="07936-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="07936-113">CSP 지원</span><span class="sxs-lookup"><span data-stu-id="07936-113">CSP Support</span></span>   |   <span data-ttu-id="07936-114">네.</span><span class="sxs-lookup"><span data-stu-id="07936-114">Yes</span></span>      |
|<span data-ttu-id="07936-115">GPO 지원</span><span class="sxs-lookup"><span data-stu-id="07936-115">GPO Support</span></span>    |   <span data-ttu-id="07936-116">네.</span><span class="sxs-lookup"><span data-stu-id="07936-116">Yes</span></span>      |
|<span data-ttu-id="07936-117">사용자 기반 지원</span><span class="sxs-lookup"><span data-stu-id="07936-117">User-based Support</span></span>     |   <span data-ttu-id="07936-118">네.</span><span class="sxs-lookup"><span data-stu-id="07936-118">Yes</span></span>      |
|<span data-ttu-id="07936-119">컴퓨터 기반 지원</span><span class="sxs-lookup"><span data-stu-id="07936-119">Machine-based Support</span></span>    |    <span data-ttu-id="07936-120">네.</span><span class="sxs-lookup"><span data-stu-id="07936-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="07936-121">엔드포인트 준비하기</span><span class="sxs-lookup"><span data-stu-id="07936-121">Prepare your endpoints</span></span>

<span data-ttu-id="07936-122">맬웨어 Storage 버전 **4.Storage 2103.3** 이상이 있는 Windows 10 장치에 이동식 액세스 제어를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="07936-123">**4.18.2104** 이상 : SerialNumberId 추가, VID_PID 파일 경로 기반 GPO 지원</span><span class="sxs-lookup"><span data-stu-id="07936-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support</span></span>

2. <span data-ttu-id="07936-124">**4.18.2105** 이상 : HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId에 대한 와일드카드 지원 추가, 특정 컴퓨터의 특정 사용자 조합, 제거 가능한 SSD(SanDisk Extreme SSD)/UAS(USB 연결된 SCSI) 지원</span><span class="sxs-lookup"><span data-stu-id="07936-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell 인터페이스":::

## <a name="policy-properties"></a><span data-ttu-id="07936-126">정책 속성</span><span class="sxs-lookup"><span data-stu-id="07936-126">Policy properties</span></span>

<span data-ttu-id="07936-127">다음 속성을 사용하여 이동식 저장소 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-127">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="07936-128">**속성 이름: 그룹 ID**</span><span class="sxs-lookup"><span data-stu-id="07936-128">**Property name: Group ID**</span></span>

1. <span data-ttu-id="07936-129">설명: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), 고유 ID는 그룹을 나타내며 정책에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07936-129">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="07936-130">**속성 이름: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="07936-130">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="07936-131">설명: 그룹에서 다루는 데 사용할 장치 속성을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-131">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="07936-132">그룹에서 다루는 데 사용할 장치 속성을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-132">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="07936-133">각 장치 속성에 대한 자세한 내용은 위의 **장치 속성** 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07936-133">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="07936-134">옵션:</span><span class="sxs-lookup"><span data-stu-id="07936-134">Options:</span></span>
    - <span data-ttu-id="07936-135">기본 ID</span><span class="sxs-lookup"><span data-stu-id="07936-135">Primary ID</span></span>
        - <span data-ttu-id="07936-136">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="07936-136">RemovableMediaDevices</span></span>
        - <span data-ttu-id="07936-137">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="07936-137">CdRomDevices</span></span>
    - <span data-ttu-id="07936-138">DeviceId</span><span class="sxs-lookup"><span data-stu-id="07936-138">DeviceId</span></span>
    - <span data-ttu-id="07936-139">HardwareId</span><span class="sxs-lookup"><span data-stu-id="07936-139">HardwareId</span></span>
    - <span data-ttu-id="07936-140">InstancePathId: InstancePathId는 시스템에서 장치를 고유하게 식별하는 문자열입니다(예: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&).</span><span class="sxs-lookup"><span data-stu-id="07936-140">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="07936-141">끝에 있는 번호(예:&**0)는** 사용 가능한 슬롯을 나타내며 디바이스에서 장치로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-141">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="07936-142">최상의 결과를 얻기 위해 끝에 와일드카드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-142">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="07936-143">예를 들어 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="07936-143">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="07936-144">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="07936-144">FriendlyNameId</span></span>
    - <span data-ttu-id="07936-145">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="07936-145">SerialNumberId</span></span>
    - <span data-ttu-id="07936-146">VID</span><span class="sxs-lookup"><span data-stu-id="07936-146">VID</span></span>
    - <span data-ttu-id="07936-147">PID</span><span class="sxs-lookup"><span data-stu-id="07936-147">PID</span></span>
    - <span data-ttu-id="07936-148">VID_PID</span><span class="sxs-lookup"><span data-stu-id="07936-148">VID_PID</span></span>
        - <span data-ttu-id="07936-149">0751_55E0: 이 정확한 VID/PID 쌍과 일치</span><span class="sxs-lookup"><span data-stu-id="07936-149">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="07936-150">_55E0: PID=55E0과 모든 미디어 일치</span><span class="sxs-lookup"><span data-stu-id="07936-150">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="07936-151">0751_: VID=0751과 모든 미디어 일치</span><span class="sxs-lookup"><span data-stu-id="07936-151">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="07936-152">**속성 이름: MatchType**</span><span class="sxs-lookup"><span data-stu-id="07936-152">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="07936-153">설명: DescriptorIDList에 여러 장치 속성이 사용되는 경우 MatchType은 관계를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-153">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="07936-154">옵션:</span><span class="sxs-lookup"><span data-stu-id="07936-154">Options:</span></span>
    - <span data-ttu-id="07936-155">MatchAll: DescriptorIdList의 모든 특성은 **And 관계가** 됩니다. 예를 들어 관리자가 DeviceID와 InstancePathID를 넣는 경우 연결된 모든 USB에 대해 시스템에서 USB가 두 값을 모두 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-155">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="07936-156">MatchAny: DescriptorIdList의 특성은 **Or 관계가** 됩니다. 예를 들어 관리자가 DeviceID 및 InstancePathID를 넣는 경우 연결된 모든 USB에 대해 USB에 **동일한 DeviceID** 또는 **InstanceID** 값이 있는 한 시스템에서 적용을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-156">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="07936-157">액세스 제어 정책 속성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-157">Following are the access control policy properties:</span></span>

<span data-ttu-id="07936-158">**속성 이름: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="07936-158">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="07936-159">설명: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), 고유한 ID는 정책을 나타내며 보고 및 문제 해결에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07936-159">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="07936-160">**속성 이름: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="07936-160">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="07936-161">설명: 정책을 적용할 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="07936-161">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="07936-162">여러 그룹이 추가된 경우 정책은 해당 그룹의 모든 미디어에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07936-162">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="07936-163">옵션: 이 인스턴스에서 그룹 ID/GUID를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-163">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="07936-164">다음 예에서는 GroupID의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07936-164">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="07936-165">**속성 이름: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="07936-165">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="07936-166">설명: 정책이 적용되지 않을 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="07936-166">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="07936-167">옵션: 이 인스턴스에서 그룹 ID/GUID를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-167">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="07936-168">**속성 이름: 항목 ID**</span><span class="sxs-lookup"><span data-stu-id="07936-168">**Property name: Entry ID**</span></span>

1. <span data-ttu-id="07936-169">설명: 하나의 PolicyRule에는 여러 항목이 있을 수 있습니다. 고유한 GUID가 있는 각 항목은 장치 제어에 한 가지 제한을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-169">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="07936-170">**속성 이름: Type**</span><span class="sxs-lookup"><span data-stu-id="07936-170">**Property name: Type**</span></span>

1. <span data-ttu-id="07936-171">설명: IncludedIDList에서 이동식 저장소 그룹에 대한 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-171">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="07936-172">적용: 허용 또는 거부</span><span class="sxs-lookup"><span data-stu-id="07936-172">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="07936-173">감사: AuditAllowed 또는 AuditDenied</span><span class="sxs-lookup"><span data-stu-id="07936-173">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="07936-174">옵션:</span><span class="sxs-lookup"><span data-stu-id="07936-174">Options:</span></span>
    - <span data-ttu-id="07936-175">허용</span><span class="sxs-lookup"><span data-stu-id="07936-175">Allow</span></span>
    - <span data-ttu-id="07936-176">거부</span><span class="sxs-lookup"><span data-stu-id="07936-176">Deny</span></span>
    - <span data-ttu-id="07936-177">AuditAllowed: 액세스가 허용되는 경우 알림 및 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-177">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="07936-178">AuditDenied: 액세스가 거부된 경우 알림 및 이벤트를 정의합니다. 거부 항목과 **함께 작업해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-178">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="07936-179">동일한 미디어에 대한 충돌 유형이 있는 경우 시스템은 정책의 첫 번째 형식을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-179">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="07936-180">충돌 형식의 예로는 **Allow** 및 **Deny가 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="07936-180">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="07936-181">**속성 이름: 옵션**</span><span class="sxs-lookup"><span data-stu-id="07936-181">**Property name: Options**</span></span>

1. <span data-ttu-id="07936-182">설명: 알림을 표시할지 여부를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-182">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="디바이스의 상태를 볼 수 있는 화면":::

1. <span data-ttu-id="07936-184">옵션: 0-4.</span><span class="sxs-lookup"><span data-stu-id="07936-184">Options: 0-4.</span></span> <span data-ttu-id="07936-185">허용 또는 거부 유형이 선택된 경우:</span><span class="sxs-lookup"><span data-stu-id="07936-185">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="07936-186">0: nothing</span><span class="sxs-lookup"><span data-stu-id="07936-186">0: nothing</span></span>
   - <span data-ttu-id="07936-187">4: 이 항목에 **대해 AuditAllowed** 및 **AuditDenied를** 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="07936-187">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="07936-188">**차단이 발생하고** **AuditDenied가 구성된** 경우에도 시스템에 알림이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-188">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="07936-189">**AuditAllowed 또는** **AuditDenied** 유형이 선택된 경우:</span><span class="sxs-lookup"><span data-stu-id="07936-189">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="07936-190">0: nothing</span><span class="sxs-lookup"><span data-stu-id="07936-190">0: nothing</span></span>
   - <span data-ttu-id="07936-191">1: 알림 표시</span><span class="sxs-lookup"><span data-stu-id="07936-191">1: show notification</span></span>
   - <span data-ttu-id="07936-192">2: 이벤트 보내기</span><span class="sxs-lookup"><span data-stu-id="07936-192">2: send event</span></span>
   - <span data-ttu-id="07936-193">3: 알림 표시 및 이벤트 보내기</span><span class="sxs-lookup"><span data-stu-id="07936-193">3: show notification and send event</span></span>

<span data-ttu-id="07936-194">**속성 이름: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="07936-194">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="07936-195">설명: 액세스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-195">Description: Defines the access.</span></span>

1. <span data-ttu-id="07936-196">옵션: 1-7:</span><span class="sxs-lookup"><span data-stu-id="07936-196">Options: 1-7:</span></span>
    - <span data-ttu-id="07936-197">1: 읽기</span><span class="sxs-lookup"><span data-stu-id="07936-197">1: Read</span></span>
    - <span data-ttu-id="07936-198">2: 쓰기</span><span class="sxs-lookup"><span data-stu-id="07936-198">2: Write</span></span>
    - <span data-ttu-id="07936-199">3: 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="07936-199">3: Read and Write</span></span>
    - <span data-ttu-id="07936-200">4: 실행</span><span class="sxs-lookup"><span data-stu-id="07936-200">4: Execute</span></span>
    - <span data-ttu-id="07936-201">5: 읽기 및 실행</span><span class="sxs-lookup"><span data-stu-id="07936-201">5: Read and Execute</span></span>
    - <span data-ttu-id="07936-202">6: 쓰기 및 실행</span><span class="sxs-lookup"><span data-stu-id="07936-202">6: Write and Execute</span></span>
    - <span data-ttu-id="07936-203">7: 읽기 및 쓰기 및 실행</span><span class="sxs-lookup"><span data-stu-id="07936-203">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="07936-204">일반적인 이동식 Storage 액세스 제어 시나리오</span><span class="sxs-lookup"><span data-stu-id="07936-204">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="07936-205">Microsoft Defender for Endpoint 이동식 Storage 액세스 제어에 익숙해지기 위해 따라야 할 몇 가지 일반적인 시나리오를 준비했습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-205">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="07936-206">시나리오 1: 모든 웹 에 대한 쓰기 및 실행 액세스를 방지하지만 승인된 특정 USB는 허용</span><span class="sxs-lookup"><span data-stu-id="07936-206">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="07936-207">그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="07936-207">Create groups</span></span>
    1. <span data-ttu-id="07936-208">그룹 1: 모든 이동식 저장소 및 CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="07936-208">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="07936-209">이동식 저장소 및 CD/DVD의 예로는 그룹 **9b28fae8-72f7-4267-a1a5-685f747a7146** 샘플의 모든 이동식 Storage 및 [CD-DVD](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Group.xml파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-209">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="07936-210">그룹 2: 장치 속성에 따라 승인된 USB.</span><span class="sxs-lookup"><span data-stu-id="07936-210">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="07936-211">이 사용 사례의 예로는 예제 승인된 USB 파일에서 인스턴스 ID – 그룹 **65fa649a-a111-4912-9294-fb6337a25038** [Group.xml이](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-211">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="07936-212">값으로 `&` `&amp;` 바꾸야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-212">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="07936-213">정책 생성</span><span class="sxs-lookup"><span data-stu-id="07936-213">Create policy</span></span>
    1. <span data-ttu-id="07936-214">정책 1: 쓰기 및 액세스 실행을 차단하지만 승인된 USB는 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-214">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="07936-215">이 사용 사례의 예는 예제 시나리오 1 쓰기 차단 및 실행에서 PolicyRule **c544a991-5786-4402-949e-a032cb790d0e이지만** 승인된 [USB는](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) .xml.</span><span class="sxs-lookup"><span data-stu-id="07936-215">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="07936-216">정책 2: 허용된 USB에 대한 쓰기 및 실행 액세스를 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-216">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="07936-217">이 사용 사례의 예는 예제 시나리오 [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 감사 쓰기 및 승인된 USBs.xml파일에 대한 액세스 실행의 PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c입니다.**</span><span class="sxs-lookup"><span data-stu-id="07936-217">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="07936-218">시나리오 2: 승인되지 않은 특정 USB를 모두 차단하지만 모든 쓰기 및 실행 액세스 감사</span><span class="sxs-lookup"><span data-stu-id="07936-218">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="07936-219">그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="07936-219">Create groups</span></span>
    1. <span data-ttu-id="07936-220">그룹 1: 모든 이동식 저장소 및 CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="07936-220">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="07936-221">이 사용 사례의 예는 샘플 Any Removable Storage [및 CD-DVD](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Group.xml파일의 Group **9b28fae8-72f7-4267-a1a5-685f747a7146입니다.**</span><span class="sxs-lookup"><span data-stu-id="07936-221">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="07936-222">그룹 2: 장치 속성에 따라 승인되지 않은 USB(예: 공급업체 ID/ 제품 ID, 식별 이름 – 그룹 **65fa649a-a111-4912-9294-fb6337a25038)** 샘플에서 승인되지 않은 [USB](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Group.xml.</span><span class="sxs-lookup"><span data-stu-id="07936-222">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="07936-223">값으로 `&` `&amp;` 바꾸야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-223">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="07936-224">정책 생성</span><span class="sxs-lookup"><span data-stu-id="07936-224">Create policy</span></span>
    1. <span data-ttu-id="07936-225">정책 1: 승인되지 않은 특정 USB를 모두 차단하지만 모든에 대한 쓰기 및 실행 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-225">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="07936-226">이 사용 사례의 예는 예제 시나리오 2 감사 쓰기 및 실행의 예제 시나리오 2에서 PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98입니다.** 승인되지 않은 특정 USBs.xml파일에 대한 액세스는 모두 차단합니다. [](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="07936-226">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="07936-227">정책 2: 다른 사용자에 대한 쓰기 및 실행 액세스를 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-227">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="07936-228">이 사용 사례의 예는 예제 시나리오 [others.xml2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 감사 쓰기 및 실행 파일에서 PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48입니다.**</span><span class="sxs-lookup"><span data-stu-id="07936-228">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="07936-229">그룹 정책을 통해 정책 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="07936-229">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="07936-230">이동식 Storage 액세스 제어 기능을 사용하면 그룹 정책을 통해 사용자 또는 장치 또는 둘 다에 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-230">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="07936-231">라이선싱</span><span class="sxs-lookup"><span data-stu-id="07936-231">Licensing</span></span>

<span data-ttu-id="07936-232">이동식 액세스 제어를 Storage 시작하기 전에 [구독을 Microsoft 365 합니다.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="07936-232">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="07936-233">이동식 액세스 Storage 액세스 제어에 액세스하고 사용하려면 액세스 Microsoft 365 E3 또는 Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="07936-233">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="07936-234">그룹 정책을 통해 정책 배포</span><span class="sxs-lookup"><span data-stu-id="07936-234">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="07936-235">모든 그룹을 하나의 `<Groups>` `</Groups>` xml 파일로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-235">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="07936-236">다음 이미지는 시나리오 1: 쓰기 금지 및 모든 승인된 USB에 대한 액세스 실행을 허용하는 [예제를 보여 줍니다.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="07936-236">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="장치에서 승인된 특정 USB를 허용하는 구성 설정을 표시하는 화면":::
    
2. <span data-ttu-id="07936-238">모든 규칙을 하나의 `<PolicyRules>` `</PolicyRules>` xml 파일로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-238">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="07936-239">특정 사용자를 제한하려는 경우 Entry에 SID 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-239">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="07936-240">정책 Entry에 SID가 없는 경우 항목은 컴퓨터의 모든 로그인 인스턴스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07936-240">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="07936-241">다음 이미지는 SID 속성의 사용을 보여 주며 시나리오 [1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)모든 승인된 USB는 허용하지만 모든 사용자에 대해 쓰기 및 실행 액세스 금지의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07936-241">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="SID 속성 특성의 사용을 나타내는 코드를 표시하는 화면":::

3. <span data-ttu-id="07936-243">네트워크 공유 폴더에 규칙 및 그룹 XML 파일을 저장하고 네트워크 공유 폴더 경로를 그룹 정책 설정으로 넣습니다. 컴퓨터 구성 -> 관리 템플릿 -> Windows 구성 요소 **-> Microsoft Defender 바이러스 백신 -> 장치 제어: '장치** 제어 정책 그룹 정의' 및 '장치 제어 정책 규칙 정의'</span><span class="sxs-lookup"><span data-stu-id="07936-243">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="07936-244">대상 컴퓨터는 정책을 사용하려면 네트워크 공유에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-244">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="07936-245">그러나 정책을 읽은 후 컴퓨터 재부팅 후에도 네트워크 공유 연결이 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-245">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="장치 제어 화면":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="07936-247">Intune OMA-URI를 통해 정책 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="07936-247">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="07936-248">이동식 Storage 액세스 제어 기능을 사용하면 OMA-URI를 통해 사용자 또는 장치 또는 둘 다에 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-248">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="07936-249">라이선싱</span><span class="sxs-lookup"><span data-stu-id="07936-249">Licensing</span></span>

<span data-ttu-id="07936-250">이동식 액세스 제어를 Storage 시작하기 전에 [구독을 Microsoft 365 합니다.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="07936-250">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="07936-251">이동식 액세스 Storage 액세스 제어에 액세스하고 사용하려면 액세스 Microsoft 365 E3 또는 Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="07936-251">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="07936-252">사용 권한</span><span class="sxs-lookup"><span data-stu-id="07936-252">Permission</span></span>

<span data-ttu-id="07936-253">Intune에서 정책 배포의 경우 계정에 장치 구성 프로필을 생성, 편집, 업데이트 또는 삭제할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-253">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="07936-254">이러한 사용 권한으로 사용자 지정 역할을 만들거나 기본 제공 역할을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-254">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="07936-255">정책 및 프로필 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="07936-255">Policy and profile Manager role</span></span>
- <span data-ttu-id="07936-256">장치 구성 프로필에 대해 보고서 만들기/편집/업데이트/읽기/삭제/보기 권한이 설정되어 있는 사용자 지정 역할</span><span class="sxs-lookup"><span data-stu-id="07936-256">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="07936-257">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="07936-257">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="07936-258">OMA-URI를 통해 정책 배포</span><span class="sxs-lookup"><span data-stu-id="07936-258">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="07936-259">**Microsoft Endpoint Manager 관리 센터( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="07936-259">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="07936-260">각 그룹에 대해 OMA-URI 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-260">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="07936-261">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="07936-261">OMA-URI:</span></span>

      <span data-ttu-id="07936-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="07936-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="07936-263">예를 들어 샘플의 이동식 저장소 및 **CD/DVD** 그룹의 경우 링크는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-263">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="07936-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="07936-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="07936-265">데이터 형식: 문자열(XML 파일)</span><span class="sxs-lookup"><span data-stu-id="07936-265">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING 데이터 형식의 xml 파일":::

2. <span data-ttu-id="07936-267">각 정책에 대해 OMA-URI도 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-267">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="07936-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="07936-268">OMA-URI:</span></span>

      <span data-ttu-id="07936-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="07936-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="07936-270">예를 들어 예제에서 승인된 **USB** 규칙을 허용하지만 쓰기 차단 및 실행에 대한 링크는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-270">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="07936-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="07936-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="07936-272">데이터 형식: 문자열(XML 파일)</span><span class="sxs-lookup"><span data-stu-id="07936-272">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="STRING 데이터 형식에 대한 XML 파일 표시":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="07936-274">Intune 사용자 인터페이스를 사용하여 정책 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="07936-274">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="07936-275">이 기능(Microsoft Endpoint Manager 관리 센터( https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control)은 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07936-275">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="07936-276">끝점용 Microsoft Defender에서 장치 Storage 이동식 액세스 제어 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="07936-276">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="07936-277">보안 Microsoft 365 포털에는 액세스 제어를 통해 장치 제어 이동식 이동식 액세스 제어에 의해 Storage 저장소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07936-277">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="07936-278">Microsoft 365 보안에 액세스하려면 다음 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07936-278">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="07936-279">Microsoft 365 E5 보고용 보고서</span><span class="sxs-lookup"><span data-stu-id="07936-279">Microsoft 365 for E5 reporting</span></span>

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="이동식 저장소의 차단을 표시하는 화면":::

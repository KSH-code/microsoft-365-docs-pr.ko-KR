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
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8b32ab5162e0022d9500f7ddba2fe5bbca1017e7
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229578"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="97272-104">Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="97272-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="97272-105">Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어를 사용하여 다음 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="97272-106">제외 또는 제외 없이 이동식 저장소에 대한 읽기, 쓰기 또는 실행 액세스 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="97272-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="97272-107">권한</span><span class="sxs-lookup"><span data-stu-id="97272-107">Privilege</span></span> |<span data-ttu-id="97272-108">사용 권한</span><span class="sxs-lookup"><span data-stu-id="97272-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="97272-109">Access</span><span class="sxs-lookup"><span data-stu-id="97272-109">Access</span></span>    |  <span data-ttu-id="97272-110">읽기, 쓰기, 실행</span><span class="sxs-lookup"><span data-stu-id="97272-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="97272-111">작업 모드</span><span class="sxs-lookup"><span data-stu-id="97272-111">Action Mode</span></span>    |    <span data-ttu-id="97272-112">감사, 허용, 방지</span><span class="sxs-lookup"><span data-stu-id="97272-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="97272-113">CSP 지원</span><span class="sxs-lookup"><span data-stu-id="97272-113">CSP Support</span></span>   |   <span data-ttu-id="97272-114">예</span><span class="sxs-lookup"><span data-stu-id="97272-114">Yes</span></span>      |
|<span data-ttu-id="97272-115">GPO 지원</span><span class="sxs-lookup"><span data-stu-id="97272-115">GPO Support</span></span>    |   <span data-ttu-id="97272-116">예</span><span class="sxs-lookup"><span data-stu-id="97272-116">Yes</span></span>      |
|<span data-ttu-id="97272-117">사용자 기반 지원</span><span class="sxs-lookup"><span data-stu-id="97272-117">User-based Support</span></span>     |   <span data-ttu-id="97272-118">예</span><span class="sxs-lookup"><span data-stu-id="97272-118">Yes</span></span>      |
|<span data-ttu-id="97272-119">컴퓨터 기반 지원</span><span class="sxs-lookup"><span data-stu-id="97272-119">Machine-based Support</span></span>    |    <span data-ttu-id="97272-120">예</span><span class="sxs-lookup"><span data-stu-id="97272-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="97272-121">엔드포인트 준비하기</span><span class="sxs-lookup"><span data-stu-id="97272-121">Prepare your endpoints</span></span>

<span data-ttu-id="97272-122">이동식 Storage 맬웨어 방지 Windows 10 **버전이 4.18.2103.3** 이상인 Windows 10 장치에 액세스 제어를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="97272-123">**4.18.2104** 이상 : SerialNumberId 추가, VID_PID, 파일 경로 기반 GPO 지원, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="97272-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="97272-124">**4.18.2105** 이상 : HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId에 대한 와일드카드 지원 추가, 특정 컴퓨터의 특정 사용자 조합, 제거 가능한 SSD(SanDisk Extreme SSD)/UAS(USB 연결된 SCSI) 지원</span><span class="sxs-lookup"><span data-stu-id="97272-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell 인터페이스":::

> [!NOTE]
> <span data-ttu-id="97272-126">모든 Windows 보안 활성화할 필요는 없습니다. 상태와는 독립적으로 이동식 Storage 제어를 실행할 Windows 보안 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-126">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="97272-127">정책 속성</span><span class="sxs-lookup"><span data-stu-id="97272-127">Policy properties</span></span>

<span data-ttu-id="97272-128">다음 속성을 사용하여 이동식 저장소 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-128">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="97272-129">**속성 이름: 그룹 ID**</span><span class="sxs-lookup"><span data-stu-id="97272-129">**Property name: Group Id**</span></span>

1. <span data-ttu-id="97272-130">설명: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), 고유 ID는 그룹을 나타내며 정책에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97272-130">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="97272-131">**속성 이름: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="97272-131">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="97272-132">설명: 그룹에서 다루는 데 사용할 장치 속성을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-132">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="97272-133">그룹에서 다루는 데 사용할 장치 속성을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-133">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="97272-134">각 장치 속성에 대한 자세한 내용은 위의 **장치 속성** 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97272-134">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="97272-135">옵션:</span><span class="sxs-lookup"><span data-stu-id="97272-135">Options:</span></span>

    - <span data-ttu-id="97272-136">기본 ID</span><span class="sxs-lookup"><span data-stu-id="97272-136">Primary ID</span></span>
        - <span data-ttu-id="97272-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="97272-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="97272-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="97272-138">CdRomDevices</span></span>
    - <span data-ttu-id="97272-139">DeviceId</span><span class="sxs-lookup"><span data-stu-id="97272-139">DeviceId</span></span>
    - <span data-ttu-id="97272-140">HardwareId</span><span class="sxs-lookup"><span data-stu-id="97272-140">HardwareId</span></span>
    - <span data-ttu-id="97272-141">InstancePathId: InstancePathId는 시스템에서 장치를 고유하게 식별하는 문자열입니다(예: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&).</span><span class="sxs-lookup"><span data-stu-id="97272-141">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="97272-142">끝에 있는 번호(예:&**0)는** 사용 가능한 슬롯을 나타내며 디바이스에서 장치로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-142">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="97272-143">최상의 결과를 얻기 위해 끝에 와일드카드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-143">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="97272-144">예를 들어 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="97272-144">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="97272-145">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="97272-145">FriendlyNameId</span></span>
    - <span data-ttu-id="97272-146">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="97272-146">SerialNumberId</span></span>
    - <span data-ttu-id="97272-147">VID</span><span class="sxs-lookup"><span data-stu-id="97272-147">VID</span></span>
    - <span data-ttu-id="97272-148">PID</span><span class="sxs-lookup"><span data-stu-id="97272-148">PID</span></span>
    - <span data-ttu-id="97272-149">VID_PID</span><span class="sxs-lookup"><span data-stu-id="97272-149">VID_PID</span></span>
        - <span data-ttu-id="97272-150">0751_55E0: 이 정확한 VID/PID 쌍과 일치</span><span class="sxs-lookup"><span data-stu-id="97272-150">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="97272-151">_55E0: PID=55E0과 모든 미디어 일치</span><span class="sxs-lookup"><span data-stu-id="97272-151">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="97272-152">0751_: VID=0751과 모든 미디어 일치</span><span class="sxs-lookup"><span data-stu-id="97272-152">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="97272-153">**속성 이름: MatchType**</span><span class="sxs-lookup"><span data-stu-id="97272-153">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="97272-154">설명: DescriptorIDList에 여러 장치 속성이 사용되는 경우 MatchType은 관계를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-154">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="97272-155">옵션:</span><span class="sxs-lookup"><span data-stu-id="97272-155">Options:</span></span>

    - <span data-ttu-id="97272-156">MatchAll: DescriptorIdList의 모든 특성은 **And 관계가** 됩니다. 예를 들어 관리자가 DeviceID와 InstancePathID를 넣는 경우 연결된 모든 USB에 대해 시스템에서 USB가 두 값을 모두 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-156">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="97272-157">MatchAny: DescriptorIdList의 특성은 **Or 관계가** 됩니다. 예를 들어 관리자가 DeviceID 및 InstancePathID를 넣는 경우 연결된 모든 USB에 대해 USB에 **동일한 DeviceID** 또는 **InstanceID** 값이 있는 한 시스템에서 적용을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-157">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="97272-158">액세스 제어 정책 속성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-158">Following are the access control policy properties:</span></span>

<span data-ttu-id="97272-159">**속성 이름: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="97272-159">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="97272-160">설명: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), 고유한 ID는 정책을 나타내며 보고 및 문제 해결에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97272-160">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="97272-161">**속성 이름: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="97272-161">**Property name: IncludedIdList**</span></span>

2. <span data-ttu-id="97272-162">설명: 정책을 적용할 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="97272-162">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="97272-163">여러 그룹이 추가된 경우 정책은 해당 그룹의 모든 미디어에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97272-163">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

3. <span data-ttu-id="97272-164">옵션: 이 인스턴스에서 그룹 ID/GUID를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-164">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="97272-165">다음 예에서는 GroupID의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97272-165">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="97272-166">**속성 이름: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="97272-166">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="97272-167">설명: 정책이 적용되지 않을 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="97272-167">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="97272-168">옵션: 이 인스턴스에서 그룹 ID/GUID를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-168">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="97272-169">**속성 이름: 항목 ID**</span><span class="sxs-lookup"><span data-stu-id="97272-169">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="97272-170">설명: 하나의 PolicyRule에는 여러 항목이 있을 수 있습니다. 고유한 GUID가 있는 각 항목은 장치 제어에 한 가지 제한을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-170">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="97272-171">**속성 이름: Type**</span><span class="sxs-lookup"><span data-stu-id="97272-171">**Property name: Type**</span></span>

1. <span data-ttu-id="97272-172">설명: IncludedIDList에서 이동식 저장소 그룹에 대한 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-172">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="97272-173">적용: 허용 또는 거부</span><span class="sxs-lookup"><span data-stu-id="97272-173">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="97272-174">감사: AuditAllowed 또는 AuditDenied</span><span class="sxs-lookup"><span data-stu-id="97272-174">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="97272-175">옵션:</span><span class="sxs-lookup"><span data-stu-id="97272-175">Options:</span></span>

    - <span data-ttu-id="97272-176">허용</span><span class="sxs-lookup"><span data-stu-id="97272-176">Allow</span></span>
    - <span data-ttu-id="97272-177">거부</span><span class="sxs-lookup"><span data-stu-id="97272-177">Deny</span></span>
    - <span data-ttu-id="97272-178">AuditAllowed: 액세스가 허용되는 경우 알림 및 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-178">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="97272-179">AuditDenied: 액세스가 거부된 경우 알림 및 이벤트를 정의합니다. 거부 항목과 **함께 작업해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-179">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="97272-180">동일한 미디어에 대한 충돌 유형이 있는 경우 시스템은 정책의 첫 번째 형식을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-180">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="97272-181">충돌 형식의 예로는 **Allow** 및 **Deny가 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="97272-181">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="97272-182">**속성 이름: Sid**</span><span class="sxs-lookup"><span data-stu-id="97272-182">**Property name: Sid**</span></span>

<span data-ttu-id="97272-183">설명: 특정 사용자 또는 사용자 그룹에 이 정책을 적용할지 여부를 정의합니다. 하나의 항목은 최대 하나의 Sid를 사용할 수 있으며 Sid가 없는 항목은 컴퓨터 위에 정책을 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97272-183">Description: Defines whether apply this policy over specific user or user group; one entry can have maximum one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="97272-184">**속성 이름: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="97272-184">**Property name: ComputerSid**</span></span>

<span data-ttu-id="97272-185">설명: 특정 컴퓨터 또는 컴퓨터 그룹에 이 정책을 적용할지 여부를 정의합니다. 하나의 항목은 ComputerSid를 최대 하나만 사용할 수 있으며, ComputerSid가 없는 항목은 컴퓨터에 정책을 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97272-185">Description: Defines whether apply this policy over specific machine or machine group; one entry can have maximum one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="97272-186">특정 사용자 및 특정 컴퓨터에 Entry를 적용하려면 Sid와 ComputerSid를 모두 동일한 항목에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-186">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="97272-187">**속성 이름: 옵션**</span><span class="sxs-lookup"><span data-stu-id="97272-187">**Property name: Options**</span></span>

<span data-ttu-id="97272-188">설명: 알림을 표시할지 여부를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-188">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="디바이스의 상태를 볼 수 있는 화면":::

<span data-ttu-id="97272-190">옵션: 0-4.</span><span class="sxs-lookup"><span data-stu-id="97272-190">Options: 0-4.</span></span> <span data-ttu-id="97272-191">허용 또는 거부 유형이 선택된 경우:</span><span class="sxs-lookup"><span data-stu-id="97272-191">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="97272-192">0: nothing</span><span class="sxs-lookup"><span data-stu-id="97272-192">0: nothing</span></span>
   - <span data-ttu-id="97272-193">4: 이 항목에 **대해 AuditAllowed** 및 **AuditDenied를** 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="97272-193">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="97272-194">**차단이 발생하고** **AuditDenied가 구성된** 경우에도 시스템에 알림이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-194">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="97272-195">**AuditAllowed 또는** **AuditDenied** 유형이 선택된 경우:</span><span class="sxs-lookup"><span data-stu-id="97272-195">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="97272-196">0: nothing</span><span class="sxs-lookup"><span data-stu-id="97272-196">0: nothing</span></span>
   - <span data-ttu-id="97272-197">1: 알림 표시</span><span class="sxs-lookup"><span data-stu-id="97272-197">1: show notification</span></span>
   - <span data-ttu-id="97272-198">2: 이벤트 보내기</span><span class="sxs-lookup"><span data-stu-id="97272-198">2: send event</span></span>
   - <span data-ttu-id="97272-199">3: 알림 표시 및 이벤트 보내기</span><span class="sxs-lookup"><span data-stu-id="97272-199">3: show notification and send event</span></span>

<span data-ttu-id="97272-200">**속성 이름: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="97272-200">**Property name: AccessMask**</span></span>

<span data-ttu-id="97272-201">설명: 액세스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-201">Description: Defines the access.</span></span>

<span data-ttu-id="97272-202">옵션 1-7:</span><span class="sxs-lookup"><span data-stu-id="97272-202">Options 1-7:</span></span>
  - <span data-ttu-id="97272-203">1: 읽기</span><span class="sxs-lookup"><span data-stu-id="97272-203">1: Read</span></span>
  - <span data-ttu-id="97272-204">2: 쓰기</span><span class="sxs-lookup"><span data-stu-id="97272-204">2: Write</span></span>
  - <span data-ttu-id="97272-205">3: 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="97272-205">3: Read and Write</span></span>
  - <span data-ttu-id="97272-206">4: 실행</span><span class="sxs-lookup"><span data-stu-id="97272-206">4: Execute</span></span>
  - <span data-ttu-id="97272-207">5: 읽기 및 실행</span><span class="sxs-lookup"><span data-stu-id="97272-207">5: Read and Execute</span></span>
  - <span data-ttu-id="97272-208">6: 쓰기 및 실행</span><span class="sxs-lookup"><span data-stu-id="97272-208">6: Write and Execute</span></span>
  - <span data-ttu-id="97272-209">7: 읽기 및 쓰기 및 실행</span><span class="sxs-lookup"><span data-stu-id="97272-209">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="97272-210">일반적인 이동식 Storage 액세스 제어 시나리오</span><span class="sxs-lookup"><span data-stu-id="97272-210">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="97272-211">Microsoft Defender for Endpoint 이동식 Storage 액세스 제어에 익숙해지기 위해 따라야 할 몇 가지 일반적인 시나리오를 준비했습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-211">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="97272-212">시나리오 1: 모든 웹 에 대한 쓰기 및 실행 액세스를 방지하지만 승인된 특정 USB는 허용</span><span class="sxs-lookup"><span data-stu-id="97272-212">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="97272-213">그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="97272-213">Create groups</span></span>

    1. <span data-ttu-id="97272-214">그룹 1: 모든 이동식 저장소 및 CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="97272-214">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="97272-215">이동식 저장소 및 CD/DVD의 예로는 그룹 **9b28fae8-72f7-4267-a1a5-685f747a7146** 샘플의 모든 이동식 Storage 및 [CD-DVD](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Group.xml파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-215">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="97272-216">그룹 2: 장치 속성에 따라 승인된 USB.</span><span class="sxs-lookup"><span data-stu-id="97272-216">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="97272-217">이 사용 사례의 예로는 예제 승인된 USB 파일에서 인스턴스 ID – 그룹 **65fa649a-a111-4912-9294-fb6337a25038** [Group.xml이](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-217">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="97272-218">값으로 `&` `&amp;` 바꾸야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-218">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="97272-219">정책 생성</span><span class="sxs-lookup"><span data-stu-id="97272-219">Create policy</span></span>

    1. <span data-ttu-id="97272-220">정책 1: 쓰기 및 액세스 실행을 차단하지만 승인된 USB는 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-220">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="97272-221">이 사용 사례의 예는 예제 시나리오 [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 쓰기 차단 및 실행에서 PolicyRule **c544a991-5786-4402-949e-a032cb790d0e이지만** 승인된 USBs.xml파일을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-221">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="97272-222">정책 2: 허용된 USB에 대한 쓰기 및 실행 액세스를 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-222">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="97272-223">이 사용 사례의 예는 예제 시나리오 [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 감사 쓰기 및 승인된 USBs.xml파일에 대한 액세스 실행의 PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c입니다.**</span><span class="sxs-lookup"><span data-stu-id="97272-223">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="97272-224">시나리오 2: 승인되지 않은 특정 USB를 모두 차단하지만 모든 쓰기 및 실행 액세스 감사</span><span class="sxs-lookup"><span data-stu-id="97272-224">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="97272-225">그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="97272-225">Create groups</span></span>

    1. <span data-ttu-id="97272-226">그룹 1: 모든 이동식 저장소 및 CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="97272-226">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="97272-227">이 사용 사례의 예는 샘플 Any Removable Storage [및 CD-DVD](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Group.xml파일의 Group **9b28fae8-72f7-4267-a1a5-685f747a7146입니다.**</span><span class="sxs-lookup"><span data-stu-id="97272-227">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="97272-228">그룹 2: 장치 속성에 따라 승인되지 않은 USB(예: 공급업체 ID/ 제품 ID, 식별 이름 – 그룹 **65fa649a-a111-4912-9294-fb6337a25038)** 샘플에서 승인되지 않은 [USB](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Group.xml.</span><span class="sxs-lookup"><span data-stu-id="97272-228">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="97272-229">값으로 `&` `&amp;` 바꾸야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-229">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="97272-230">정책 생성</span><span class="sxs-lookup"><span data-stu-id="97272-230">Create policy</span></span>

    1. <span data-ttu-id="97272-231">정책 1: 승인되지 않은 특정 USB를 모두 차단하지만 모든에 대한 쓰기 및 실행 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-231">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="97272-232">이 사용 사례의 예는 예제 시나리오 2 감사 쓰기 및 실행의 예제 시나리오 2에서 PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98입니다.** 승인되지 않은 특정 USBs.xml파일에 대한 액세스는 모두 차단합니다. [](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="97272-232">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="97272-233">정책 2: 다른 사용자에 대한 쓰기 및 실행 액세스를 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-233">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="97272-234">이 사용 사례의 예는 예제 시나리오 [others.xml2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 감사 쓰기 및 실행 파일에서 PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48입니다.**</span><span class="sxs-lookup"><span data-stu-id="97272-234">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="97272-235">그룹 정책을 통해 정책 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="97272-235">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="97272-236">이동식 Storage 액세스 제어 기능을 사용하면 그룹 정책을 통해 사용자 또는 장치 또는 둘 다에 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-236">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="97272-237">라이선싱</span><span class="sxs-lookup"><span data-stu-id="97272-237">Licensing</span></span>

<span data-ttu-id="97272-238">이동식 액세스 제어를 Storage 시작하기 전에 [구독을 Microsoft 365 합니다.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="97272-238">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="97272-239">이동식 액세스 Storage 액세스 제어에 액세스하고 사용하려면 액세스 Microsoft 365 E3 또는 Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="97272-239">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="97272-240">그룹 정책을 통해 정책 배포</span><span class="sxs-lookup"><span data-stu-id="97272-240">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="97272-241">모든 그룹을 하나의 `<Groups>` `</Groups>` xml 파일로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-241">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="97272-242">다음 이미지는 시나리오 1: 쓰기 금지 및 모든 승인된 USB에 대한 액세스 실행을 허용하는 [예제를 보여 줍니다.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="97272-242">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="장치에서 승인된 특정 USB를 허용하는 구성 설정을 표시하는 화면":::
    
2. <span data-ttu-id="97272-244">모든 규칙을 하나의 `<PolicyRules>` `</PolicyRules>` xml 파일로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-244">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="97272-245">특정 사용자를 제한하려는 경우 Entry에 SID 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-245">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="97272-246">정책 Entry에 SID가 없는 경우 항목은 컴퓨터의 모든 로그인 인스턴스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97272-246">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="97272-247">다음 이미지는 SID 속성의 사용을 보여 주며 시나리오 [1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)모든 승인된 USB는 허용하지만 모든 사용자에 대해 쓰기 및 실행 액세스 금지의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97272-247">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="SID 속성 특성의 사용을 나타내는 코드를 표시하는 화면":::

3. <span data-ttu-id="97272-249">네트워크 공유 폴더에 규칙 및 그룹 XML 파일을 저장하고 네트워크 공유 폴더 경로를 그룹 정책 설정으로 넣습니다. 컴퓨터 구성 -> 관리 템플릿 -> Windows 구성 요소 **-> Microsoft Defender 바이러스 백신 -> 장치 제어: '장치** 제어 정책 그룹 정의' 및 '장치 제어 정책 규칙 정의'</span><span class="sxs-lookup"><span data-stu-id="97272-249">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="97272-250">대상 컴퓨터는 정책을 사용하려면 네트워크 공유에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-250">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="97272-251">그러나 정책을 읽은 후 컴퓨터 재부팅 후에도 네트워크 공유 연결이 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-251">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="장치 제어 화면":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="97272-253">Intune OMA-URI를 통해 정책 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="97272-253">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="97272-254">이동식 Storage 액세스 제어 기능을 사용하면 OMA-URI를 통해 사용자 또는 장치 또는 둘 다에 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-254">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="97272-255">라이선싱</span><span class="sxs-lookup"><span data-stu-id="97272-255">Licensing</span></span>

<span data-ttu-id="97272-256">이동식 액세스 제어를 Storage 시작하기 전에 [구독을 Microsoft 365 합니다.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="97272-256">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="97272-257">이동식 액세스 Storage 액세스 제어에 액세스하고 사용하려면 액세스 Microsoft 365 E3 또는 Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="97272-257">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="97272-258">사용 권한</span><span class="sxs-lookup"><span data-stu-id="97272-258">Permission</span></span>

<span data-ttu-id="97272-259">Intune에서 정책 배포의 경우 계정에 장치 구성 프로필을 생성, 편집, 업데이트 또는 삭제할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-259">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="97272-260">이러한 사용 권한으로 사용자 지정 역할을 만들거나 기본 제공 역할을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-260">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="97272-261">정책 및 프로필 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="97272-261">Policy and profile Manager role</span></span>
- <span data-ttu-id="97272-262">장치 구성 프로필에 대해 보고서 만들기/편집/업데이트/읽기/삭제/보기 권한이 설정되어 있는 사용자 지정 역할</span><span class="sxs-lookup"><span data-stu-id="97272-262">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="97272-263">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="97272-263">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="97272-264">OMA-URI를 통해 정책 배포</span><span class="sxs-lookup"><span data-stu-id="97272-264">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="97272-265">**Microsoft Endpoint Manager 관리 센터( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="97272-265">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="97272-266">각 그룹에 대해 OMA-URI 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-266">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="97272-267">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="97272-267">OMA-URI:</span></span>

      <span data-ttu-id="97272-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="97272-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="97272-269">예를 들어 샘플의 이동식 저장소 및 **CD/DVD** 그룹의 경우 링크는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-269">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="97272-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="97272-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="97272-271">데이터 형식: 문자열(XML 파일)</span><span class="sxs-lookup"><span data-stu-id="97272-271">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING 데이터 형식의 xml 파일":::

2. <span data-ttu-id="97272-273">각 정책에 대해 OMA-URI도 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-273">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="97272-274">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="97272-274">OMA-URI:</span></span>

      <span data-ttu-id="97272-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="97272-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="97272-276">예를 들어 예제에서 승인된 **USB** 규칙을 허용하지만 쓰기 차단 및 실행에 대한 링크는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-276">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="97272-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="97272-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="97272-278">데이터 형식: 문자열(XML 파일)</span><span class="sxs-lookup"><span data-stu-id="97272-278">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="STRING 데이터 형식에 대한 XML 파일 표시":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="97272-280">Intune 사용자 인터페이스를 사용하여 정책 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="97272-280">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="97272-281">이 기능(Microsoft Endpoint Manager 관리 센터( https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control)은 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-281">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="97272-282">끝점용 Microsoft Defender에서 장치 Storage 이동식 액세스 제어 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="97272-282">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="97272-283">보안 Microsoft 365 포털에는 액세스 제어를 통해 장치 제어 이동식 이동식 액세스 제어에 의해 Storage 저장소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="97272-283">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="97272-284">Microsoft 365 보안에 액세스하려면 다음 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-284">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="97272-285">Microsoft 365 E5 보고용 보고서</span><span class="sxs-lookup"><span data-stu-id="97272-285">Microsoft 365 for E5 reporting</span></span>

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

## <a name="frequently-asked-questions"></a><span data-ttu-id="97272-287">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="97272-287">Frequently asked questions</span></span>
<span data-ttu-id="97272-288">**최대 USB 수에 대한 이동식 저장소 미디어 제한은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="97272-288">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="97272-289">100,000 미디어(최대 7MB) 크기의 USB 그룹 하나를 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-289">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="97272-290">이 정책은 성능 문제 없이 Intune 및 GPO에서 모두 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-290">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="97272-291">**정책이 작동하지 않는 이유는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="97272-291">**Why does the policy not work?**</span></span>

<span data-ttu-id="97272-292">가장 일반적인 이유는 필수 맬웨어 방지 클라이언트 [버전이 없습니다.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)</span><span class="sxs-lookup"><span data-stu-id="97272-292">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="97272-293">예를 들어 XML 파일의 "&" 문자에 올바른 표시 형식을 사용하지 않는 등 XML 파일의 형식이 올바르게 지정되지 않은 경우 또는 텍스트 편집기에서 파일 시작부에 BOM(0xEF 0xBB 0xBF 순서 표시)을 추가하여 XML 구문 분석이 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-293">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="97272-294">한 가지 간단한 해결 [](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 방법은 샘플 파일을 다운로드한 **다음(원시를** 선택한 **다음** 다른 로 저장)을 다운로드한 다음 업데이트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97272-294">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="97272-295">값이 있으며 그룹 정책을 통해 정책이 관리되는 경우 클라이언트 장치가 정책 XML 경로에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97272-295">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="97272-296">**조직에서 최신 맬웨어 방지 클라이언트 버전을 사용하는 컴퓨터는 어떻게 알 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="97272-296">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="97272-297">다음 쿼리를 사용하여 보안 포털에서 맬웨어 방지 클라이언트 버전을 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97272-297">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```


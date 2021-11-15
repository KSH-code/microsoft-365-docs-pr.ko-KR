---
title: Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어, 이동식 저장소 미디어
description: 끝점용 Microsoft Defender에 대한 Walk-through
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.date: 11/02/2021
ms.openlocfilehash: b9634b616214d62a540ffba59fabd4996de3c3b6
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962485"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어

> [!NOTE]
> 이 제품의 그룹 정책 관리는 이제 일반적으로 사용할 수 있습니다(4.18.2106): [Tech Community 블로그: Endpoint용 Microsoft Defender를](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806) 사용하여 이동식 저장소 및 프린터 보호를 참조하세요. 


Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어를 사용하여 다음 작업을 할 수 있습니다.

- 제외 또는 제외 없이 이동식 저장소에 대한 읽기, 쓰기 또는 실행 액세스 허용 또는 차단

<br/><br/>

|권한|사용 권한|
|---|---|
|접근|읽기, 쓰기, 실행|
|작업 모드|감사, 허용, 방지|
|CSP 지원|예|
|GPO 지원|예|
|사용자 기반 지원|예|
|컴퓨터 기반 지원|예|

## <a name="prepare-your-endpoints"></a>엔드포인트 준비하기

이동식 Storage 맬웨어 방지 클라이언트 Windows 10 Windows 11 **4.18.2103.3** 이상이 있는 Windows 11 장치에 이동식 액세스 제어를 배포합니다.

- **4.18.2104** 이상 : SerialNumberId 추가, VID_PID, 파일 경로 기반 GPO 지원, ComputerSid
- **4.18.2105** 이상 : HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId에 대한 와일드카드 지원 추가, 특정 컴퓨터의 특정 사용자 조합, 제거 가능한 SSD(SanDisk Extreme SSD)/UAS(USB 연결된 SCSI) 지원
- **4.18.2107** 이상: Windows 이동식 장치(태블릿) 지원 추가(태블릿 등의 모바일 장치용) 추가, 고급 헌팅에 AccountName [추가](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint)

:::image type="content" source="images/powershell.png" alt-text="PowerShell 인터페이스.":::

> [!NOTE]
> 이동식 Windows 보안 상태와는 독립적으로 이동식 액세스 제어를 실행할 수 Storage 구성 요소를 활성화할 Windows 보안 없습니다.

## <a name="policy-properties"></a>정책 속성

다음 속성을 사용하여 이동식 저장소 그룹을 만들 수 있습니다.

> [!NOTE]
> XML 주석 표기법을 사용하는 설명은 규칙 및 그룹 XML 파일에서 사용할 수 있지만 XML 파일의 첫 번째 줄이 아니라 첫 번째 XML 태그 안에 `<!-- COMMENT -->` 있어야 합니다.

### <a name="removable-storage-group"></a>이동식 Storage 그룹

<br/><br/>

|속성 이름|설명|옵션|
|---|---|---|
|**GroupId**|고유 ID인 GUID는 그룹을 나타내며 정책에 사용됩니다.||
|**DescriptorIdList**|그룹에서 다루는 데 사용할 장치 속성을 나열합니다. 각 장치 속성에 대한 자세한 내용은 [장치 속성을](device-control-removable-storage-protection.md) 참조하세요. 모든 속성에는 대소문자 구분이 있습니다. |**PrimaryId**: RemovableMediaDevices, CdRomDevices, WpdDevices<p>**BusId**: 예: USB, SCSI<p>**DeviceId**<p>**HardwareId**<p>**InstancePathId**: InstancePathId는 시스템에서 장치를 고유하게 식별하는 문자열입니다(예: `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0` ). 끝에 있는 번호(예: &0)는 사용 가능한 슬롯을 나타내며 디바이스에서 장치로 변경될 수 있습니다. 최상의 결과를 얻기 위해 끝에 와일드카드를 사용 합니다. 예를 들면 `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*`와 같습니다.<p>**FriendlyNameId**<p>**SerialNumberId**<p>**VID**<p>**PID**<p>**VID_PID**<p>0751_55E0: 이 정확한 VID/PID 쌍과 일치<p>55E0: PID=55E0과 모든 미디어 일치 <p>0751: VID=0751과 모든 미디어 일치|
|**MatchType**|DescriptorIDList에 여러 장치 속성이 사용되는 경우 MatchType은 관계를 정의합니다.|**MatchAll:** DescriptorIdList의 모든 특성은 **And 관계가** 됩니다. 예를 들어 관리자가 DeviceID와 InstancePathID를 넣는 경우 연결된 모든 USB에 대해 시스템에서 USB가 두 값을 모두 충족하는지 확인합니다. <p> **MatchAny:** DescriptorIdList의 특성은 **또는** 관계가 됩니다. 예를 들어 관리자가 DeviceID 및 InstancePathID를 넣는 경우 연결된 모든 USB에 대해 USB에 **동일한 DeviceID** 또는 **InstanceID** 값이 있는 한 시스템에서 적용을 실행합니다. |

### <a name="access-control-policy"></a>액세스 제어 정책

<br/><br/>

| 속성 이름 | 설명 | 옵션 |
|---|---|---|
| **PolicyRuleId** | 고유한 ID인 GUID는 정책을 나타내며 보고 및 문제 해결에 사용됩니다. | |
| **IncludedIdList** | 정책을 적용할 그룹입니다. 여러 그룹이 추가된 경우 정책은 해당 그룹의 모든 미디어에 적용됩니다.|이 인스턴스에서는 그룹 ID/GUID를 사용해야 합니다. <p> 다음 예에서는 GroupID의 사용을 보여 줍니다. <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | 정책이 적용되지 않는 그룹입니다. | 이 인스턴스에서는 그룹 ID/GUID를 사용해야 합니다. |
| **항목 ID** | 하나의 PolicyRule에는 여러 항목이 있을 수 있습니다. 고유한 GUID가 있는 각 항목은 장치 제어에 한 가지 제한을 알 수 있습니다.| |
| **유형** | IncludedIDList에서 이동식 저장소 그룹에 대한 작업을 정의합니다. <p>적용: 허용 또는 거부 <p>감사: AuditAllowed 또는 AuditDenied<p> | 허용<p>거부 <p>AuditAllowed: 액세스가 허용되는 경우 알림 및 이벤트를 정의합니다. <p>AuditDenied: 액세스가 거부된 경우 알림 및 이벤트를 정의합니다. 거부 항목과 **함께 작업해야** 합니다.<p> 동일한 미디어에 대한 충돌 유형이 있는 경우 시스템은 정책의 첫 번째 형식을 적용합니다. 충돌 형식의 예로는 **Allow** 및 **Deny가 있습니다.** |
| **Sid** | 로컬 사용자 Sid 또는 사용자 Sid 그룹 또는 AD 개체의 Sid는 특정 사용자 또는 사용자 그룹에 이 정책을 적용할지 여부를 정의합니다. 하나의 항목은 최대 하나의 Sid를 사용할 수 있으며 Sid가 없는 항목은 컴퓨터 위에 정책을 적용하는 것입니다. |  |
| **ComputerSid** | 로컬 컴퓨터 Sid 또는 컴퓨터 Sid 그룹 또는 AD 개체의 Sid는 특정 컴퓨터 또는 컴퓨터 그룹에 이 정책을 적용할지 여부를 정의합니다. 하나의 항목은 최대 하나의 ComputerSid를 사용할 수 있으며 ComputerSid가 없는 항목은 컴퓨터에 정책을 적용하는 것입니다. 특정 사용자 및 특정 컴퓨터에 Entry를 적용하려면 Sid와 ComputerSid를 모두 동일한 항목에 추가합니다. |  |
| **옵션** | 알림을 표시할지 여부를 정의합니다. |**0 또는 4:** 허용 또는 거부 유형이 선택된 경우. <p>0: nothing<p>4: 이 항목에 **대해 AuditAllowed** 및 **AuditDenied를** 사용하지 않도록 설정 **차단이 발생하고** AuditDenied가 구성된 경우에도 시스템에 알림이 표시되지 않습니다. <p> **AuditAllowed 유형이 선택된** 경우: <p>0: nothing <p>1: nothing <p>2: 이벤트 보내기<p>3: 이벤트 보내기 <p> **AuditDenied 유형이 선택된** 경우: <p>0: nothing <p>1: 알림 표시 <p>2: 이벤트 보내기<p>3: 알림 표시 및 이벤트 보내기 |
|AccessMask|액세스를 정의합니다. | **1-7**: <p>1: 읽기 <p>2: 쓰기 <p>3: 읽기 및 쓰기 <p>4: 실행 <p>5: 읽기 및 실행<p>6: 쓰기 및 실행 <p>7: 읽기 및 쓰기 및 실행 |

## <a name="common-removable-storage-access-control-scenarios"></a>일반적인 이동식 Storage 액세스 제어 시나리오

Microsoft Defender for Endpoint 이동식 Storage 액세스 제어에 익숙해지기 위해 따라야 할 몇 가지 일반적인 시나리오를 준비했습니다.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>시나리오 1: 모든 웹 에 대한 쓰기 및 실행 액세스를 방지하지만 승인된 특정 USB는 허용

1. 그룹 만들기

    1. 그룹 1: 모든 이동식 저장소 및 CD/DVD. 이동식 저장소 및 CD/DVD의 예로는 그룹 **9b28fae8-72f7-4267-a1a5-685f747a7146** 샘플의 모든 이동식 Storage 및 [CD-DVD](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Group.xml파일이 있습니다.
    2. 그룹 2: 장치 속성에 따라 승인된 USB. 이 사용 사례의 예로는 샘플 승인된 USB 파일에서 인스턴스 ID - 그룹 **65fa649a-a111-4912-9294-fb6337a25038** [Group.xml이](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 있습니다.

    > [!TIP]
    > 값으로 `&` `&amp;` 바꾸기

2. 정책 생성

    1. 정책 1: 쓰기 및 액세스 실행을 차단하지만 승인된 USB는 허용합니다. 이 사용 사례의 예는 예제 시나리오 [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 쓰기 차단 및 실행에서 PolicyRule **c544a991-5786-4402-949e-a032cb790d0e이지만** 승인된 USBs.xml파일을 허용합니다.
    2. 정책 2: 허용된 USB에 대한 쓰기 및 실행 액세스를 감사합니다. 이 사용 사례의 예는 예제 시나리오 [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 감사 쓰기 및 승인된 USBs.xml파일에 대한 액세스 실행의 PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c입니다.**

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>시나리오 2: 승인되지 않은 특정 USB를 모두 차단하지만 모든 쓰기 및 실행 액세스 감사

1. 그룹 만들기

    1. 그룹 1: 모든 이동식 저장소 및 CD/DVD. 이 사용 사례의 예는 샘플 Any Removable Storage [및 CD-DVD](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Group.xml파일의 Group **9b28fae8-72f7-4267-a1a5-685f747a7146입니다.**
    2. 그룹 2: 장치 속성에 따라 승인되지 않은 USB(예: 공급업체 ID/ 제품 ID, 식별 이름 – 그룹 **65fa649a-a111-4912-9294-fb6337a25038)** 샘플에서 승인되지 않은 [USB](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Group.xml.

    > [!TIP]
    > 값으로 `&` `&amp;` 바꾸기

2. 정책 생성

    1. 정책 1: 승인되지 않은 특정 USB를 모두 차단하지만 모든에 대한 쓰기 및 실행 액세스를 차단합니다. 이 사용 사례의 예는 예제 시나리오 2 감사 쓰기 및 실행의 예제 시나리오 2에서 PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98입니다.** 승인되지 않은 특정 USBs.xml파일에 대한 액세스는 모두 차단합니다. [](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)
    2. 정책 2: 다른 사용자에 대한 쓰기 및 실행 액세스를 감사합니다. 이 사용 사례의 예는 예제 시나리오 [others.xml2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 감사 쓰기 및 실행 파일에서 PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48입니다.**

## <a name="deploying-and-managing-policy-via-group-policy"></a>그룹 정책을 통해 정책 배포 및 관리

이동식 Storage 액세스 제어 기능을 사용하면 그룹 정책을 통해 사용자 또는 장치 또는 둘 다에 정책을 적용할 수 있습니다.

### <a name="licensing"></a>라이선싱

이동식 액세스 제어를 Storage 시작하기 전에 [구독을 Microsoft 365 합니다.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) 이동식 액세스 Storage 액세스 제어에 액세스하고 사용하려면 액세스 Microsoft 365 E3 또는 Microsoft 365 E5.

### <a name="deploying-policy-via-group-policy"></a>그룹 정책을 통해 정책 배포

1. 모든 그룹을 하나의 `<Groups>` `</Groups>` xml 파일로 결합합니다.

    다음 이미지는 시나리오 1: 쓰기 금지 및 모든 승인된 USB에 대한 액세스 실행을 허용하는 [예제를 보여 줍니다.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)

    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="장치에서 승인된 특정 USB를 허용하는 구성 설정을 표시하는 화면입니다.":::

2. 모든 규칙을 하나의 `<PolicyRules>` `</PolicyRules>` xml 파일로 결합합니다.

    특정 사용자를 제한하려는 경우 Entry에 SID 속성을 사용 합니다. 정책 Entry에 SID가 없는 경우 항목은 컴퓨터의 모든 로그인 인스턴스에 적용됩니다.

    다음 이미지는 SID 속성의 사용을 보여 주며 시나리오 [1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)모든 승인된 USB는 허용하지만 모든 사용자에 대해 쓰기 및 실행 액세스 금지의 예를 보여 줍니다.

    :::image type="content" source="images/usage-sid-property.png" alt-text="SID 속성 특성의 사용을 나타내는 코드를 표시하는 화면입니다.":::

3. 네트워크 공유 폴더에 규칙 및 그룹 XML 파일을 저장하고 네트워크 공유 폴더 경로를 그룹 정책 설정에 넣습니다. **컴퓨터** 구성 관리 템플릿 Windows 구성 요소 Microsoft Defender 바이러스 백신 장치 \>  \>  \>  \> 제어: **'장치** 제어 **정책 그룹 정의' 및 '장치 제어 정책 규칙 정의'**.

   그룹 정책에서 정책 구성 UX를 찾을 수 없는 경우 원시를 선택한 다음 로 저장을 선택하여  [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) 및 [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) 파일을 다운로드할 **수 있습니다.**

   - 대상 컴퓨터는 정책을 사용하려면 네트워크 공유에 액세스할 수 있어야 합니다. 그러나 정책을 읽은 후 컴퓨터 재부팅 후에도 네트워크 공유 연결이 더 이상 필요하지 않습니다.

    :::image type="content" source="images/device-control.png" alt-text="장치 제어 화면입니다.":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Intune OMA-URI를 통해 정책 배포 및 관리

이동식 Storage 액세스 제어 기능을 사용하면 OMA-URI를 통해 사용자 또는 장치 또는 둘 다에 정책을 적용할 수 있습니다.

### <a name="licensing-requirements"></a>라이선스 요구사항

이동식 액세스 제어를 Storage 시작하기 전에 [구독을 Microsoft 365 합니다.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) 이동식 액세스 Storage 액세스 제어에 액세스하고 사용하려면 액세스 Microsoft 365 E3 또는 Microsoft 365 E5.

### <a name="permission"></a>사용 권한

Intune에서 정책 배포의 경우 계정에 장치 구성 프로필을 생성, 편집, 업데이트 또는 삭제할 수 있는 권한이 있어야 합니다. 이러한 사용 권한으로 사용자 지정 역할을 만들거나 기본 제공 역할을 사용할 수 있습니다.

- 정책 및 프로필 관리자 역할
- 장치 구성 프로필에 대해 보고서 만들기/편집/업데이트/읽기/삭제/보기 권한이 설정되어 있는 사용자 지정 역할
- 전역 관리자

### <a name="deploying-policy-via-oma-uri"></a>OMA-URI를 통해 정책 배포

Microsoft Endpoint Manager 관리 센터( ) 장치 구성 프로필 프로필 만들기 프로필 플랫폼: Windows 10 <https://endpoint.microsoft.com/> \>  \>  \>  \> **이상 & 프로필: 사용자 지정**

1. 각 그룹에 대해 OMA-URI 규칙을 생성합니다.

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**GroupGUID**%7d/GroupData`

      예를 들어 샘플의 이동식 저장소 및 **CD/DVD** 그룹의 경우 링크는 다음과 같습니다.

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

    - 데이터 형식: 문자열(XML 파일)

      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING 데이터 형식의 xml 파일입니다.":::

2. 각 정책에 대해 OMA-URI도 생성합니다.

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**PolicyRuleGUID**%7d/RuleData`

      예를 들어 예제에서 승인된 **USB** 규칙을 허용하지만 쓰기 차단 및 실행에 대한 링크는 다음과 같습니다.

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData`

    - 데이터 형식: 문자열(XML 파일)

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Intune 사용자 인터페이스를 사용하여 정책 배포 및 관리

이 기능은 Microsoft Endpoint Manager 관리 센터( )에서 사용할 수 <https://endpoint.microsoft.com/> 있습니다. **끝점 보안 공격 표면**  >  **축소 정책**  >  **만들기로 이동 합니다.** 플랫폼: **Windows 10** 이상 프로필: 장치 제어 **를 선택하세요.**

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에서 장치 Storage 이동식 액세스 제어 데이터 보기

Microsoft 365 Defender [포털에는](https://security.microsoft.com/advanced-hunting) 액세스 제어를 통해 장치 제어 이동식으로 트리거되는 Storage 표시됩니다. Microsoft 365 보안에 액세스하려면 다음 구독이 있어야 합니다.

- Microsoft 365 E5 보고용 보고서

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == "RemovableStoragePolicyTriggered"
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
|project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="이동식 저장소의 차단을 표시하는 화면입니다.":::

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="what-is-the-removable-storage-media-limitation-for-the-maximum-number-of-usbs"></a>최대 USB 수에 대한 이동식 저장소 미디어 제한은 무엇입니까?

100,000 미디어(최대 7MB) 크기의 USB 그룹 하나를 검증했습니다. 이 정책은 성능 문제 없이 Intune 및 GPO에서 모두 작동합니다.

### <a name="why-does-the-policy-not-work"></a>정책이 작동하지 않는 이유는 무엇입니까?

가장 일반적인 이유는 필수 맬웨어 방지 클라이언트 [버전이 없습니다.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)

예를 들어 XML 파일의 "&" 문자에 올바른 표시다운 서식을 사용하지 않는 등 XML 파일의 형식이 올바르게 지정되지 않은 경우 또는 텍스트 편집기에서 파일 시작에 BOM(0xEF 0xBB 0xBF 순서 표시)을 추가하여 XML 구문 분석이 작동하지 않을 수 있습니다. 한 가지 간단한 해결 [](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 방법은 샘플 파일을 다운로드한 **다음(원시를** 선택한 **다음** 다른 로 저장)을 다운로드한 다음 업데이트하는 것입니다.

그룹 정책을 통해 정책을 배포하고 관리하는 경우 PolicyRules라는 부모 노드 내의 하나의 XML 파일로 모든 PolicyRule을 결합하고 모든 Group을 그룹이라는 부모 노드 내의 하나의 XML 파일로 결합해야 합니다. Intune을 통해 관리하는 경우 하나의 PolicyRule을 하나의 XML 파일, 동일한 점, 하나의 그룹 하나의 XML 파일을 유지하십시오.

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>그룹 정책에 '장치 제어 정책 그룹 정의' 및 '장치 제어 정책 규칙 정의'에 대한 구성 UX가 없습니다.

그룹 정책 구성 UX를 백포트하지는 않지만 [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) 및 [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) 파일에서 '원시' 및 '다른 사용자로 저장'을 클릭하여 관련 adml 및 admx 파일을 계속 얻을 수 있습니다.

### <a name="how-can-i-know-which-machine-is-using-out-of-date-antimalware-client-version-in-the-organization"></a>조직에서 최신 맬웨어 방지 클라이언트 버전을 사용하는 컴퓨터는 어떻게 알 수 있나요?

다음 쿼리를 사용하여 보안 포털에서 맬웨어 방지 클라이언트 버전을 Microsoft 365 있습니다.

```kusto
//check the antimalware client version
DeviceFileEvents
|where FileName == "MsMpEng.exe"
|where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
|extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//|project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
|summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
|order by PlatformVersion desc
```

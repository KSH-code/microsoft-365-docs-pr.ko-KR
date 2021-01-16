---
title: Microsoft 365의 모바일 장치 관리에 등록된 장치 관리
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 기본 모바일 및 보안은 모바일 장치를 보호하고 관리하는 데 도움이 될 수 있습니다.
ms.openlocfilehash: 4954da0ff44276d9bd46cabc78bc52c7879e5e26
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876963"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Microsoft 365의 모바일 장치 관리에 등록된 장치 관리

Microsoft 365에 대한 기본 제공 모바일 장치 관리를 사용하면 iPhone, iPad, Android 및 Windows 휴대폰과 같은 사용자의 모바일 장치를 보호하고 관리할 수 있습니다. 첫 번째 단계는 Microsoft 365에 로그인하고 기본 이동성 및 보안을 설정하는 것입니다. 자세한 내용은 기본 이동성 및 [보안 설정을 참조하세요.](set-up.md)

이 구성을 설정한 후 조직의 사람들이 서비스에 장치를 등록해야 합니다. 자세한 내용은 기본 이동성 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md)그런 다음 기본 이동성 및 보안을 사용하여 조직의 장치를 관리할 수 있습니다. 예를 들어 장치 보안 정책을 사용하여 전자 메일 액세스 또는 기타 서비스를 제한하고, 장치 보고서를 보고, 원격으로 장치를 지우는 데 도움이 될 수 있습니다. 일반적으로 보안 및 준수 & 이동하여 이러한 작업을 수행합니다. 자세한 내용은 [Microsoft 365 규정 준수 센터를 참조하세요.](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)

## <a name="device-management-tasks"></a>장치 관리 작업

장치 관리 패널에 연결하려면 다음 단계를 수행합니다.

1.  [Microsoft 365 관리 센터로 이동하세요.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. 검색 필드에 모바일 장치 관리를 입력하고 결과 목록에서 모바일 장치 관리를   선택합니다.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="모바일 장치 관리 옵션":::

3. Select  **Let's get started**.

## <a name="manage-mobile-devices"></a>모바일 장치 관리

기본 이동성 및 보안을 설정한 후 조직에서 모바일 장치를 관리할 수 있는 몇 가지 방법이 있습니다.

|**이 작업을 위해**|**실행할 작업**|
|:----------------|:------------------------------------------------------------------------------|
|장치 지우기 |장치 관리 패널에서 ** 장치 이름을  **** 선택한 다음 전체 지우기를 선택하여 모든 정보를 삭제하거나 선택적 지우기를 선택하여 디바이스의 조직 정보만     ****   삭제합니다. 자세한 내용은 기본 이동성 및 보안에서 모바일 장치 [지우기를 참조하세요.](wipe-mobile-device.md)|
|Exchange ActiveSync를 사용하여 지원되지 않는 장치의 Exchange 전자 메일 액세스 차단 |장치 관리 패널에서 차단을  **선택합니다.** |
|암호 요구 사항 및 보안 설정과 같은 장치 정책 설정 |장치 관리 패널에서 **장치 보안** 정책   >  **추가 + 를 선택합니다.** 자세한 내용은 기본 이동성 및 보안에서 장치 보안 [정책 만들기를 참조하세요.](create-device-security-policies.md)|
|차단된 장치 목록 보기  |장치 관리 패널의  **보기 선택에서**     **차단을 선택합니다.** |
|사용자 또는 사용자 그룹에 대해 비규격 또는 지원되지 않는 장치의 차단 해제  |디바이스 차단을 해제하기 위해 다음 중 하나를 선택하십시오.<br/>- 정책이 적용된 보안 그룹에서 사용자 또는 사용자를 제거합니다. Go to Microsoft 365 admin center > **Groups,** and then select group name. 구성원 **및 관리자 편집을 선택합니다.**<br/>- 사용자가 장치 정책에서 구성원인 보안 그룹을 제거합니다. 보안 정책 장치 & 보안 > **보안**   >  **센터로 이동하세요.** 장치 정책 이름을 선택한 다음 배포 **편집을**  >  **선택합니다.**<br/>- 장치 정책에 대해 모든 비준수 장치 차단을 해제합니다. 보안 정책 장치 & 정책 > **보안**   >  **센터로 이동하십시오.** 장치 정책 이름을 선택한 다음 액세스 편집  >  **요구 사항을 선택합니다.** 액세스  **허용 및 위반 보고를 선택합니다.**<br/>- 사용자 또는 사용자 그룹에 대한 비준수 또는 지원되지 않는 장치 차단을 해제하려면 보안 & 준수 센터> **보안** 정책 장치 관리 장치 액세스 설정 관리로   >  ****   >  **이동합니다.** Microsoft 365에 대한 액세스가 차단되지 못하게 제외하려는 구성원이 있는 보안 그룹을 추가합니다. 자세한 내용은 Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 [삭제를 참조하세요.](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)|
|장치를 기본 이동성 및 보안으로 더 이상 관리하지 못하게 사용자 제거 |사용자를 제거하려면 기본 이동성 및 보안에 대한 장치 관리 정책이 있는 보안 그룹을 편집합니다. 자세한 내용은 Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는  [삭제를 참조하세요.](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)<br/>모든 Microsoft 365 사용자에서 기본 이동성 및 보안을 제거하려면 기본 이동성 및 보안 [해제를 참조합니다.](turn-off.md)|

Live(v14)
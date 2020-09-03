---
title: Microsoft 365의 모바일 장치 관리에 등록 되어 있는 장치 관리
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
description: 기본 이동성 및 보안은 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다.
ms.openlocfilehash: 36ea0d12becca2e97a56aceea107fa1f5bf6ded4
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337013"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Microsoft 365의 모바일 장치 관리에 등록 되어 있는 장치 관리

기본 제공 되는 모바일 장치 관리 Microsoft 365는 Iphone, Ipad, Androids 및 Windows phone과 같은 사용자의 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다. 첫 번째 단계는 Microsoft 365에 로그인 하 고 기본 이동성 및 보안을 설정 하는 것입니다. 자세한 내용은 [기본 이동성 및 보안 설정을](set-up-basic-mobility-and-security.md)참조 하십시오.

이 설정을 지정한 후에는 조직의 사용자가 서비스에서 해당 장치를 등록 해야 합니다. 자세한 내용은 [기본 이동성 및 보안을 사용 하 여 모바일 장치 등록](enroll-your-mobile-device-using-basic-mobility-and-security.md)을 참조 하세요.그런 다음 기본 이동성 및 보안을 사용 하 여 조직의 장치를 관리할 수 있습니다. 예를 들어 장치 보안 정책을 사용 하 여 전자 메일 액세스 또는 기타 서비스를 제한 하 고, 장치 보고서를 보고, 원격으로 장치를 지울 수 있습니다. 일반적으로 보안 & 준수 센터로 이동 하 여 이러한 작업을 수행 합니다. 자세한 내용은 [Microsoft 365 준수 센터](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)를 참조 하세요.

## <a name="device-management-tasks"></a>장치 관리 작업

장치 관리 패널에 액세스 하려면 다음 단계를 수행 합니다.

1.  [Microsoft 365 관리 센터로](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)이동 합니다.
    
2. 검색 필드에 모바일 장치 관리를 입력 하 고 결과 목록에서 **모바일 장치 관리**를 선택   합니다.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="모바일 장치 관리 옵션":::

3.   **장치 관리**를 선택 합니다.

## <a name="manage-mobile-devices"></a>모바일 장치 관리
    
기본 이동성 및 보안을 설정한 후에는 조직의 모바일 장치를 관리할 수 있는 몇 가지 방법이 나와 있습니다.

|**이 작업을 수행 하려면**|**실행할 작업**|
|:----------------|:------------------------------------------------------------------------------|
|장치 지우기 |장치 관리 패널에서 *장치 이름*,  **전체 지우기**   를 차례로 선택 하 여 모든 정보 또는  **선택 정리** 를 삭제 하 고   장치에서 조직 정보만 삭제 합니다. 자세한 내용은 [기본 Mobility And Security에서 모바일 장치 초기화](wipe-mobile-device.md)를 참조 하세요.|
|Exchange ActiveSync를 사용하여 지원되지 않는 장치의 Exchange 전자 메일 액세스 차단 |장치 관리 패널에서  **차단을**선택 합니다. |
|암호 요구 사항 및 보안 설정과 같은 장치 정책 설정 |장치 관리 패널에서 **장치 보안 정책**   >  **추가 +** 를 선택 합니다. 자세한 내용은 [기본 이동성 및 보안에서 장치 보안 정책 만들기](create-device-security-policies-in-basic-mmobility-and-security.md)를 참조 하세요.|
|차단된 장치 목록 보기  |장치 관리 패널의  **보기 선택** 에서     **차단 됨**을 선택 합니다. |
|사용자 또는 사용자 그룹에 대해 비규격 또는 지원되지 않는 장치의 차단 해제  |장치 차단을 해제 하려면 다음 중 하나를 선택 합니다.<br/>-정책이 적용 된 보안 그룹에서 사용자를 제거 합니다. Microsoft 365 관리 센터 > **그룹**으로 이동한 후 그룹 이름을 선택 합니다. **구성원 및 관리자 편집을**선택 합니다.<br/>-사용자가 장치 정책의 구성원 인 보안 그룹을 제거 합니다. Security & 준수 센터 > **보안 정책**   >  **장치 보안 정책**으로 이동 합니다. 장치 정책 이름을 선택한 다음 배포 **편집**을 선택  >  **Deployment**합니다.<br/>-장치 정책에 대 한 비규격 장치를 모두 차단 해제 합니다. Security & 준수 센터 > **보안 정책**   >  **장치 보안 정책**으로 이동 합니다. 장치 정책 이름을 선택한 다음 **Edit**  >  **액세스 요구 사항**편집을 선택 합니다.  **액세스 허용 및 보고서 위반**을 선택 합니다.<br/>-사용자 또는 사용자 그룹에 대해 비규격 또는 지원 되지 않는 장치를 차단 해제 하려면 보안 & 준수 센터 > **보안 정책**   >  **장치 관리**장치   >  **액세스 설정 관리**로 이동 합니다. Microsoft 365에 대 한 차단 된 액세스 권한에서 제외 시키려는 구성원을 포함 하는 보안 그룹을 추가 합니다. 자세한 내용은 [Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)를 참조 하세요.|
|조직의 장치에 대 한 세부 정보 얻기  |장치 보안 정책을 등록 하 고 준수 하는 장치에 대 한 자세한 내용은 [기본 이동성 및 보안 관리 장치에 대 한 세부 정보 가져오기를](get-details-about-basic-mobility-and-security-managed-devices.md)참조 하세요.|
|디바이스가 더 이상 기본 이동성 및 보안으로 관리 되지 않도록 사용자를 제거 합니다. |사용자를 제거 하려면 기본 이동성 및 보안에 대 한 장치 관리 정책이 포함 된 보안 그룹을 편집 합니다. 자세한 내용은  [Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)를 참조 하세요.<br/>Microsoft 365 사용자에 게 기본 Mobility and Security를 제거 하려면 [기본 이동성 및 보안 해제](turn-off-basic-mobility-and-security.md)를 참조 하세요.|

라이브 (v 14)
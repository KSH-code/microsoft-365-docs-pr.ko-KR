---
title: 모바일 장치에서 모바일 장치 관리에 등록된 Microsoft 365
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
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- MET150
description: 기본 모바일 및 보안은 조직 모바일 장치를 보호하고 관리하는 데 도움이 될 수 있습니다.
ms.openlocfilehash: 88d3dd58d61a0b3e26aaf46951f1dbcde76b7b34
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774186"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>모바일 장치에서 모바일 장치 관리에 등록된 Microsoft 365

iPhone, iPad Microsoft 365 Androids 및 휴대폰과 같은 사용자의 모바일 장치를 보호하고 관리하는 데 도움이 되는 기본 Windows 관리합니다. 첫 번째 단계는 기본 이동성 및 Microsoft 365 로그인하고 설정하는 데 있습니다. 자세한 내용은 기본 이동성 및 [보안 설정 을 참조하세요.](set-up.md)

이 서비스를 설정한 후 조직의 사람들이 서비스에 장치를 등록해야 합니다. 자세한 내용은 기본 모바일 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md)그런 다음 기본 Mobility and Security를 사용하여 조직의 장치를 관리할 수 있습니다. 예를 들어 장치 보안 정책을 사용하여 전자 메일 액세스 또는 기타 서비스를 제한하고, 장치 보고서를 보고, 장치를 원격으로 지우는 데 도움이 될 수 있습니다. 일반적으로 보안 및 준수 & 이동하여 이러한 작업을 수행합니다. 자세한 내용은 [를](../../compliance/microsoft-365-compliance-center.md)Microsoft 365 규정 준수 센터.

## <a name="device-management-tasks"></a>장치 관리 작업

장치 관리 패널에 연결하려면 다음 단계를 수행합니다.

1. 으로 [이동하여 Microsoft 365 관리 센터.](../../admin/admin-overview/about-the-admin-center.md)

2. 검색 필드에 모바일 장치 관리를 입력하고 결과 목록에서 **모바일** 장치 관리를   선택합니다.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="모바일 장치 관리 옵션입니다.":::

3. 시작  **을 선택합니다.**

## <a name="manage-mobile-devices"></a>모바일 장치 관리

기본 모바일 및 보안을 설정한 후 조직에서 모바일 장치를 관리할 수 있는 몇 가지 방법은 다음과 같습니다.

|**이 작업을 위해**|**실행할 작업**|
|:----------------|:------------------------------------------------------------------------------|
|장치 지우기 |장치 관리 패널에서 ** 장치 이름,  **** 전체 지우기를 선택하여 모든 정보를 삭제하거나 선택적 지우기를 선택하여 디바이스의 조직 정보만     ****   삭제합니다. 자세한 내용은 기본 모바일 및 보안에서 모바일 장치 [지우기를 참조하세요.](wipe-mobile-device.md)|
|Exchange ActiveSync를 사용하여 지원되지 않는 장치의 Exchange 전자 메일 액세스 차단 |장치 관리 패널에서 차단 을  **선택합니다.** |
|암호 요구 사항 및 보안 설정과 같은 장치 정책 설정 |장치 관리 패널에서 장치 **보안** 정책   >  **추가 + 를 선택합니다.** 자세한 내용은 기본 모바일 및 보안에서 장치 보안 [정책 만들기를 참조하세요.](create-device-security-policies.md)|
|차단된 장치 목록 보기  |장치 관리 패널의 보기  **선택에서 차단**     **을 선택합니다.** |
|사용자 또는 사용자 그룹에 대해 비규격 또는 지원되지 않는 장치의 차단 해제  |디바이스 차단을 해제하기 위해 다음 중 하나를 선택하십시오.<br/>- 정책이 적용된 보안 그룹에서 사용자 또는 사용자를 제거합니다. 그룹 Microsoft 365 관리 센터 > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**로**</a>이동한 다음 그룹 이름을 선택합니다. 구성원 **및 관리자 편집을 선택합니다.**<br/>- 사용자가 구성원인 보안 그룹을 장치 정책에서 제거합니다. 보안 및 준수 & 정책 > **정책**   >  **장치 보안 정책으로 이동하세요.** 장치 정책 이름을 선택한 다음 배포 **편집 을**  >  **선택합니다.**<br/>- 장치 정책에 대해 모든 비준수 장치의 차단을 해제합니다. 보안 및 준수 & 정책 > **정책**   >  **장치 보안 정책으로 이동하세요.** 장치 정책 이름을 선택한 다음 **액세스** 요구  >  **사항 편집 을 선택합니다.** 액세스  **및 보고서 위반 허용을 선택합니다.**<br/>- 사용자 또는 사용자 그룹에 대한 비규준 또는 지원되지 않는 장치 차단을 해제하려면 보안 & 준수 센터 > **보안** 정책 장치 관리 장치 액세스 설정 관리로   >  ****   >  **이동합니다.** 보안 그룹에 대한 액세스가 차단되지 못하게 제외하려는 구성원이 있는 보안 그룹을 Microsoft 365. 자세한 내용은 에서 보안 그룹 만들기, 편집 또는 [삭제를 Microsoft 365 관리 센터.](../../admin/email/create-edit-or-delete-a-security-group.md)|
|장치를 기본 이동성 및 보안으로 더 이상 관리하지 못하게 사용자를 제거합니다. |사용자를 제거하려면 기본 이동성 및 보안에 대한 장치 관리 정책이 있는 보안 그룹을 편집합니다. 자세한 내용은 에서 보안 그룹 만들기, 편집 또는  [삭제를 Microsoft 365 관리 센터.](../../admin/email/create-edit-or-delete-a-security-group.md)<br/>모든 사용자로부터 기본 모바일 및 보안을 Microsoft 365 기본 모바일 및 보안 [끄기를 참조합니다.](turn-off.md)|

Live(v14)
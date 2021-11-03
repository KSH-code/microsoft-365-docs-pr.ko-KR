---
title: 사용자 계정이 있는 장치에서 끝점 구성 설정에 대한 Microsoft Defender Microsoft Endpoint Manager
description: 끝점용 Microsoft Defender를 통해 Microsoft Endpoint Manager 보안 설정을 사용하도록 설정하는 방법을 확인합니다.
keywords: 장치 관리, 끝점 장치용 Microsoft Defender 구성, Microsoft Endpoint Manager
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 08fae46ce14a74dacefd76fbc8e77511c40609e6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60677195"
---
# <a name="manage-microsoft-defender-for-endpoint-configuration-settings-on-devices-with-microsoft-endpoint-manager"></a>사용자 계정이 있는 장치에서 끝점 구성 설정에 대한 Microsoft Defender Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [사용자 계정이 있는 장치에서 끝점에 대한 Microsoft Defender Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)


Microsoft Defender for Endpoint용 보안 관리는 Microsoft Defender에 대한 보안 구성을 수신하기 위해 Microsoft Endpoint Manager 또는 Microsoft Intune Microsoft Endpoint Configuration Manager 관리되지 않는 장치에 대한 기능입니다. 에서 직접 Endpoint Manager.


보안 구성 관리에 대한 선행 구성, 지원되는 플랫폼 등을 비롯한 자세한 내용은 Manage [Microsoft Defender for Endpoint on devices with Microsoft Endpoint Manager.](/mem/intune/protect/mde-security-integration)



[!INCLUDE [Prerequisites](../../includes/security-config-mgt-prerequisites.md)]


보안 구성 관리에 대한 자세한 내용은 Manage [Microsoft Defender for Endpoint on devices with Microsoft Endpoint Manager.](/mem/intune/protect/mde-security-integration)

등록 문제가 발생하는 경우 보안 구성 관리 등록 [문제 해결을 참조합니다.](troubleshoot-security-config-mgt.md)

> [!NOTE]
> 이 기능은 이미 Intune 또는 구성 관리자에 등록된 Microsoft Endpoint Manager 적용되지 않습니다. Intune에 등록된 장치는 설정한 관리 채널을 통해 정책을 계속 수신합니다.

## <a name="identify-onboarded-devices"></a>온보더드 장치 식별

다음 단계를 사용하여 끝점에서 끝점용 Microsoft Defender의 보안 관리 온보딩 프로세스를 성공적으로 완료한지 확인할 수 있습니다.

1.  디바이스가 에 있는 장치 인벤토리 섹션에 [Microsoft 365 Defender.](https://security.microsoft.com/)

2.  Azure Active Directory [포털에서](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/UsersManagementMenuBlade/MsGraphUsers)장치가 성공적으로 등록되어 있는지 확인합니다.

3.  Microsoft Endpoint Manager [관리](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/mDMDevicesPreview)센터의 장치 및 모든 장치 섹션에서 장치를 찾아 **> 등록되어 있는지** 확인합니다.


## <a name="offboard-devices"></a>장치 오프보드
끝점용 Microsoft Defender에 대한 보안 관리를 통해 온보딩된 장치를 오프보딩하는 경우 [끝점 서비스용 Microsoft Defender에서](offboard-machines.md)장치 오프보드를 참조합니다.

>[!NOTE]
>활성화된 경우 오프보더는 [변조](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) 보호를 사용하지 않도록 설정합니다.

## <a name="troubleshooting-security-management"></a>보안 관리 문제 해결 
끝점 등록 문제에 대한 Microsoft Defender의 보안 관리 문제를 해결 방법은 [Endpoint용 Microsoft Defender의](troubleshoot-security-config-mgt.md)보안 관리와 관련된 등록 문제 해결을 참조합니다.

## <a name="related-topic"></a>관련 항목
- [끝점용 Microsoft Defender의 보안 관리와 관련된 온보딩 문제 해결](troubleshoot-security-config-mgt.md)
- [사용자 계정이 있는 장치에서 끝점에 대한 Microsoft Defender Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration#configure-your-tenant-to-support-mde-security-configuration-management)

---
title: 파트너가 장치를 등록하기 위한 단계
description: 파트너가 장치를 등록 하 여 Microsoft Managed Desktop에서 관리할 수 있도록 하는 방법
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1b1a8f03b7a11a0467826281bc2b789140dbcee
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327059"
---
# <a name="steps-for-partners-to-register-devices"></a>파트너가 장치를 등록하기 위한 단계


이 항목에서는 파트너가 장치를 등록 하기 위해 수행 해야 하는 단계에 대해 설명 합니다. 장치를 직접 등록 하는 프로세스는 [Microsoft Managed Desktop의 등록 장치에 직접](register-devices-self.md)기록 됩니다.



## <a name="prepare-for-registration"></a>등록 준비 
고객에 대 한 등록을 완료 하기 전에 먼저 [파트너 센터](https://partner.microsoft.com/dashboard)에서 해당 사용자와의 관계를 설정 해야 합니다. 해당 프로세스에 대 한 자세한 내용은 [동의 설명서](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 를 참조 하세요. 모든 CSP 파트너는 고객을 대신 하 여 고객을 추가할 수 있는 consents 있습니다. 파트너 관계 및 Autopilot 사용 권한에 대 한 자세한 내용은 [Partner Center help](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)를 참조 하십시오.


> [!NOTE]
> 이 문서는 파트너 및 Oem만을 위한 것입니다. 자동 등록 프로세스는 [Microsoft Managed Desktop의 등록 장치에서 직접](register-devices-self.md)설명 됩니다.


## <a name="register-devices-by-using-partner-center"></a>파트너 센터를 사용 하 여 장치 등록

고객과의 관계를 설정한 후에는 파트너 센터를 활용 하 여 다음 단계를 수행 하 여 관계가 있는 고객의 Autopilot에 장치를 추가할 수 있습니다.

1. [파트너 센터로](https://partner.microsoft.com/dashboard) 이동
2. 파트너 센터 메뉴에서 **고객** 을 선택한 다음 해당 장치를 관리할 고객을 선택 합니다.
3. 고객 정보 페이지에서 **장치**를 선택 합니다.
4. 장치에 **프로필 적용** 에서 **장치 추가**를 선택 합니다.
5. 그룹 이름으로 **Microsoft365Managed_Autopilot** 입력 한 다음 **찾아보기를** 선택 하 여 고객 목록 (.csv 파일 형식)을 파트너 센터에 업로드 합니다.


> [!IMPORTANT]
> 그룹 이름은 대/소문자 및 특수 문자를 포함 하 여 **Microsoft365Managed_Autopilot** 정확히 일치 해야 합니다. 이렇게 하면 새로 등록 된 장치를 Microsoft Managed Desktop Autopilot 프로필에 할당할 수 있습니다.

>[!NOTE]
> 장치 구입처에서이 .csv 파일을 받아야 합니다. .Csv 파일을 받지 못한 경우에는 [Windows Autopilot에 장치 추가](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)의 단계를 수행 하 여 직접 만들 수 있습니다. Windows PowerShell 스크립트는 [Microsoft Managed Desktop Admin 포털](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash)에 사용 된 것과 다릅니다. 파트너는 [get-windowsautopilotinfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 을 사용 하 여 파트너 센터에서 Microsoft Managed Desktop 장치에 대 한 장치를 등록 해야 합니다.

.Csv 파일을 업로드 하는 동안 오류 메시지가 표시 되 면 파일 형식을 확인 합니다. 하드웨어 해시 전용, OEM 이름, 일련 번호 및 모델 (열 순서) 또는 Windows 제품 ID를 사용할 수 있습니다. 장치 **추가** 옆의 링크에서 제공 되는 예제 .csv 파일을 사용 하 여 디바이스 목록을 만들 수도 있습니다. 

파트너 시나리오의 Autopilot에 대 한 자세한 내용은 [고객의 계정에 장치 추가](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)를 참조 하세요.


## <a name="register-devices-by-using-the-oem-api"></a>OEM API를 사용 하 여 장치 등록

고객에 대 한 등록을 완료 하기 전에 먼저 해당 고객과의 관계를 설정 해야 합니다. 각 고객에 게 제공할 고유한 링크가 있어야 합니다. [OEM 관계를 설정 하는 방법을](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)참조 하세요.

관계를 설정한 후에는 Group 태그 **Microsoft365Managed_Autopilot**를 사용 하 여 고객을 위한 장치 등록을 시작할 수 있습니다.

> [!IMPORTANT]
> 그룹 이름은 대/소문자 및 특수 문자를 포함 하 여 **Microsoft365Managed_Autopilot** 정확히 일치 해야 합니다. 이렇게 하면 새로 등록 된 장치를 Microsoft Managed Desktop Autopilot 프로필에 할당할 수 있습니다.

---
title: 파트너가 장치를 등록하기 위한 단계
description: 파트너가 디바이스를 등록하여 디바이스를 관리하기 위해 등록하는 Microsoft Managed Desktop
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
ms.openlocfilehash: 64686f84d8e4cc7dca40a875d8b54508ea9a1fc9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212375"
---
# <a name="steps-for-partners-to-register-devices"></a>파트너가 장치를 등록하기 위한 단계


이 문서에서는 파트너가 장치를 등록하기 위해 따라야 하는 단계에 대해 설명합니다. 장치를 직접 등록하는 프로세스는 장치 등록에서 직접 Microsoft Managed Desktop [문서화되어 있습니다.](register-devices-self.md)



## <a name="prepare-for-registration"></a>등록 준비 
고객 등록을 완료하기 전에 먼저 파트너 센터에서 고객과 [관계를 설정해야 합니다.](https://partner.microsoft.com/dashboard) 해당 [프로세스에 대한](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 자세한 내용은 동의 설명서를 참조하세요. 모든 CSP 파트너는 고객이 동의하는 한 모든 고객을 대신하여 장치를 추가할 수 있습니다. 파트너 관계 및 Autopilot 사용 권한에 대한 자세한 내용은 파트너 센터 [도움말을 통해 자세히 알아보실 수 있습니다.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> 이 설명서는 파트너 및 OEM에 한해 제공됩니다. 자체 등록 프로세스는 에서 장치 등록에 [Microsoft Managed Desktop 설명되어 있습니다.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>파트너 센터를 사용하여 장치 등록

고객과의 관계를 설정한 후 파트너 센터를 사용하여 다음 단계에 따라 관계가 있는 모든 고객을 위해 Autopilot에 장치를 추가할 수 있습니다.

1. 파트너 [센터로 이동](https://partner.microsoft.com/dashboard)
2. 파트너 **센터** 메뉴에서 고객을 선택한 다음 디바이스를 관리할 고객을 선택합니다.
3. 고객의 세부 정보 페이지에서 장치를 **선택합니다.**
4. 장치에 **프로필 적용에서** 장치 **추가를 선택합니다.**
5. 선택한 장치 프로필에 적절한 그룹 태그를 입력한 다음 찾아보기를 선택하여  고객 목록을 파트너 센터에 업로드합니다(.csv 파일 형식).

|[장치 프로필](../service-description/profiles.md)  |그룹 태그  |
|---------|---------|
|민감 데이터     |**Microsoft365Managed \_ SensitiveData**    |
|파워 사용자     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**        |

> [!IMPORTANT]
> 그룹 이름은 대문자 및 특수 문자를 포함하여 표에 나열된 이름과 정확히 일치해야 합니다. 이렇게 하면 새로 등록된 디바이스를 Autopilot 프로필과 함께 Microsoft Managed Desktop 수 있습니다.

>[!NOTE]
> 디바이스 구매 시 이 .csv 파일을 받았을 것입니다. .csv 파일을 받지 못하면 [Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)에 장치 추가의 단계에 따라 직접 Windows 있습니다. 추가 열은 지원되지 않습니다. 따옴표는 지원되지 않습니다. ANSI 형식 텍스트 파일만 사용할 수 있습니다(유니코드 아미드). 헤더는 대소문자 구분입니다. 이러한 Excel 파일을 편집하고 CSV 파일로 저장하면 이러한 요구 사항으로 인해 사용할 수 있는 파일이 생성되지 않습니다. 디바이스 일련 번호에 선행 0을 유지해야 합니다. 파트너는 [Get-WindowsAutoPilotInfo를](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 사용하여 파트너 센터에서 Microsoft Managed Desktop 장치를 등록해야 합니다.

파일 파일을 업로드하는 동안 오류 메시지가 .csv 파일의 형식을 검사합니다. 열 순서가 새 디바이스의 [Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)프로필을 사용하여 고객의 첫 번째 경험 사용자 지정에 설명된 Windows 일치하는지 확인 장치 추가 옆에 있는 링크에서 제공된 샘플  .csv 파일을 사용하여 장치 목록을 만들 수 있습니다. 

파트너 시나리오의 Autopilot에 대한 자세한 내용은 고객 계정에 장치 [추가를 참조하세요.](/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>OEM API를 사용하여 장치 등록

고객 등록을 완료하기 전에 먼저 고객과 관계를 설정해야 합니다. 각 고객에게 제공할 고유한 링크가 있습니다. [OEM 관계를 설정하는 방법을 참조합니다.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

관계를 설정한 후 선택한 각 장치 프로필에 대해 적절한 그룹 태그를 사용하여 고객을 위해 디바이스를 등록할 수 있습니다.


|장치 프로필  |그룹 태그  |
|---------|---------|
|민감 데이터     | **Microsoft365Managed \_ SensitiveData**     |
|파워 사용자     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**      |

> [!IMPORTANT]
> 그룹 태그는 대문자 및 특수 문자를 포함하여 표에 나열된 태그와 정확히 일치해야 합니다. 이렇게 하면 새로 등록된 디바이스를 Autopilot 프로필과 함께 Microsoft Managed Desktop 수 있습니다.

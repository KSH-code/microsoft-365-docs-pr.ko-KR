---
title: 파트너가 장치를 등록하기 위한 단계
description: 파트너가 Microsoft Managed Desktop에서 관리할 수 있도록 디바이스를 등록하는 방법
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071446"
---
# <a name="steps-for-partners-to-register-devices"></a>파트너가 장치를 등록하기 위한 단계


이 항목에서는 파트너가 디바이스를 등록하기 위해 따라야 하는 단계에 대해 설명합니다. 직접 디바이스를 등록하는 프로세스는 [Microsoft Managed Desktop의 장치 등록에 설명되어 있습니다.](register-devices-self.md)



## <a name="prepare-for-registration"></a>등록 준비 
고객 등록을 완료하기 전에 먼저 파트너 센터에서 고객과 관계를 [설정해야 합니다.](https://partner.microsoft.com/dashboard) 해당 [프로세스에 대한](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 자세한 내용은 동의 설명서를 참조하세요. 모든 CSP 파트너는 고객이 동의하는 한 모든 고객을 대신하여 장치를 추가할 수 있습니다. 파트너 관계 및 Autopilot 사용 권한에 대한 자세한 내용은 파트너 센터 도움말을 통해 자세히 [알아보실 수 있습니다.](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> 이 설명서는 파트너 및 OEM에 한해 제공됩니다. 자체 등록 프로세스는 [Microsoft Managed Desktop의 등록 장치에 직접 문서화되어 있습니다.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>파트너 센터를 사용하여 장치 등록

고객과의 관계를 설정한 후 파트너 센터를 활용하여 다음 단계에 따라 관계에 있는 모든 고객을 위해 Autopilot에 장치를 추가할 수 있습니다.

1. 파트너 [센터로 이동](https://partner.microsoft.com/dashboard)
2. 파트너 **센터** 메뉴에서 고객을 선택한 다음 디바이스를 관리할 고객을 선택합니다.
3. 고객의 세부 정보 페이지에서 장치를 **선택합니다.**
4. 장치에 **프로필 적용** 아래에서 장치 **추가를 선택합니다.**
5. 그룹 **Microsoft365Managed_Autopilot** 이름을 입력한 다음 찾아보기를 선택하여 고객 목록(.csv 파일 형식)을 파트너 센터에 업로드합니다. 


> [!IMPORTANT]
> 그룹 이름은 **대문자** Microsoft365Managed_Autopilot 문자를 포함하여 정확히 일치해야 합니다. 이렇게 하면 새로 등록된 장치를 Microsoft Managed Desktop Autopilot 프로필로 할당할 수 있습니다.

>[!NOTE]
> 장치 구매와 함께 이 .csv 파일을 받았을 것입니다. .csv 파일을 받지 않은 경우 [Windows Autopilot에](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)장치 추가의 단계에 따라 직접 파일을 만들 수 있습니다. 이 Windows PowerShell [Microsoft Managed Desktop Admin 포털에 사용되는 스크립트와 다릅니다.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash) 파트너는 [Get-WindowsAutoPilotInfo를](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 사용하여 파트너 센터에서 Microsoft Managed Desktop 장치용 장치를 등록해야 합니다.

.csv 파일을 업로드하는 동안 오류 메시지가 표시되어 있는 경우 파일의 형식을 검사합니다. 열 순서가 새 장치에서 [Windows Autopilot](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)프로필을 사용하여 고객의 첫 실행 경험을 사용자 지정하는 데 설명된 순서와 일치하는지 확인 장치 추가 옆에 있는 링크에서 제공된 샘플 .csv 파일을 사용하여 장치 목록을 만들 수 있습니다.  

파트너 시나리오의 Autopilot에 대한 자세한 내용은 고객 계정에 장치 [추가를 참조하세요.](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>OEM API를 사용하여 장치 등록

고객 등록을 완료하기 전에 먼저 고객과 관계를 설정해야 합니다. 각 고객에게 제공할 고유한 링크가 있습니다. [OEM 관계를 설정하는 방법을 참조합니다.](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

관계를 설정한 후 그룹 태그 그룹을 사용하여 고객을 위해 디바이스를 등록할 **수 Microsoft365Managed_Autopilot.**

> [!IMPORTANT]
> 그룹 이름은 **대/Microsoft365Managed_Autopilot** 문자를 포함하여 정확히 일치해야 합니다. 이렇게 하면 새로 등록된 장치를 Microsoft Managed Desktop Autopilot 프로필로 할당할 수 있습니다.

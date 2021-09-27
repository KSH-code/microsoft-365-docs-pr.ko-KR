---
title: PC에 대한 앱 보호 Windows 10 유효성 검사
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 비즈니스용 앱 보호 Microsoft 365 설정이 사용자의 디바이스에 영향을 Windows 10 방법을 확인합니다.
ms.openlocfilehash: c0d5ded2eeda022984f86c33429572fa4a8671bb
ms.sourcegitcommit: 34259ec9b6cccc8f6e29808dbe4796d9f72b651b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59933378"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>PC에 대한 장치 보호 Windows 10 유효성 검사

## <a name="verify-that-windows-10-device-policies-are-set"></a>장치 Windows 10 설정되어 있는지 확인

장치 정책을 [설정한](protection-settings-for-windows-10-pcs.md)후 정책이 사용자의 장치에 적용되는 데 최대 몇 시간이 걸릴 수 있습니다. 사용자 디바이스의 다양한 Windows 설정 확인하여 정책이 적용된 것으로 확인할 수 있습니다. 사용자가 자신의 Windows 장치에서 Windows 및 Windows Defender 바이러스 백신 설정을 수정할 수 Windows 10 옵션이 많이 회색으로 표시됩니다.
  
1. 보안 **설정** 업데이트 Windows 다시 시작 옵션으로 이동하여 모든 설정이 \> **&amp;** \>  \>  회색으로 표시되어 있는지 확인합니다. 
    
    ![다시 시작 옵션은 모두 회색으로 표시됩니다.](../../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. 보안 **설정** 업데이트 Windows 고급 옵션으로 이동하여 모든 설정이 \> **&amp;** \>  \>  회색으로 표시되어 있는지 확인합니다. 
    
    ![Windows 고급 업데이트 옵션은 모두 회색으로 표시됩니다.](../../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **설정** \> **Update security &amp; Windows** \>  \> **Advanced options** Choose \> **how updates are delivered**.
    
    일부 설정이 조직에서 숨겨지거나 관리되고 모든 옵션이 회색으로 표시되고 메시지가 빨간색으로 표시될 수 있도록 합니다.
    
    ![업데이트 배달 방법 선택 페이지에는 조직에서 설정을 숨기거나 관리하는 설정이 표시됩니다.](../../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Windows Defender 보안 센터를 열려면 설정  업데이트 보안 Windows Defender 보안 센터 바이러스 스레드 보호 바이러스 위협 보호 Windows Defender 설정을 \> **&amp;** \>  \>  \> **&amp;** \> **&amp; 클릭합니다.** 
    
5. 모든 옵션이 회색으로 표시 있는지 확인 
    
    ![바이러스 및 위협 방지 설정은 회색으로 표시됩니다.](../../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365 문서 및 리소스에 대한 자세한 설명](./index.yml)\
[Windows 10 PC용 장치 구성 설정](protection-settings-for-windows-10-pcs.md)

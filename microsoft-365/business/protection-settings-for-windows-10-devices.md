---
title: Windows 10 장치에 대 한 응용 프로그램 보호 설정 편집 또는 설정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 사용자의 개인 Windows 10 장치에서 앱 관리 정책을 만들거나 편집 하 고 작업 파일을 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: f85a59649e43c141b62091337b842a490d411833
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289202"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>Windows 10 장치에 대 한 응용 프로그램 보호 설정 설정 또는 편집

이 문서는 Microsoft 365 Business Premium에 적용 됩니다.

## <a name="edit-an-app-management-policy-for-windows-10"></a>Windows 10 용 앱 관리 정책 편집

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.     
2. 왼쪽 탐색 창에서 **장치** \> **정책을** 선택 합니다.
1. 기존 Windows 앱 정책을 선택 하 고 **편집**을 클릭 합니다.
1. 변경할 설정 옆의 **편집** 을 선택한 다음 **저장**을 선택 합니다.

## <a name="create-an-app-management-policy-for-windows-10"></a>Windows 10용 앱 관리 정책 만들기

사용자들이 업무를 수행할 수 있는 개인 Windows 10 장치를 갖고 있는 경우, 해당 장치에서도 데이터를 보호할 수 있습니다.
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다. 
2. 왼쪽 탐색 창에서 **장치** \> **정책** \> **추가**를 선택 합니다.
3. **정책 추가** 창에서 이 정책의 고유 이름을 입력합니다. 
4. **정책 유형**에서 **Windows 10용 응용 프로그램 관리**를 선택합니다.
5. **장치 유형에**서 **개인** 또는 **소유한 회사**를 선택 합니다.
6. **작업 파일 암호화**가 자동으로 켜집니다. 
7. 사용자가 작업 파일을 개인 PC에 저장하지 않도록 하려면 **사용자가 회사 데이터를 개인 파일로 복사하는 것을 차단하고 회사 파일은 비즈니스용 OneDrive에 저장하도록 합니다.** 를 **켜기**로 설정하세요. 
9. **Windows 장치에서 데이터 복구를**확장 합니다. 이 기능을 켜는 것이 **좋습니다.**
    데이터 복구 에이전트 인증서의 위치를 찾기 전에 먼저 하나 만들어야 합니다. 자세한 내용은 [efs (파일 시스템 암호화) 및 DRA (데이터 복구 에이전트) 인증서 만들기 및 확인](https://go.microsoft.com/fwlink/p/?linkid=853700)을 참조 하세요.
    
    기본적으로 작업 파일은 장치에 저장되고 사용자 프로필과 연결된 비밀 키를 사용하여 암호화됩니다. 사용자만 파일을 열고 암호 해독할 수 있습니다. 그러나 장치를 분실하거나 사용자가 제거된 경우 파일이 암호화된 상태에 계속 머물러 있을 수 있습니다. 관리자는 DRA (데이터 복구 에이전트) 인증서를 사용 하 여 파일의 암호를 해독할 수 있습니다.
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. 나열 된 모든 앱의 파일이 보호 되도록 추가 도메인 또는 SharePoint Online 위치를 추가 하려는 경우 **추가 네트워크 및 클라우드 위치 보호** 를 확장 합니다. 필드에 2개 이상의 항목을 입력해야 하는 경우 항목 사이에 세미콜론(;)을 사용하세요.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. 다음으로 **이러한 설정을 적용할 대상은 누구입니까?** 를 설정하세요. **모든 사용자** 기본 보안 그룹을 사용하지 않으려는 경우 **변경**을 선택하고 이 설정을 적용할 보안 그룹 \> **선택**을 선택합니다.
12. 마지막으로 **추가**를 선택하여 정책을 저장하고 장치에 할당합니다. 

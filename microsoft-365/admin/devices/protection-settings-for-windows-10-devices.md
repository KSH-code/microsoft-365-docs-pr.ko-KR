---
title: 디바이스에 대한 응용 프로그램 보호 Windows 10 편집하거나 설정
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
description: 앱 관리 정책을 만들거나 편집하고 사용자의 개인 앱 디바이스에서 작업 파일을 보호하는 Windows 10 대해 자세히 알아보습니다.
ms.openlocfilehash: 6370f2c21ce9f8de1223d5445c87abf197c0cf89
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165487"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>디바이스의 응용 프로그램 보호 Windows 10 설정 또는 편집

이 문서는 이 문서에 Microsoft 365 Business Premium.

## <a name="edit-an-app-management-policy-for-windows-10"></a>사용자에 대한 앱 관리 정책 Windows 10

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.     
2. 왼쪽 nav에서 장치 **정책을** \> **선택 합니다.**
1. 기존 앱 Windows 정책을 선택한 다음 편집 **을 선택하세요.**
1. 변경하려는 설정 옆에 있는 편집을 선택한 다음 저장 을 **선택 합니다.** 

## <a name="create-an-app-management-policy-for-windows-10"></a>Windows 10용 앱 관리 정책 만들기

사용자들이 업무를 수행할 수 있는 개인 Windows 10 장치를 갖고 있는 경우, 해당 장치에서도 데이터를 보호할 수 있습니다.
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다. 
2. 왼쪽 nav에서 장치 정책 **추가** \> **를** \> **선택 합니다.**
3. **정책 추가** 창에서 이 정책의 고유 이름을 입력합니다. 
4. **정책 유형** 에서 **Windows 10용 응용 프로그램 관리** 를 선택합니다.
5. 장치 **유형에서** 개인  또는 회사 소유 **를 선택하세요.**
6. **작업 파일 암호화** 가 자동으로 켜집니다. 
7. 사용자가 작업 파일을 개인 PC에 저장하지 않도록 하려면 **사용자가 회사 데이터를 개인 파일로 복사하는 것을 차단하고 회사 파일은 비즈니스용 OneDrive에 저장하도록 합니다.** 를 **켜기** 로 설정하세요. 
9. 에서 **데이터 복구를 Windows 확장합니다.** 을 으로 설정하는 **것이 좋습니다.**
    데이터 복구 에이전트 인증서의 위치를 찾기 전에 먼저 하나 만들어야 합니다. 자세한 내용은 [EFS(파일 시스템 암호화) DRA(데이터](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate)복구 에이전트) 인증서 만들기 및 확인을 참조하세요.
    
    기본적으로 작업 파일은 장치에 저장되고 사용자 프로필과 연결된 비밀 키를 사용하여 암호화됩니다. 사용자만 파일을 열고 암호 해독할 수 있습니다. 그러나 장치를 분실하거나 사용자가 제거된 경우 파일이 암호화된 상태에 계속 머물러 있을 수 있습니다. 관리자는 DRA(데이터 복구 에이전트) 인증서를 사용하여 파일의 암호를 해독할 수 있습니다.
    
    ![Browse to Data Recovery Agent certificate.](../../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. 추가 **도메인 또는** SharePoint 온라인 위치를 추가하려면 추가 네트워크 및 클라우드 위치 보호를 확장하여 나열된 모든 앱의 파일이 보호되어 있는지 확인합니다. 필드에 2개 이상의 항목을 입력해야 하는 경우 항목 사이에 세미콜론(;)을 사용하세요.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. 다음으로 **이러한 설정을 적용할 대상은 누구입니까?** 를 설정하세요. **모든 사용자** 기본 보안 그룹을 사용하지 않으려는 경우 **변경** 을 선택하고 이 설정을 적용할 보안 그룹 \> **선택** 을 선택합니다.
12. 마지막으로 **추가** 를 선택하여 정책을 저장하고 장치에 할당합니다.
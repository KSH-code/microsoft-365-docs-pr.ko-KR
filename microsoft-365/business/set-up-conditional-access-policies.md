---
title: Microsoft 365 캠페인에 대 한 조건부 액세스 정책 설정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 캠페인에 대 한 조건부 액세스 정책을 설정 하 여 상당한 추가 보안을 추가 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: eda65e335df2a7c2c443d7095f7b35b5c1cf27e4
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561223"
---
# <a name="set-up-conditional-access-policies"></a>조건부 액세스 정책 설정

[조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) 정책은 상당히 추가 보안을 추가 합니다. Microsoft는 모든 고객에 게 권장 되는 기본 조건부 액세스 정책 집합을 제공 합니다. 기본 정책은 일반적인 여러 공격 으로부터 조직을 보호 하는 데 도움이 되는 미리 정의 된 정책의 집합입니다. 이러한 일반적인 공격에는 암호 스프레이, replay 및 피싱이 포함 될 수 있습니다.

관리자 및 사용자는 이러한 정책을 통해 특정 조건이 충족 될 때 다단계 인증 또는 MFA 라는 두 번째 인증 양식을 입력 해야 합니다. 예를 들어 사용자가 다른 국가에서 로그인 하는 경우 로그인이 위험한 것으로 간주 될 수 있으며 사용자는 추가 인증 양식을 제공 해야 합니다. 

현재 기본 정책에는 다음이 포함 됩니다.
- 관리자 **에 게 MFA 필요를 요구** &ndash; 하는 경우 전역 관리자를 포함 하 여 가장 권한이 부여 된 관리자 역할에 대해 다단계 인증이 필요 합니다.
- **최종 사용자 보호** &ndash; 를 사용 하려면 로그인이 위험한 경우에만 사용자에 대 한 다단계 인증이 필요 합니다. 
- **레거시 인증** &ndash; 차단 이전 버전의 클라이언트 앱과 일부 새 앱은 보다 새로운 비보안 인증 프로토콜을 사용 하지 않습니다. 이러한 이전 앱은 조건부 액세스 정책을 우회 하 여 환경에 대 한 무단 액세스를 얻을 수 있습니다. 이 정책은 조건부 액세스를 지원 하지 않는 클라이언트의 액세스를 차단 합니다. 
- &ndash; **서비스 관리에 MFA 필요를 요구** 하는 경우 Azure portal을 비롯 하 여 관리 도구에 액세스 하기 위한 다단계 인증이 필요 합니다 (기준 정책 구성). 

이러한 모든 기본 정책을 사용 하도록 설정 하는 것이 좋습니다. 이러한 정책을 사용 하도록 설정 하 고 나면 관리자 및 사용자에 게 Azure Multii-요인 인증을 등록 하 라는 메시지가 표시 됩니다.

이러한 정책에 대 한 자세한 내용은 [기본 정책 이란](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?를 참조 하십시오.


## <a name="set-up-baseline-policies"></a>기본 정책 설정

1. [Azure 포털로](https://portal.azure.com)이동한 다음 **azure Active Directory** \> **조건부 액세스**로 이동 합니다.
    
    기본 정책은 페이지에 나열 됩니다. <br/> <br/>
    ![조건부 액세스에 대 한 기준 정책을 나열 하는 페이지입니다.](../media/baslinepolicies.png)
1. 각 정책에 대해 다음과 같은 구체적인 지침을 참조 하세요.

  - [관리자를 위해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [사용자에 대해 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [레거시 인증 차단](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [서비스 관리를 위해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

승인 된 클라이언트 앱을 요구 하는 등의 다양 한 추가 정책을 설정할 수 있습니다. 자세한 내용은 [조건부 액세스 설명서](https://docs.microsoft.com/azure/active-directory/conditional-access/)를 참조 하세요.

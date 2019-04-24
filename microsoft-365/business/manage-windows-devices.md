---
title: 도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Microsoft 365에서 로컬 AD에 가입 된 Windows 10 장치를 보호 하도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: d61b3bf6be50d6b21e7b883774567bb63995e60e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278080"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정

조직에서 windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business를 설정 하 여 windows 10 장치를 보호 하 되, 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다. 먼저 Active directory를 azure active directory와 동기화 한 다음 azure AD를 사용 하 여 Windows 10 장치를 등록 하 고 Microsoft 365 Business에서 모바일 장치 관리용으로 등록 하 여이를 설정할 수 있습니다.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Microsoft 365 Business에서 관리할 도메인 가입 장치 설정

온-프레미스 Active directory 외에 azure Active directory에서 제공 하는 기능을 활용 하기 위해 조직의 도메인에 가입 된 장치를 설정 하려면 **하이브리드 Azure AD에 가입 된 장치**를 구현할 수 있습니다. 온-프레미스 Active directory 및 Azure Active directory에 모두 가입 된 장치입니다. 하이브리드 Azure AD 조인 장치는 Microsoft 365 Business에서 보호 하 고 관리할 수 있습니다.. 
  
Windows 10 장치 하이브리드 Azure AD를 가입 하 고 Microsoft 365 Business에 의해 관리 되도록 하려면 아래 단계를 완료 합니다.
  
1. 사용자, 그룹 및 연락처를 로컬 active directory에서 Azure active directory로 동기화 하려면 [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)에 설명 된 대로 디렉터리 동기화 마법사 및 azure active Directory Connect를 실행 합니다.
    
    > [!NOTE]
    > 이 단계는 Microsoft 365 비즈니스에서 동일 합니다. 
  
2. 3 단계를 완료 하 여 Windows 10 장치를 하이브리드 Azure AD에 연결 된 상태로 설정 하기 전에 다음 필수 구성 요소를 충족 하는지 확인 해야 합니다.
    
   - 최신 버전의 Azure AD connect를 실행 하 고 있습니다.
    
   - azure ad connect에서 하이브리드 Azure ad에 가입 하려는 장치의 모든 컴퓨터 개체를 동기화 했습니다. 컴퓨터 개체가 특정 OU (조직 구성 단위)에 속하는 경우 이러한 ou가 Azure AD connect 에서도 동기화 되도록 설정 되어 있는지 확인 합니다.
    
3. Intune에서 하이브리드 Azure AD에 가입 하 고 사용자가 모바일 장치 관리용으로 등록할 수 있도록 기존 도메인에 가입 된 Windows 10 장치 등록 (Microsoft 365 Business):
    
4. [하이브리드 Azure Active Directory 가입 된 장치를 구성 하는 방법](https://go.microsoft.com/fwlink/p/?linkid=872870)에 대 한 단계별 지침을 따릅니다. 이렇게 하면 온-프레미스 Active Directory에 가입 된 Windows 10 컴퓨터를 동기화 하 고 클라우드를 준비할 수 있습니다.
    
5. windows 10 장치를 모바일 장치 관리에 등록 하려면 설명을 위해 [그룹 정책을 사용 하 여 Intune을 사용 하 여 windows 10 장치 등록](https://go.microsoft.com/fwlink/p/?linkid=872871) 을 참조 하십시오. 로컬 컴퓨터 수준에서 또는 대량 작업을 위해 그룹 정책을 설정할 수 있으며, 도메인 컨트롤러 서버에서이 그룹 정책 설정을 만들 수 있습니다. 
    


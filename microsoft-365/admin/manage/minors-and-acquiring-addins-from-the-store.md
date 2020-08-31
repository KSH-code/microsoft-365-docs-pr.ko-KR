---
title: 미성년자가을 사용 하 여 스토어에서 추가 기능 가져오기
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 미성년자가의 개인 데이터를 제어 하는 GDPR (일반 데이터 보호 규정) 규정에 대해 알아봅니다.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306554"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>미성년자가을 사용 하 여 스토어에서 추가 기능 가져오기

GDPR (일반 데이터 보호 규정)은 실제 5 월 25 일 2018이 되는 유럽 연합 규정입니다. 사용자에 게 해당 데이터에 대 한 권한을 부여 하 고 보호 합니다. GDPR의 특징 중 하나는 미성년자가가 자신의 부모 또는 보호를 승인 하지 않은 파티에 개인 데이터를 보낼 수 없다는 것입니다. 약간만 정의 되는 특정 기간은 개인이 있는 지역에 따라 달라 집니다.
  
자녀 보호에 대 한 법적 규정이 있는 지역에는 미국, 대한민국, 영국 및 유럽 연합 등이 있습니다. 이러한 지역의 경우 저장소에서 새 Office 추가 기능을 가져오는 작업과 이전에 획득 한 추가 기능을 실행 하는 것을 Azure Active Directory를 통해 차단 합니다. 법적 규정이 없는 국가의 경우에는 다운로드 제한이 없습니다.
  
사용자는 Azure Active Directory에 지정 된 데이터를 기반으로 하는 부 버전으로 확인 됩니다. 조직 관리자는 해당 사용자의 법적 연령 그룹 및 보호자 보호를 선언 해야 합니다.
  
특정 추가 기능을 사용 하 여 상위/보호자를 consents 하는 경우 조직 관리자는 중앙 집중식 배포를 사용 하 여 사용자가 동의 하는 모든 미성년자가에 해당 추가 기능을 배포할 수 있습니다.
  
미성년자가에 대 한 GDPR을 준수 하려면 학교/조직에 Office의 다음 빌드 중 하나가 배포 되었는지 확인 해야 합니다.
 
 **Word, Excel, PowerPoint 및 Project에 대해**다음을 수행 합니다. 

|**플랫폼** <br/> |**빌드 번호** <br/> |
|:-----|:-----|
|Microsoft 365 Apps for enterprise (현재 채널)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for enterprise (반기 엔터프라이즈 채널)  <br/> |8431.2159  <br/> |
|Windows 용 Office 2016  <br/> |16.0.4672.1000  <br/> |
|Windows 용 Office 2013  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|웹에 대 한 Office  <br/> |해당 없음  <br/> |
   
 **Outlook의 경우**: 
  
|**플랫폼** <br/> |**빌드 번호** <br/> |
|:-----|:-----|
|Windows 용 Outlook 2016 (MSI)  <br/> |TBD 만들기  <br/> |
|C2R (Windows 용 Outlook 2016)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|IOS 용 Outlook 모바일  <br/> |2.75.0  <br/> |
|Android 용 Outlook 모바일  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |해당 없음  <br/> |

 **Office 2013 요구 사항**
  
Windows 용 Word, Excel 및 PowerPoint 2013은 ADAL (Active Directory 인증 라이브러리)을 사용 하는 경우 동일한 미성년자가 검사를 지원 합니다. 다음에 설명 된 대로 준수에 대 한 두 가지 옵션이 있습니다.
  
- **ADAL을 사용 하도록 설정**합니다. 이 문서에서는 Office [365](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)2013에 대해 ADAL을 사용 하도록 설정 하는 방법에 대해 설명 합니다.<br/>또한 [Windows 장치에서 Office 2013에 대 한 최신 인증 사용](../security-and-compliance/enable-modern-authentication.md)에 설명 된 대로 ADAL을 사용 하도록 레지스트리 키를 설정 해야 합니다.<br/>또한 Office 2013에 대 한 다음 4 월 업데이트를 설치 해야 합니다.
    
  - [Office 2013의 보안 업데이트에 대 한 설명: 2018 년 4 월 10 일](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [4 월 3 일, 2018, Office 2013 업데이트 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **ADAL을 사용 하지 않도록 설정**합니다. Office 2013에서 ADAL을 사용 하도록 설정할 수 없는 경우 그룹 정책을 사용 하 여 Office 클라이언트에 대 한 저장소를 해제 하는 것이 좋습니다. Office 용 앱 설정을 해제 하는 방법에 대 한 정보는 [여기](https://technet.microsoft.com/library/cc178992.aspx)에 있습니다.

## <a name="related-articles"></a>관련 문서

[관리 센터에서 추가 기능 배포](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[관리 센터에서 추가 기능 관리](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
